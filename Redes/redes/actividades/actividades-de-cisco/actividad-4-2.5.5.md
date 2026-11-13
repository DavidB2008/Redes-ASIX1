# Actividad 4 (2.5.5)

Packet Tracer - Configure ajustes iniciales del interruptor

### Objetivos

Parte 1: Verifique la configuración predeterminada del switch\
Parte 2: Establezca una configuración básica del switch\
Parte 3: Configure un aviso de MOTD\
Parte 4: Guarde los archivos de configuración en la NVRAM\
Parte 5: Configure el S2

### Antecedentes/Escenario

En esta actividad, realizará tareas básicas de configuración del conmutador. Protegerá el acceso a la interfaz de línea de comandos (CLI) y a los puertos de la consola mediante contraseñas cifradas y contraseñas de texto no cifrado. También aprenderá cómo configurar mensajes para los usuarios que inician sesión en el switch. Estos banners de mensajes también se utilizan para advertir a los usuarios no autorizados que el acceso está prohibido.

Nota: En Packet Tracer, el switch Catalyst 2960 utiliza la versión 12.2 de IOS de forma predeterminada. Si es necesario, la versión IOS se puede actualizar desde un servidor de archivos en la topología Packet Tracer. El switch puede configurarse para arrancar a IOS versión 15.0, si esa versión es necesaria.

### Instrucciones

#### Parte 1: Verifique la configuración predeterminada del switch

**Paso 1: Ingrese al modo EXEC privilegiado.**

Puede acceder a todos los comandos del switch en el modo EXEC privilegiado. Sin embargo, debido a que muchos de los comandos privilegiados configuran parámetros operativos, el acceso privilegiado se debe proteger con una contraseña para evitar el uso no autorizado.

El conjunto de comandos EXEC privilegiado incluye los comandos disponibles en el modo EXEC del usuario, muchos comandos adicionales y el comando configure a través del cual se obtiene acceso a los modos de configuración.

a. Haga clic en S1 y luego en la pestaña CLI. Presione Enter.

b. Ingrese al modo EXEC privilegiado introduciendo el comando enable:

Abra la ventana de configuración para S1

```
Switch> enable
Switch#
```

Observe que la solicitud cambió para reflejar el modo EXEC privilegiado.

**Paso 2: Examine la configuración actual del switch.**

Ingrese el comando show running-config.

```
Switch# show running-config
```

Responda las siguientes preguntas:

¿Cuántas interfaces Fast Ethernet tiene el switch? Tiene 24 interfaces desde el FastEthernet 0/1 a 0/24.

¿Cuántas interfaces Gigabit Ethernet tiene el switch? Tiene 2 interfaces el GigabitEthernet 0/1 y GigabitEthernet 0/2.

¿Cuál es el rango de valores que se muestra para las líneas vty? De 0 a 15.

¿Qué comando muestra el contenido actual de la memoria de acceso aleatorio no volátil (NVRAM)? show startup-config

¿Por qué el conmutador responde con "startup-config no está presente"? Porque el switch se encuentra con la configuración predeterminada de fábrica y todavía no se ha guardado ningún archivo de configuración en la NVRAM.

#### Parte 2: Cree una configuración básica del switch

**Paso 1: Asigne un nombre a un switch.**

Para configurar los parámetros de un switch, quizá deba pasar por diversos modos de configuración. Observe cómo cambia la petición de entrada mientras navega por el switch.

```
Switch# configure terminal
Switch(config)# hostname S1
S1(config)# exit
S1#
```

**Paso 2: Proporcione acceso seguro a la línea de consola.**

Para proporcionar un acceso seguro a la línea de la consola, acceda al modo config-line y establezca la contraseña de consola en letmein.

```
S1# configure terminal
Introduzca los comandos de configuración, uno por línea. End with CNTL/Z.
S1(config)# line console 0
S1(config-line)# password letmein
S1(config-line)# login
S1(config-line)# exit
S1(config)# exit
%SYS-5-CONFIG_I: Configured from console by console
S1#
```

**Pregunta:**

¿Por qué se requiere el comando login?

Para indicarle al switch que debe solicitar la contraseña configurada cada vez que un usuario intente acceder a la línea de consola.ba sus respuestas aquí.

**Paso 3: Verifique que el acceso a la consola sea seguro.**

Salga del modo privilegiado para verificar que la contraseña del puerto de consola esté vigente.

```
S1# exit
Switch con0 is now available
Press RETURN to get started.

Verificación de acceso del usuario
Contraseña:
S1>
```

Nota:Si el switch no le solicitó una contraseña, no configuró el parámetrologin en el Paso 2.

**Paso 4: Proporcione un acceso seguro al modo privilegiado.**

Establezca la contraseña de enable en c1$c0. Esta contraseña protege el acceso al modo privilegiado.

Nota: El 0 en c1$c0 es un cero, no una O mayúscula. Esta contraseña no se calificará como correcta hasta después de que la cifre en el Paso 8.

```
S1> enable
S1# configure terminal
S1(config)# enable password c1$c0
S1(config)# exit
%SYS-5-CONFIG_I: Configured from console by console
S1#
```

**Paso 5: Verifique que el acceso al modo privilegiado sea seguro.**

a. Introduzca el comando exit nuevamente para cerrar la sesión del switch.

b. Presione ; a continuación, se le pedirá que introduzca una contraseña:

```
Verificación de acceso del usuario
Password:
```

c. La primera contraseña es la contraseña de consola que configuró para line con 0. Introduzca esta contraseña para volver al modo EXEC del usuario.

d. Introduzca el comando para acceder al modo privilegiado.

e. Introduzca la segunda contraseña que configuró para proteger el modo EXEC privilegiado. f. Verifique su configuración examinando el contenido del archivo de configuración en ejecución:

```
S1# show running-config
```

Tenga en cuenta que la consola y las contraseñas de activación están en texto plano. Esto podría suponer un riesgo para la seguridad si alguien está mirando por encima de su hombro u obtiene acceso a los archivos de configuración almacenados en una ubicación de copia de seguridad.

**Paso 6: Configure una contraseña encriptada para proporcionar un acceso seguro al modo privilegiado.**

La contraseña de enable se debe reemplazar por una nueva contraseña secreta encriptada mediante el comando enable secret. Configure la contraseña de enable secret como itsasecret.

```
S1# config t
S1(config)# enable secret itsasecret
S1(config)# exit
S1#
```

Nota: La contraseña deenable secret sobrescribe la contraseña de enable password. Si ambos están configurados en el conmutador, debe ingresar la contraseña enable secret para ingresar al modo EXEC privilegiado.

**Paso 7: Verifique si la contraseña de enable secret se agregó al archivo de configuración.**

Introduzca el comando show running-config nuevamente para verificar si la nueva contraseña de enable secret está configurada.

Nota: Puede abreviar show running-config como show run.

**Preguntas:**

¿Qué se muestra como contraseña de enable secret? Una cadena larga de caracteres cifrados mediante un algoritmo hash.

¿Por qué la contraseña de enable secret se ve diferente de lo que se configuró? Porque se almacena de forma encriptada e irreversible por motivos de seguridad.

**Paso 8: Encripte las contraseñas de consola y de enable.**

Como notó en el Paso 7, la contraseña enable secretestaba encriptada, pero las contraseñasenable y console todavía estaban en texto plano. Ahora encriptaremos estas contraseñas de texto no cifrado con el comando service password-encryption.

```
S1# config t
S1(config)# service password-encryption
S1(config)# exit
```

**Pregunta:**

Si configura más contraseñas en el switch, ¿se mostrarán como texto no cifrado o en forma cifrada en el archivo de configuración? Explique. Sí, aparecerán cifradas. Como ya activamos el comando service password-encryption, el switch se encarga de proteger automáticamente cualquier contraseña nueva que pongas de ahí en adelante para que no se lea a simple vista.

#### Parte 3: Configure un aviso de MOTD

**Paso 1: Configure un aviso de mensaje del día (MOTD).**

El conjunto de comandos de Cisco IOS incluye una característica que permite configurar los mensajes que cualquier persona puede ver cuando inicia sesión en el switch. Estos mensajes se denominan “mensajes del día” o “avisos de MOTD”. Coloque el texto del mensaje en citas o utilizando un delimitador diferente a cualquier carácter que aparece en la cadena de MOTD.

```
S1# config t
S1(config)# banner motd "This is a secure system. Authorized Access Only!
S1(config)# exit
%SYS-5-CONFIG_I: Configured from console by console
S1#
```

**Preguntas:**

¿Cuándo se muestra este aviso? Aparece en pantalla inmediatamente antes de que el usuario inicie sesión en el switch.

¿Por qué todos los switches deben tener un aviso de MOTD? Para advertir formal y legalmente a los usuarios no autorizados que el acceso está prohibido y restringido, lo cual es fundamental para políticas de seguridad.

#### Parte 4: Guarde y verifique archivos de configuración en NVRAM

**Paso 1: Verifique que la configuración sea precisa mediante el comando show run.**

Guarde el archivo de configuración. Usted ha completado la configuración básica del switch. Ahora haga una copia de seguridad del archivo de configuración en ejecución a NVRAM para garantizar que los cambios que se han realizado no se pierdan si el sistema se reinicia o se apaga.

```
S1# copy running-config startup-config
Destination filename [startup-config]?[Enter]
Building configuration...
[OK]
```

Cierre la ventana de configuración para S1

**Preguntas:**

¿Cuál es la versión abreviada más corta del comando copy running-config startup-config? La versión más corta del comando es copy r s. Escriba sus respuestas aquí.

Examine el archivo de configuración de inicio.

¿Qué comando muestra el contenido de la NVRAM? Muestra el comando show startup-config.

¿Todos los cambios realizados están grabados en el archivo? Sí, una vez ejecutado el comando de copia, la configuración actual pasa de la memoria RAM a guardarse de forma permanente en la NVRAM.

#### Parte 5: Configurar S2

Ha completado la configuración en S1. Ahora configurará el S2. Si no recuerda los comandos, consulte las partes 1 a 4 para obtener ayuda.

Configure el S2 con los siguientes parámetros:

Abra la ventana de configuración para S2

a. Device name: S2

b. Proteja el acceso a la consola con la contraseña letmein.

c. Configure enable password comoc1$c0 y una contraseña enable secret como itsasecret.

d. Configure un mensaje apropiado para aquellos que inician sesión en el switch.

e. Encripte todas las contraseñas de texto no cifrado.

f. Asegúrese de que la configuración sea correcta.

g. Guarde el archivo de configuración para evitar perderlo si el switch se apaga.

h. Cierre la ventana de configuración para S2
