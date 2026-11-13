# Actividad 3 (1.5.7)

Packet Tracer: Representación de la red

### Objetivos

El modelo de red en esta actividad incluye muchas de las tecnologías que llegará a dominar en sus estudios en CCNA y representa una versión simplificada de la forma en que podría verse una red de pequeña o mediana empresa. Siéntase libre de explorar la red por usted mismo. Cuando esté listo, siga estos pasos y responda las preguntas.

Nota: No es importante que comprenda todo lo que vea y haga en esta actividad. Siéntase libre de explorar la red por usted mismo. Si desea hacerlo de manera más sistemática, siga estos pasos. Responda las preguntas lo mejor que pueda.

### Instrucciones

#### Paso 1: Identifique los componentes comunes de una red según se los representa en Packet Tracer.

La barra de herramientas de íconos en la esquina inferior izquierda tiene diferentes categorías de componentes de red. Debería ver las categorías que corresponden a los dispositivos intermediarios, los terminales y los medios. La categoría Conexiones (su ícono es un rayo) representa los medios de red que admite Packet Tracer. También hay una categoría llamada Terminales y dos categorías específicas de Packet Tracer: Dispositivos personalizados y Conexión multiusuario.

**Preguntas:**

Enumere las categorías de los dispositivos intermediarios.

Routers, Switches, Dispositivos Inalámbricos, Hubs y Emulación de WAN.

Sin ingresar en la nube de Internet o de intranet, ¿cuántos íconos de la topología representan dispositivos de terminales (solo una conexión conduce a ellos)? Son 15 dispositivos.

Sin contar las dos nubes, ¿cuántos íconos de la topología representan dispositivos intermediarios (varias conexiones conducen a ellos)? Son 11 dispositivos.

¿Cuántos terminales no son PC de escritorio? Son 8 dispositivos.

¿Cuántos tipos diferentes de conexiones de medios se utilizan en esta topología de red?

Son 4 tipos de conexiones de medios:

Cobre Ethernet: Para conectar los equipos locales a los switches.

Serie: Para los enlaces WAN entre routers.

Coaxial: Para conectar el módem a la red exterior.

Inalámbrica: Para los dispositivos que se conectan por aire sin cables.

#### Paso 2: Explique la finalidad de los dispositivos.

a. En Packet Tracer, solo el dispositivo Server-PT puede funcionar como servidor. Las PC de escritorio o portátiles no pueden funcionar como servidores. Según lo que estudió hasta ahora, explique el modelo cliente-servidor.

Los servidores son dispositivos que ofrecen servicios o recursos como por ejemplo: páginas web, correo,archivos, DNS, impresión. Los clientes son dispositivos que solicitan esos servicios para el usuario. El cliente inicia la petición, el servidor la atiende y responde, y un servidor puede atender a muchos clientes a la vez

b. Enumere, al menos, dos funciones de los dispositivos intermediarios.

1.Conectar los dispositivos finales a la red.

2.Interconectar redes distintas y reenviar datos por la mejor ruta.

Escriba sus respuestas aquí.

c. Enumere, al menos, dos criterios para elegir un tipo de medio de red.

1.Distancia máxima que soporta la señal.

2.Cantidad de datos y velocidad requeridas

3.Costo del medio y de su instalación.

#### Paso 3: Compare las redes LAN y WAN.

a. Explique la diferencia entre una LAN y una WAN, y dé ejemplos de cada una.

**LAN:** Conecta dispositivos en un área geográfica pequeña y limitada, como una oficina, un hogar, un edificio o un campus universitario. Ofrece altas velocidades de transferencia y es de propiedad privada.

Ejemplo: La red de ordenadores e impresoras dentro de una oficina o tu red de casa conectada al router Wi-Fi.

**WAN:** Conecta redes y dispositivos a través de grandes distancias geográficas, abriendo ciudades, países o incluso a escala global. Suele requerir el uso de servicios de operadores de telecomunicaciones.

Ejemplo: Internet o una red corporativa que conecta las oficinas centrales de una empresa en Madrid con sus sucursales en el extranjero.

b. ¿Cuántas WAN ve en la red de Packet Tracer? Se ven 2 WAN la WAN de internet y la WAN de intranet que es la que conecta los sitios remotos de la empresa.

c. ¿Cuántas LAN ve? Se ven 3 LAN que son la red del Home Office, la red central y la red de Branch.

d. En esta red de Packet Tracer, Internet está simplificada en gran medida y no representa ni la estructura ni la forma de Internet propiamente dicha. Describa Internet brevemente.

Es una red global de redes interconectadas, que no pertenece a nadie. Está formada por millones de redes públicas y privadas de ISP, empresas, gobiernos y universidades, unidas por proveedores de distintos niveles (Tier 1, 2 y 3) que intercambian tráfico. En Packet Tracer se simplifica con una nube y unos pocos routers.

e. ¿Cuáles son algunas de las formas más comunes que utiliza un usuario doméstico para conectarse a Internet? Las formas más comunes en que un usuario doméstico se conecta a Internet son la fibra óptica (FTTH) por su gran velocidad y estabilidad mediante pulsos de luz, el cable coaxial (HFC) que aprovecha las redes de televisión, el DSL a través de las líneas telefónicas tradicionales, el internet móvil (4G/5G) mediante routers celulares y el internet satelital para zonas rurales o de difícil acceso.

f. ¿Cuáles son algunos de los métodos más comunes que utilizan las empresas para conectarse a Internet en su área? Los métodos más comunes que utilizan las empresas para conectarse a Internet en su área son las líneas arrendadas dedicadas (para conexiones exclusivas y de velocidad garantizada entre sedes), la fibra óptica corporativa (Ethernet WAN / FTTO) para soportar un alto volumen de tráfico y los enlaces satelitales o inalámbricos de alta capacidad, que se emplean como respaldo o para conectar ubicaciones remotas.

### Pregunta de desafío

Ahora que tuvo la oportunidad de explorar la red representada en esta actividad de Packet Tracer, es posible que haya adquirido algunas habilidades que quiera poner en práctica o tal vez desee tener la oportunidad de analizar esta red en mayor detalle. Teniendo en cuenta que la mayor parte de lo que ve y experimenta en Packet Tracer supera su nivel de habilidad en este momento, los siguientes son algunos desafíos que tal vez quiera probar. No se preocupe si no puede completarlos todos. Muy pronto se convertirá en un usuario y diseñador de redes experto en Packet Tracer.

* Agregue un dispositivo final a la topología y conéctelo a una de las LAN con una conexión de medios. ¿Qué otra cosa necesita este dispositivo para enviar datos a otros usuarios finales? ¿Puede proporcionar la información? ¿Hay alguna manera de verificar que conectó correctamente el dispositivo?

Un dispositivo final nuevo necesita dirección IP, máscara de subred y puerta de enlace predeterminada (manual o por DHCP). Puedes darle esa información. Se verifica con ping a la puerta de enlace y a otros equipos.

* Agregue un nuevo dispositivo intermediario a una de las redes y conéctelo a uno de las LAN o WAN con una conexión de medios. ¿Qué otra cosa necesita este dispositivo para funcionar como intermediario de otros dispositivos en la red?

Un dispositivo intermedio nuevo necesita configuración: nombre, interfaces con direcciones y activadas ( no shutdown ), y, si es un router, rutas o un protocolo de enrutamiento.

* Abra una nueva instancia de Packet Tracer. Cree una nueva red con, al menos, dos redes LAN conectadas mediante una WAN. Conecte todos los dispositivos. Investigue la actividad de Packet Tracer original para ver qué más necesita hacer para que la nueva red esté en condiciones de funcionamiento. Registre sus comentarios y guarde el archivo de Packet Tracer. Tal vez desee volver a acceder a la red cuando domine algunas habilidades más.

En una red propia con dos LAN unidas por una WAN faltarán, normalmente, direccionamiento en todos los equipos y rutas entre los routers.
