# Actividad 2 (2.9.1)

Packet Tracer — Configuración básica del switch y del dispositivo final

### Tabla de asignación de direcciones

| Dispositivo | Interfaz | Dirección IP | Máscara de subred |
| ----------- | -------- | ------------ | ----------------- |
| ASw-1       | VLAN 1   | 10.10.10.100 | 255.255.255.0     |
| ASw-2       | VLAN 1   | 10.10.10.150 | 255.255.255.0     |
| User-01     | NIC      | 10.10.10.4   | 255.255.255.0     |
| User-02     | NIC      | 10.10.10.5   | 255.255.255.0     |

### Objetivos

* Configure los nombres de host y las direcciones IP en dos switches con sistema operativo Internetwork (IOS) de Cisco mediante la interfaz de línea de comandos (CLI).
* Utilice comandos de Cisco IOS para especificar o limitar el acceso a las configuraciones de dispositivos.
* Utilice comandos de IOS para guardar la configuración en ejecución.
* Configure dos dispositivos host con direcciones IP.
* Verifique la conectividad entre dos terminales PC.

### Escenario

Como técnico de LAN contratado recientemente, el administrador de red le solicitó que demuestre su habilidad para configurar una LAN pequeña. Sus tareas incluyen la configuración de parámetros iniciales en dos switches mediante Cisco IOS y la configuración de parámetros de dirección IP en dispositivos host para proporcionar conectividad completa. Debe utilizar dos switches y dos hosts/PC en una red conectada por cable y con alimentación.

### Instrucciones

Configure los dispositivos para que cumplan los requisitos que se indican a continuación.

### Requisitos

* Utilice una conexión de consola para acceder a cada switch.
* Nombre los switches ASw-1 y ASw-2.
* Utilice la contraseña xAw6k para todas las líneas.
* Utilice la contraseña secreta enable secret es : 6EBUp.
* Encripte todas las contraseñas de texto no cifrado. Aplicado mediante service password-encryption.
* Configure un aviso apropiado para el mensaje del día (MOTD). # Acceso autorizado #
* Configure el direccionamiento para todos los dispositivos de acuerdo con la tabla de direccionamiento. Aplicado a las interfaces VLAN 1 de los switches y a la interfaz NIC de los PC de acuerdo con la tabla.
* Guarde las configuraciones.

Configuración guardada en la memoria NVRAM mediante el comando write / copy running-config startup-config.

* Verifique la conectividad entre todos los dispositivos.

Nota: Hag clic en Check Results para ver su progreso. Haga clic en Reset Activity para generar un nuevo conjunto de requisitos. Si hace clic en esto antes de completar la actividad, se perderán todas las configuraciones.
