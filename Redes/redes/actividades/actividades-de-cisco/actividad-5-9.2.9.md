# Actividad 5 (9.2.9)

## Tabla de asignación de direcciones

| Dispositivo | Interfaz    | Dirección MAC  | Interfaz del switch |
| ----------- | ----------- | -------------- | ------------------- |
| Router0     | Gg0/0       | 0001.6458.2501 | G0/1                |
| Router0     | S0/0/0      | N/A            | N/A                 |
| Router1     | G0/0        | 00E0.F7B1.8901 | G0/1                |
| Router1     | S0/0/0      | N/A            | N/A                 |
| 10.10.10.2  | Inalámbrica | 0060.2F84.4AB6 | F0/2                |
| 10.10.10.3  | Inalámbrica | 0060.4706.572B | F0/2                |
| 172.16.31.2 | F0          | 000C.85CC.1DA7 | F0/1                |
| 172.16.31.3 | F0          | 0060.7036.2849 | F0/2                |
| 172.16.31.4 | G0          | 0002.1640.8D75 | F0/3                |

## Objetivos

Parte 1: Examinar una solicitud de ARP\
Parte 2: Examinar una tabla de direcciones MAC del switch\
Parte 3: Examinar el proceso ARP en comunicaciones remotas

## Aspectos básicos

Esta actividad está optimizada para la visualización de PDU. Los dispositivos ya están configurados. Reunirá información de PDU en el modo de simulación y responderá una serie de preguntas sobre los datos que obtenga.

## Instrucciones

### Parte 1: Examinar una solicitud de ARP

#### Paso 1: Generar solicitudes de ARP haciendo ping a 172.16.31.3 en 172.16.31.2.

Abra un símbolo del sistema.

a. Haga click en 172.16.31.2 y abra el Command Prompt.

b. Introduzca el comando `arp -d` para borrar la tabla ARP.

Cierre símbolo del sistema

c. Ingrese al modo Simulation (Simulación) e introduzca el comando `ping 172.16.31.3`. Se generan dos PDU. El comando ping no puede completar el paquete ICMP sin conocer la dirección MAC del destino. Por lo tanto, la PC envía una trama de difusión de ARP para encontrar la dirección MAC del destino.

d. Haga clic en Capture/Forward (Capturar/Adelantar) una vez. La PDU ARP mueve el Switch1, mientras que la PDU ICMP desaparece y espera la respuesta de ARP. Abra la PDU y registre la dirección MAC de destino.

**Pregunta:**

¿Esta dirección se indica en la tabla anterior? No. La dirección MAC de destino es FFFF.FFFF.FFFF que es la dirección MAC de difusión y no aparece en la tabla de asignación de direcciones porque no pertenece a ningún dispositivo específico.

e. Haga clic en Capture/Forward (Capturar/Adelantar) para mover la PDU al siguiente dispositivo.

**Pregunta:**

¿Cuántas copias de la PDU realizó el Switch1?&#x20;

El Switch1 realizó 3 copias de la PDU y reenvió la trama de difusión por todos sus puertos activos, excepto por el puerto F0/1 por donde la recibió.

¿Cuál es la dirección IP del dispositivo que aceptó la PDU?&#x20;

La PC con la dirección IP 172.16.31.3.

f. Abra la PDU y examine la capa 2.

**Pregunta:**

¿Qué sucedió con las direcciones MAC de origen y destino?&#x20;

Las MAC de origen y destino se invirtieron la de la PC 172.16.31.3 pasó a ser el origen y la de 172.16.31.2 el destino, convirtiéndose en una comunicación unicast.

g. Haga clic en Capture/Forward (Capturar/Adelantar) hasta que la PDU regrese a 172.16.31.2.

**Pregunta:**

¿Cuántas copias de la PDU realizó el switch durante la respuesta de ARP?&#x20;

No se hizo ninguna copia porque el switch envió una única respuesta unidireccional dirigida específicamente a la interfaz F0/1 vinculada a la PC 172.16.31.2.

#### Paso 2: Examinar la tabla ARP.

a. Observe que vuelve a aparecer el paquete ICMP. Abra la PDU y examine las direcciones MAC.

**Pregunta:**

¿Las direcciones MAC de origen y destino coinciden con sus direcciones IP?&#x20;

Sí. La dirección MAC de origen corresponde a la dirección IP de origen 172.16.31.2 y la dirección MAC de destino corresponde a la dirección IP del destinatario 172.16.31.3.

b. Vuelva a cambiar al modo Realtime (Tiempo real); el ping se completa.

c. Haga clic en 172.16.31.2 e introduzca el comando `arp -a`.

**Pregunta:**

¿A qué dirección IP corresponde la entrada de la dirección MAC?&#x20;

Corresponde a la dirección IP 172.16.31.3.

En general, ¿cuándo emite una terminal una solicitud de ARP?&#x20;

Una terminal emite una solicitud ARP cuando necesita enviar un paquete IP a una dirección IP de destino situada en la misma subred, pero desconoce la dirección MAC física correspondiente asociada a esa IP.

### Parte 2: Examinar una tabla de direcciones MAC del switch

#### Paso 1: Generar tráfico adicional para completar la tabla de direcciones MAC del switch.

Abra un símbolo del sistema.

a. Desde 172.16.31.2, introduzca el `172.16.31.4` comando ping.

b. Haga clic en 10.10.10. 2 y abra el símbolo del sistema.

c. Introduzca el comando `ping 10.10.10.3`.

**Pregunta:**

¿Cuántas respuestas se enviaron y se recibieron?&#x20;

Se enviaron 4 solicitudes de eco ICMP y se recibieron 4 respuestas válidas.

Cierre símbolo del sistema

#### Paso 2: Examinar la tabla de direcciones MAC en los switches.

a. Haga clic en Switch1 y, a continuación, en la ficha CLI. Introduzca el comando `show mac-address table`.

**Pregunta:**

¿Las entradas corresponden a las de la tabla de arriba?&#x20;

Sí. Las direcciones MAC aprendidas dinámicamente en los puertos F0/1, F0/2, F0/3 y G0/1 coinciden con las direcciones asignadas a las PCs locales y al enlace hacia el router.

b. Haga clic en Switch0 y, a continuación, en la ficha CLI. Introduzca el comando `show mac-address table`.

**Preguntas:**

¿Las entradas corresponden a las de la tabla de arriba?&#x20;

Sí. Muestra las direcciones MAC aprendidas en sus respectivas interfaces y puntos de acceso asociados.

¿Por qué hay dos direcciones MAC asociadas a un puerto?&#x20;

Porque el puerto está conectado a un dispositivo intermediario que interconecta a múltiples dispositivos finales, permitiendo que el puerto aprenda las direcciones MAC de todos los equipos conectados detrás de él.

### Parte 3: Examinar el proceso ARP en comunicaciones remotas

#### Paso 1: Generar tráfico para producir tráfico ARP.

Abra un símbolo del sistema.

a. Haga click 172.16.31.2 y abra el Command Prompt.

b. Introduzca el comando `ping 10.10.10.1`.

c. Escriba `arp -a`.

**Pregunta:**

¿Cuál es la dirección IP de la nueva entrada de la tabla ARP?&#x20;

La dirección IP de la nueva entrada es 172.16.31.1, que corresponde a la interfaz del router local.

d. Escriba `arp -d` para borrar la tabla ARP y cambiar al modo Simulation (Simulación).

e. Repita el ping a 10.10.10.1.

**Pregunta:**

¿Cuántas PDU aparecen?&#x20;

Aparecen 2 PDU, una PDU ICMP para el paquete de ping y una PDU ARP para la resolución de direcciones.

Cierre símbolo del sistema

f. Haga clic en Capture/Forward (Capturar/Adelantar). Haga clic en la PDU que ahora se encuentra en el Switch1.

**Pregunta:**

¿Cuál es la dirección IP de destino objetivo de la solicitud de ARP?&#x20;

La dirección IP 172.16.31.1 que es la de la interfaz del router local.

g. La dirección IP de destino no es 10.10.10.1.

**Pregunta:**

¿Por qué?&#x20;

Porque el host de destino se encuentra en una red remota diferente. Y eso ocurre cuando un host envía datos a una red remota, emite una solicitud ARP dirigida a la dirección IP de su puerta de enlace predeterminada como es el gateway, no a la IP del destino final, para que el router se encargue de encaminar el paquete.

#### Paso 2: Examinar la tabla ARP en el Router1.

a. Cambie al modo Realtime. Haga click en el Router1 y luego en la pestaña CLI

b. Ingrese al modo EXEC privilegiado y, a continuación, introduzca el comando `show mac-address-table`.

**Pregunta:**

¿Cuántas direcciones MAC figuran en la tabla? ¿Por qué?&#x20;

No aparece ninguna MAC porque el Router1 es un dispositivo de Capa 3 y no un switch de Capa 2; los routers no usan tablas de direcciones MAC, sino tablas de enrutamiento y ARP.

c. Introduzca el comando `show arp`.

**Preguntas:**

¿Existe una entrada para 172.16.31.2?&#x20;

No, no existe una entrada directa para 172.16.31.2 en el Router1 porque esa dirección IP pertenece a la LAN local conectada al Router 0. El Router1 solo registra las entradas ARP correspondientes a las subredes conectadas directamente a sus propias interfaces.

¿Qué sucede con el primer ping en una situación en la que el router responde a la solicitud de ARP?&#x20;

El primer paquete de ping falla lo que hace que se agota el tiempo de espera mientras el router espera a que se complete la solicitud y respuesta ARP. Una vez que el router aprende la dirección MAC, los siguientes paquetes de ping 2, 3 y 4 se envían y reciben correctamente.
