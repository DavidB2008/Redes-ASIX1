# Actividad 1 (1.0.5)

Packet Tracer - Exploración de Modo Lógico y Físico

### Objetivos

Parte 1: Investigar la Barra de Herramientas Inferior\
Parte 2: Investigar Dispositivos en un Armario de Cableado\
Parte 3: Conectar Dispositivos Finales a Dispositivos de Red\
Parte 4: Instalar un Router de Respaldo\
Parte 5: Configurar un Nombre de Host\
Parte 6: Explora el resto de la Red

### Aspectos básicos/Situación

El modelo de red de esta actividad Packet Tracer Physical Mode (PTPM) incorpora muchas de las tecnologías que puede dominar en los cursos de Cisco Networking Academy. Y representa una versión simplificada de la forma en que podría verse una red de pequeña o mediana empresa.

La mayoría de los dispositivos de la sucursal de Seward y del Centro de Datos de Warrenton ya están implementados y configurados. Usted acaba de ser contratado para revisar los dispositivos y redes implementados. No es importante que comprenda todo lo que vea y haga en esta actividad. Siéntase libre de explorar la red por usted mismo. Si desea hacerlo de manera más sistemática, siga estos pasos. Responda las preguntas lo mejor que pueda.

Nota: Esta actividad se abre y se centra en el modo Físico. Muchas de las actividades de Packet Tracer que encuentre en los cursos de Cisco Networking Academy utilizarán el modo Lógico. Puede cambiar entre estos modos en cualquier momento para comparar las diferencias haciendo clic en los botones Lógico (Shift+L) y Físico (Shift+P). Sin embargo, en otras actividades de este curso puede estar bloqueado de un modo u otro.

### Instrucciones

#### Parte 1: Investigar la Barra de Herramientas Inferior

La barra de herramientas de iconos en la esquina inferior izquierda tiene varias categorías de componentes de red. Debería ver categorías que corresponden a Dispositivos de Red, Dispositivos Finales, y Componentes. La cuarta categoría (con el icono del rayo) es Conexiones y representa los medios de red compatibles con Packet Tracer. Las dos últimas categorías son Miscelánea y Conexión multiusuario.

¿Cuáles son las subcategorías de Dispositivos de Red? Las subcategorías son los routers, switches, hubs, wireless devices, security y WAN emulation.

Escriba sus respuestas aquí.

#### Parte 2: Investigar Dispositivos en un Armario de Cableado

a. Si fuiste a explorar, vuelve a modo Físico e Intercity ahora. En la barra azul superior, haga clic en Físico y, a continuación, utilice los botones Panel de Navegación o Nivel Atrás para desplazarse a Intercity.

b. Haga clic en Seward y, a continuación, haga clic en la Sucursal.

c. Haga clic en el Armario de Cableado de la Sucursal. Observe que el armario de cableado tiene un Rack, un Tablero de Cables, una Mesa y un Estante.

El Rack contiene dispositivos que se pueden montar en rack. Si amplía el rack (herramienta de zoom o Ctrl+rueda de desplazamiento), puede ver que los dispositivos están atornillados (montados) en el rack. Debajo del dispositivo de distribución de energía, encontrará un router. Los routers conectan redes diferentes.

d. Debajo del router hay dos switches. Estos switches proporcionan conexiones por cable para conectarse a otros dispositivos. Observe que los dispositivos tienen un nombre asignado por el administrador de red.

¿Qué dispositivos utilizan una conexión por cable para conectarse al switch ALS2? Los dispositivos son el web server, backup router, PC\_1 y otros dispositivos finales de la red de la sucursal.

Escriba sus respuestas aquí.

e. Debajo de los switches del Rack se encuentra un punto de acceso inalámbrico denominado Access\_Point. Los puntos de acceso inalámbricos utilizan una conexión inalámbrica para conectarse a otros dispositivos. Cambie al modo Lógico. ¿Qué dispositivo está conectado a Access\_Point? Es el dispositivo Laptop 1. Es el único portátil configurado con el SSID Branch Office, el mismo del Access Point, y se conecta de forma inalámbrica.

Escriba sus respuestas aquí.

f. Cambie al modo Físico. Deberías estar de vuelta en el Armario de Cableado de la Sucursal. ¿Dónde se encuentra físicamente el dispositivo conectado a Access\_Point? En el armario de cableado de la sucursal de Seward (Intercity > Seward > Sucursal > Armario de Cableado), encima de la mesa. No está en el rack: el Access Point sí está en el Rack, pero el portátil se conecta por WiFi desde la mesa.

Escriba sus respuestas aquí.

#### Parte 3: Conectar Dispositivos Finales a Dispositivos de Red

Los dispositivos se pueden conectar de varias maneras. Para la conectividad de red, los dispositivos normalmente se conectan mediante un cable directo de cobre o de forma inalámbrica. Para la conectividad de administración, los dispositivos normalmente se conectan mediante un cable de consola o un cable USB.

Nota: Packet Tracer calificará el resto de esta actividad. En cualquier momento, puede hacer clic en Comprobar resultados en la parte inferior de la ventana Tareas. A continuación, haga clic en Elementos de evaluación para ver qué elementos aún no ha completado.

a. Investigue el Tablero de Cables. Incluye dos cables de Consola, diez cables directos de cobre, cuatro cables de Fibra, dos cables Coaxiales y dos cables USB. Observe que las representaciones de cable en modo Físico son más representativas de sus homólogos del mundo real. Cambie al modo Lógico. Observe que las representaciones de cable son diferentes en este modo.

b. Cambie al modo Físico. Haga clic en un cable directo de cobre del Tablero de Cables.

c. Mueva el ratón sobre los puertos de PC\_1 hasta que vea la ventana emergente FastEthernet0. El otro puerto RS232 es para conectar cables de Consola.

d. Con el cable directo de cobre todavía seleccionado, haga clic en el puerto FastEthernet0 para conectar el cable. Ahora el puerto debe estar resaltado en verde.

e. Conecte el otro extremo del cable al switch ALS2 haciendo clic en un puerto Fast Ethernet vacío. El cable ahora debería colgar entre la PC\_1 y el puerto de ALS2.

f. Las PCs y los portátiles también se pueden conectar a dispositivos de red mediante un cable de consola o un cable USB. Esta conexión proporciona acceso de administración. Haga clic en un cable de Consola del Tablero de Cables.

g. Haga clic en el puerto RS232 en PC\_1. Ahora el puerto debe estar resaltado en verde.

h. Pase el ratón sobre el Edge\_Router y busque el puerto de Consola. Puede hacer clic con el botón derecho en > Inspeccionar Frente para ampliar y facilitar la búsqueda del puerto.

i. Haga clic en el puerto de consola en Edge\_Router para conectar el cable de Consola. El cable ahora debería colgar entre PC\_1 y el puerto de Consola en el Edge\_Router.

#### Parte 4: Instalar un Router de Respaldo

A los modelos más nuevos de dispositivos de red se puede acceder a través de un puerto USB para la configuración de la administración. Esto es necesario porque los portátiles y los PC más recientes normalmente no incluyen un puerto RS232 para las conexiones de cables de consola.

a. Investigue el Estante. Esto incluye un inventario de dispositivos de la Sucursal de Seward que no están instalados actualmente.

b. Haga clic y arrastre Backup\_Router a un lugar vacío en el Rack.

c. Algunos dispositivos no se encienden automáticamente cuando se instalan en el Rack. Haga clic en Backup\_Router > Inspeccionar parte trasera. Busque el botón de encendido y encienda el router.

d. En el Tablero de Cables, elija un cable USB. Vuelva a la vista trasera de Backup\_Router y encuentre el puerto deconsola USB en el extremo izquierdo. Haga clic en el puerto para conectar el cable USB. Ahora el puerto debe estar resaltado en verde.

e. Conecte el otro extremo del cable USB a cualquiera de los puertos USB de la Laptop\_1. El cable no colgará como lo hicieron los cables para las conexiones a PC\_1.

#### Parte 5: Configuración de un Nombre de Host

Los administradores de red suelen asignar un nombre a los dispositivos de red. Para hacer esto, utilizará la conexión de consola al Backup\_Router.

a. Haga clic enLaptop\_1 > pestaña deDesktop > Terminal.

b. La configuración de la Terminal ya está definida con la configuración de puerto necesaria. Haga clic en Aceptar.

c. Ahora está en la línea de comandos para Backup\_Router y debería ver lo siguiente.

```
cisco ISR4331/K9 (1RU) processor with 1795999K/6147K bytes of memory.
Processor board ID FLM232010G0
3 Gigabit Ethernet interfaces
2 Serial interfaces
32768K bytes of non-volatile configuration memory.
4194304K bytes of physical memory.
3207167K bytes of flash memory at bootflash:.
0K bytes of WebUI ODM Files at webui:.

--- System Configuration Dialog ---

Would you like to enter the initial configuration dialog? [yes/no]: no
```

d. Responda no a la pregunta y luego presione ENTRAR para obtener el símbolo del sistema Router.

```
Press RETURN to get started!

<ENTER>

Router>
```

e. Introduzca los siguientes comandos para nombrar al router Edge\_Router\_Backup.

```
Router> enable
Router#configure terminal
Enter configuration commands, one per line. End with CNTL/Z.
Router (config) # hostname Edge_Router_Backup
Edge_Router_Backup (config) # end
Edge_Router_Backup#
```

Observe que el nombre de host cambió de Router a Edge\_Router\_Backup.

f. Cierre la ventana de Laptop\_1 y vuelva al Armario de Cableado de la Sucursal.

g. Observe que el nombre para mostrar de Backup\_Router no ha cambiado. Haga clic en Backup\_Router > pestaña Config. En Configuración global, observe que Packet Tracer mantiene dos nombres para el dispositivo: un nombre para mostrar y un nombre de host.

#### Parte 6: Explora el resto de la Red

Tómese un tiempo para explorar el resto de la red. Familiarícese con las representaciones de red en los modos Lógico y Físico. En el modo Físico, vaya a otras áreas, como el Centro de Datos de Wellington y el hogar de Teleworker. Las tecnologías utilizadas en estos lugares se analizan con mayor detalle en los cursos de Cisco Networking Academy. Por ahora, vea lo que puede descubrir por su cuenta. No se preocupe por romper nada. Siempre puede cerrar Packet Tracer y abrir una copia nueva para empezar a explorar de nuevo.

Escriba sus respuestas aquí.

Fin del documento
