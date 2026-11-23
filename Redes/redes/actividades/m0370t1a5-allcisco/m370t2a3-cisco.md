# M370T2A3-Cisco

Módulo 0370 - Redes

Ciclo ASIX\
Nombre alumno David Blanco

RÚBRICA Se hace en clases

DEDICACIÓN 4 horas

REFERENCIA Recursos de campus y bibliografía

Actividad Individual

Entrega PKT y link a Gitbook

## Objetivo

Introducción a Cisco packet tracer y las configuraciones de:

1. Router SOHO
   1. Abrir puertos (port forward)
   2. Redes de invitado
   3. DHCP y DNS
2. Servidores y servicios:
   1. DHCP y DNS
   2. WEB
   3. FTP

## Entrega

El PKT debidamente cumplimentado puesto que se hace con el profesor en clase.\
Un documento con las preguntas planteadas y sus respuestas.

## Práctica

La siguiente configuración intenta mostrar lo que sería tener una red de una empresa conectada a un ISP y la red detrás de un router inalámbrico en casa.

Nota: Trae de casa la topología de la red con todos los dispositivos conectados.

## Dispositivos a utilizar:

Tenemos las redes: LAN1-empresa, LAN2-casa y el ISP

### 1.1. LAN1-Empresa

* PC: 1
* Server: 1
* PC: 3
* Impresora: 1
* AP: 3 (A17, A18, A10)
* Switch: 1

### 1.2. LAN2-casa

* Router inalámbrico: 1
* Laptop: 2
* Impresora: 1

### 1.3. ISP

* Router: 2
* Server: 2

## A configurar de manera general:

1. Cada uno de los servidores tiene una página web que propongo personalizar.
2. El servidor Godo del ISP, es el servidor de DNS para todos los dispositivos
3. Configura el RIP en cada router

## A configurar en la Empresa:

1. El servidor Trantor de la empresa brinda servicio WEB, DHCP y DNS.
2. Agrega dos dispositivos (printer y un laptop) a la red de la empresa que reciban los parámetros de la red por DHCP.

## A configurar en el ISP:

1. El servidor Godo brinda servicio de DHCP y DNS.
2. El servidor Paco es un servidor de FTP¹.
3. Investiga cómo debes conectarte desde el equipo PC0 de la empresa al servicio de FTP que brinda Paco en el ISP. Explica y muestra un pantallazo.

Desde el equipo de empresa abrimos el Command Prompt, ejecutamos ftp 30.0.0.2, iniciamos sesión con el usuario cisco y contraseña cisco, y ejecutamos dir para listar los archivos disponibles en el servidor las capturas 1 y 2 están al final del documento.

¹ Investiga el uso del servicio FTP.

## A configurar en casa ¿Qué hemos configurado en el home router?

### 1. Configuración básica del router home:

1. IP de Internet
2. DNS apuntando al server Godo del ISP
3. Servicio de DHCP para los equipos de la casa

### 2. Wifi

1. Habilitar la 2.4GHz exclusivamente
2. Habilitar seguridad WPA2

### 3. Guest network

1. Habilitar el acceso de invitado sin posibilidad que pueda acceder a la red de casa
2. Deshabilitar el acceso a través de la MAC, a un PC (el de Xenxito) de casa para que no pudiera conectarse a la 2.4GHz

### 4. Access restriction

1. Configurar reglas de acceso a la red.

En este caso vamos a configurar una ACL estándar (1 – 99) donde estaríamos habilitando el bloqueo del protocolo HTTP a través del puerto 80 a los dispositivos especificados en la lista (en este ejemplo solo el PC con IP: 192.168.0.102).

Nota: Testear qué ocurre si únicamente bloqueamos el puerto 80 del protocolo HTTP y no lo hacemos para el puerto 443 de HTTPS.

Al bloquear únicamente el puerto 80 el equipo deja de poder navegar por páginas web sin cifrar, pero sigue accediendo con normalidad a todas las webs seguras que funcionan sobre HTTPS por el puerto 443 para cortar por completo la navegación web en ese dispositivo es necesario bloquear ambos puertos el 80 y el 443.

## Preguntas teóricas:

1. ¿Qué es el protocolo RIP? Es un protocolo de encaminamiento dinámico basado en vector de distancia que utiliza el número de saltos como métrica para seleccionar la mejor ruta hacia una red destino, con un límite máximo de 15 saltos.
2. Cuando estés configurando el RIP, observa en la parte de abajo de la ventana, justo donde dice «Equivalent IOS Commands» y escribe los comandos que ves que se generan al añadir redes que alcanzan ese router. router rip, version 2, network 192.168.3.0, network 30.0.0.0 .
3. ¿Qué tipo de IP tenemos en la red de la empresa? Una dirección IP privada de clase C perteneciente al rango reservado 192.168.3.0/24.
   1. ¿Cuántos dispositivos podemos configurar en la misma? Se pueden configurar hasta 254 dispositivos ya que de las 256 direcciones disponibles en una red /24, se reservan dos: una para la dirección de red y otra para la de broadcast.
4.  ¿Puedo hacer un ping entre el PC0 de la empresa y el switch? Argumentar

    No directamente, ya que por defecto los switches operan en capa 2 y no tienen una dirección IP asignada a menos que se configure explícitamente en una interfaz virtual.
5. La red del ISP es una simulación muy básica, a la que le hemos configurado redes del tipo:
   1. 30.0.0.0/8
   2. 40.0.0.0/8
   3. 50.0.0.0/8
   4. 80.0.0.0/8
      1. ¿Qué tipo de redes son éstas? Son redes de Clase A con una máscara de subred /8.
      2. ¿De cuántas direcciones IP válidas disponemos en este tipo de redes? Cada red /8 dispone de 2²⁴ − 2 = 16.777.214 direcciones IP válidas.
      3.  ¿Cuántas direcciones IP estamos utilizando de cada una?

          Únicamente las necesarias para las interfaces de los routers y servidores conectados en esos segmentos que normalmente 2 o 3 IPs por enlace.
      4. Si estamos diciendo que las redes 30, 40, 50 y 80 corresponden a una organización (ISP en este caso) ¿tendría sentido que utilizáramos redes diferentes en lugar de una misma red? Investiga unos mínimos² Sí, tiene sentido desde el punto de vista del diseño de red y la segmentación. Utilizar diferentes bloques de red permite delimitar dominios de broadcast, aplicar políticas de seguridad independientes, estructurar jerárquicamente el enrutamiento y evitar el agotamiento o la ineficiencia de utilizar una única red masiva para enlaces punto a punto o subredes separadas.
      5.  Investiga que es un Sistema Autónomo (AS) en redes. Si le preguntas al chatGPT adjunta las preguntas realizadas como parte de la bibliografía.

          Es una red o un grupo de redes IP bajo el control administrativo de una única entidad u organización que aplica una política de enrutamiento común y utiliza protocolos de pasarela exterior para intercambiar rutas con otros sistemas autónomos.
   5.  ¿Por qué no puedo hacer ping a un PC dentro de la casa?

       Porque está detrás del router doméstico (HomeRouter-PT4C, con red interna 192.168.0.0/24), que hace NAT y actúa como cortafuegos bloqueando por defecto el tráfico entrante que viene desde fuera hacia la red privada de casa.
6.  Explica que tenemos que configurar para poder tener acceso a la web www.casa.com que se hospeda en el servidor que tenemos en casa.

    Hay que configurar tres cosas: tener activo el servicio HTTP con la web en el servidor interno de casa (Portal\_de\_casa, 192.168.0.102), registrar www.casa.com en el servidor DNS (8.8.8.8) apuntando a la IP WAN del router de casa (13.0.0.2), y crear una regla de reenvío de puertos (Port Forwarding) en el router de casa redirigiendo el puerto 80 hacia 192.168.0.102.
7.  Testea y explica qué ocurre si eliminamos el DNS del server de la empresa.

    Los equipos de la empresa dejarán de acceder a las webs mediante nombres de dominio aunque seguirán teniendo conexión directa usando direcciones IP numéricas gracias al protocolo RIP.

## Prueba a configurar unos extras

### Empresa:

1. Añade dos portátiles y una impresora
2. Añade un AP
   1. Conecta un smartphone al AP

Se conectó un Access Point al switch de la empresa con el SSID Empresa\_wifi, se sustituyó el módulo Ethernet por la tarjeta Wi-Fi WPC300N en los dos portátiles y la impresora, y se conectaron junto con el smartphone a Empresa\_wifi por DHCP recibiendo direcciones 192.168.1.50 hasta la 192.168.1.53.

### ISP:

1.  ¿Qué cambios tenemos que hacer para que el server Paco brinde parámetros de red (direcciones IP) a dos PC que necesitamos conectar a la red 30.0.0.0/8.

    En el servidor FTP 30.0.0.2 entramos en Services > DHCP, encendemos el servicio, configuramos un pool con Default Gateway 30.0.0.1, DNS Server 8.8.8.8, Start IP Address 30.0.0.10 y Subnet Mask 255.0.0.0, y guardamos. Después ponemos DHCP en IP Configuration de los dos PCs.
2. Habilita el servicio FTP, aunque es más interesante desde Linux 😉

Conéctate desde un equipo cualquiera al servidor donde hayas habilitado el servicio de FTP.

Se activó el servicio FTP en 30.0.0.2 con el usuario cisco y contraseña cisco (permisos RWDNL) y se comprobó el acceso desde el equipo de empresa mediante ftp 30.0.0.2.

### Casa:

1.  Conéctate a la WIFI de Invitado con un teléfono y un tablet

    Al conectar un teléfono y una tablet a la red de invitados ambos reciben IP automática y salida a Internet, pero quedan aislados de la red local de casa sin poder comunicarse con los equipos internos 192.168.0.0/24.
2.  Prueba a habilitar la MAC de un equipo externo para que pueda acceder acceder al server de casa.

    En Wireless > Wireless MAC Filter, activando el filtro en modo Permit y añadiendo la MAC del equipo externo en la lista, ese equipo puede conectarse a la Wi-Fi mientras que cualquier otro dispositivo cuya MAC no esté en la lista queda bloqueado.
3.  ¿Qué le sucede al PC de Xenxita si bloqueo el acceso (Website Blocking by URL..) al server Godo?

    Al añadir la URL o IP del servidor en Website Blocking by URL Address dentro de la política aplicada a ese equipo, el router le bloquea el acceso a esa web en el navegador mientras el resto de páginas siguen funcionando.
4.  Testea la opción de "Blocked Applications"

    En Access Restrictions > Blocked Applications pasamos HTTP (80) a Blocked List y aplicamos la política al equipo seleccionado en Edit List. Al probar desde ese equipo, el tráfico web por HTTP (80) queda bloqueado, mientras que otros servicios que no están en la lista como por ejemplo HTTPS por el puerto 443 siguen funcionando con normalidad.

## 1. Incidencias tenidas durante el proceso de configuración.

Durante el montaje y las pruebas surgieron un par de fallos habituales que fuimos corrigiendo:

Al conectar el smartphone a la red inalámbrica de la empresa, al principio se asoció a otra zona/SSID distinto (Default o la red de casa), por lo que no recibía IP de 192.168.1.0/24 y fallaban los ping. Lo solucione cambiando manualmente el SSID a Empresa\_wifi en Config > Wireless0 y renovando la IP por DHCP.

En los portátiles y la impresora inalámbrica de la empresa, antes de conectarlos por Wi-Fi hubo que apagar el equipo en la pestaña Physical, quitar el módulo Ethernet de cable y poner la tarjeta inalámbrica WPC300N.

También tuve que revisar que en todos los routers estuviera activado RIP versión 2 con todas las redes directamente conectadas declaradas (ya que la versión 1 no trabaja bien con subredes y provocaba que faltaran rutas hacia el servidor FTP 30.0.0.2).

## 2. ¿Por qué no podemos acceder a la web del servidor de casa desde el ISP o la empresa? ¿Qué tenemos que configurar para poder hacerlo?

Por qué no se puede acceder: Porque el servidor de casa (Portal\_de\_casa, 192.168.0.102) está dentro de una red privada (192.168.0.0/24) detrás del router doméstico (HomeRouter-PT4C). Ese router hace NAT (traducción de direcciones) y actúa como cortafuegos bloqueando por defecto cualquier conexión entrante que venga desde fuera (desde el ISP o desde la empresa) hacia una IP privada interna.

Qué hay que configurar para poder hacerlo:

1. Tener el servicio HTTP encendido con la página web en el servidor de casa (192.168.0.102).
2. Configurar Port Forwarding (reenvío de puertos) en el router de casa (en Applications & Gaming > Single Port Forwarding), redirigiendo el tráfico externo que llegue al puerto 80 (TCP) hacia la IP privada 192.168.0.102.
3. Si queremos entrar por nombre de dominio (como www.casa.com) y no solo por IP, dar de alta un registro A en el servidor DNS (8.8.8.8) apuntando ese dominio a la IP WAN del router de casa (13.0.0.2).

## 3. ¿Cómo o qué detalle nos indica la conexión del router del proveedor de servicios con el home router de casa?

En la topología se ve porque la interfaz WAN (Internet / Gig0/1) del HomeRouter-PT4C está conectada directamente mediante cable al puerto Gig0/0/0 del router del ISP (Router2), compartiendo la misma red de enlace 13.0.0.0/8 (13.0.0.1 en el router del ISP y 13.0.0.2 en la pata WAN del router de casa, actuando 13.0.0.1 como puerta de enlace hacia Internet).

## 4. ¿Cómo se lleva a cabo internamente la resolución del dominio y la descarga del HTML desde la perspectiva del cliente (navegador) y del DNS?

1. Petición en el navegador: El usuario escribe la URL en el navegador (por ejemplo http://www.paco.com).
2. Búsqueda en caché: El sistema operativo y el navegador miran primero si ya tienen guardada la IP de ese dominio en su caché local o en el archivo hosts.
3. Consulta DNS: Si no la tienen, el cliente envía una consulta DNS (por UDP puerto 53) al servidor DNS configurado en su tarjeta de red (8.8.8.8).
4. Respuesta del DNS: El servidor DNS busca el registro A asociado a ese nombre de dominio en su tabla y devuelve al cliente la dirección IP correspondiente.
5. Conexión HTTP y descarga del HTML: Con esa IP, el navegador abre una conexión TCP hacia el puerto 80 (HTTP) o 443 (HTTPS) del servidor web, manda una petición GET /, el servidor responde con el código 200 OK junto con el archivo HTML (y recursos asociados) y el navegador lo renderiza en pantalla.

## 5. Cambia los DNS de los servidores y haz que todos apunten al server de Google 8.8.8.8.

En nuestra topología ya apuntamos los equipos y servidores al DNS 8.8.8.8, comprobando que todos resuelven los dominios contra ese único servidor.

### 5.1. ¿Cómo se lleva a cabo la resolución del dominio a nivel del DNS?

El DNS (8.8.8.8) busca el dominio en su tabla/caché (registros A o CNAME) y devuelve la IP directamente si ya la tiene (como en Packet Tracer). Si no la tiene en Internet, consulta en cadena a los servidores raíz, al TLD (.com, .es, etc.) y al DNS autoritativo, guarda la respuesta en caché y se la envía al cliente.

## 6. Analiza la siguiente situación: Imagina que al escenario que hemos configurado (LAN-WAN-HOMELAN) añadimos una sucursal de la empresa (LAN) y queremos que utilice la misma dirección IP de red: 192.168.1.0/24. Dicha sucursal está también conectada al ISP.

### 6.1. ¿Podemos utilizar la misma dirección IP de red en la sucursal nueva y en la red de la empresa (la que ya tenemos configurada)? Ten en cuenta lo que sucede en la realidad y lo que tenemos configurado en Cisco.

En lo que tenemos configurado en Cisco (enrutamiento directo con RIPv2): No funcionaría bien, porque en nuestro montaje los routers están anunciando las redes directamente por RIPv2 sin NAT entre sedes. Si dos redes distintas conectadas al mismo dominio de enrutamiento anuncian 192.168.1.0/24, se produce un conflicto de rutas (enrutamiento ambiguo o solapamiento de subredes): los routers no sabrían hacia qué sede mandar los paquetes dirigidos a 192.168.1.x y el tráfico se perdería o iría solo a una de las dos.

En la realidad: Sí es muy habitual que dos oficinas o redes distintas usen internamente el mismo rango privado (192.168.1.0/24), porque las IPs privadas no se enrutan directamente por Internet. Cada sede sale a Internet haciendo NAT/PAT detrás de su propia IP pública, así que de cara al ISP son dos IPs públicas diferentes y no chocan. Ahora bien, si quisieras unir ambas sedes por una VPN sitio a sitio para que se vean entre sí directamente, entonces sí habría conflicto de direcciones y tocaría cambiar el rango de una de las sedes o aplicar doble NAT.

## 7. En relación a los puertos lógicos:

### 7.1. ¿Cómo se clasifican dichos puertos y por qué (su uso)?

La IANA divide los puertos lógicos (del 0 al 65535) en tres rangos según su función y control:

Puertos bien conocidos (Well-Known Ports, 0 – 1023): Están reservados para los servicios y protocolos estándar más importantes del sistema y de Internet (como HTTP, HTTPS, FTP, SSH o DNS), de modo que cualquier cliente sepa siempre a qué puerto conectarse por defecto.

Puertos registrados (Registered Ports, 1024 – 49151): Se asignan a aplicaciones, bases de datos o servicios específicos de fabricantes para evitar conflictos entre programas (por ejemplo MySQL, RDP o servidores de juegos/contenedores).

Puertos dinámicos o privados (Dynamic / Ephemeral Ports, 49152 – 65535): No están asignados a ningún servicio fijo; los usa temporalmente el sistema operativo del cliente como puerto de origen cada vez que abre una conexión saliente hacia un servidor.

## 8. Dime los puertos que se utilizan para los siguientes servicios y qué hacen cada uno de ellos:

| Servicio               | Puerto(s) y protocolo                    | ¿Para qué sirve?                                                                                                             |
| ---------------------- | ---------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| 1. FTP                 | 20 y 21 (TCP)                            | Transferencia de archivos entre cliente y servidor (el 21 controla la sesión y comandos, y el 20 envía los datos).           |
| 2. SSH                 | 22 (TCP)                                 | Acceso remoto seguro por consola/terminal cifrada y transferencia segura de archivos (SFTP/SCP).                             |
| 3. DNS                 | 53 (UDP / TCP)                           | Traduce nombres de dominio (como www.google.com) a direcciones IP y viceversa.                                               |
| 4. HTML (HTTP / HTTPS) | 80 (TCP) y 443 (TCP)                     | HTML es el lenguaje de las páginas web; para servirlas se usa HTTP en el puerto 80 (sin cifrar) o HTTPS en el 443 (cifrado). |
| 5. MySQL               | 3306 (TCP)                               | Conexión y gestión remota de bases de datos relacionales MySQL / MariaDB.                                                    |
| 6. Portainer           | 9000 (HTTP) / 9443 (HTTPS)               | Interfaz web para administrar y desplegar contenedores, imágenes y redes en Docker.                                          |
| 7. SMTP                | 25 (TCP) (también 587 / 465)             | Envío y transferencia de correos electrónicos desde el cliente al servidor o entre servidores de correo.                     |
| 8. POP3                | 110 (TCP) (995 con SSL/TLS)              | Descarga de correos electrónicos desde el servidor al cliente (por defecto los borra del servidor tras bajarlos).            |
| 9. IMAP                | 143 (TCP) (993 con SSL/TLS)              | Acceso y sincronización del correo electrónico manteniendo los mensajes y carpetas directamente en el servidor.              |
| 10. DHCP               | 67 (servidor) y 68 (cliente) (UDP)       | Asigna automáticamente la configuración de red (IP, máscara, puerta de enlace y DNS) a los dispositivos al conectarse.       |
| 11. VNC                | 5900 (TCP) (y siguientes según pantalla) | Control remoto gráfico del escritorio de otro ordenador viendo su pantalla en tiempo real.                                   |
| 12. LDAP               | 389 (TCP/UDP) (636 LDAPS)                | Consulta y autenticación contra servicios de directorio centralizados (usuarios, grupos y permisos en red).                  |
| 13. OpenVPN            | 1194 (UDP / TCP)                         | Creación de túneles VPN cifrados para conectar redes o usuarios remotos de forma segura.                                     |
| 14. WireGuard          | 51820 (UDP)                              | Protocolo VPN moderno, ligero y muy rápido basado en criptografía de clave pública sobre UDP.                                |
| 15. NTP                | 123 (UDP)                                | Sincronización exacta del reloj y la hora entre ordenadores, routers y servidores de una red.                                |

## Capturas ejercicio cisco

Captura 1: Comprobación de conectividad ping y conexión FTP al servidor 30.0.0.2 con el usuario cisco desde el equipo de Empresa.

Captura 2: Listado de archivos del directorio /ftp dir dentro de la sesión FTP en 30.0.0.2.
