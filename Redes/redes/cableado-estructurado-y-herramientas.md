---
description: Arquitectura del cableado estructurado y herramientas de diseño de redes.
icon: sitemap
---

# Cableado Estructurado y Herramientas

## Cableado estructurado y herramientas

### Cableado troncal

El cableado troncal es la columna vertebral de una instalación. Interconecta la sala de equipamiento, los armarios de telecomunicaciones y la entrada de servicios. Transporta el tráfico agregado entre plantas, zonas o edificios.

| Característica            | Troncal de cobre              | Troncal de fibra óptica                  |
| ------------------------- | ----------------------------- | ---------------------------------------- |
| Alcance Ethernet habitual | Hasta 100 m                   | Desde cientos de metros hasta kilómetros |
| Interferencias            | Puede sufrir EMI/RFI          | Inmune a EMI/RFI                         |
| Capacidad                 | Adecuada en distancias cortas | Alta capacidad y escalabilidad           |
| Tamaño y peso             | Mayor en mazos de cables      | Menor peso y diámetro                    |
| Coste inicial             | Electrónica más económica     | Transceptores y terminación más costosos |

Se recomienda cobre para armarios muy cercanos y presupuestos limitados. La fibra es la elección adecuada entre plantas, edificios, tramos superiores a 90–100 m o zonas con ruido eléctrico.

### Estructura del cableado

#### Sala central de equipamiento

Aloja servidores, routers, switches troncales y equipos que gestionan el tráfico principal del edificio.

#### Armario de telecomunicaciones

Distribuye la conectividad por planta o zona. Incluye paneles de parcheo, switches de acceso y la terminación del cableado horizontal.

#### Cableado vertical

También llamado _backbone_. Interconecta la sala central con los armarios de telecomunicaciones. Habitualmente emplea fibra por capacidad y distancia.

#### Áreas de trabajo

Son los espacios donde se conectan los dispositivos de usuario. Incluyen rosetas, latiguillos y equipos como ordenadores, teléfonos o impresoras.

#### Toma del edificio

Es el punto de entrada de los servicios externos. Conecta la red del operador con la infraestructura interna del edificio.

### Herramientas de diseño de redes

| Herramienta         | Características                                                     | Licencia                                         |
| ------------------- | ------------------------------------------------------------------- | ------------------------------------------------ |
| Cisco Packet Tracer | Simula dispositivos Cisco y permite configurar redes virtuales.     | Gratuita con cuenta de Cisco Networking Academy. |
| GNS3                | Emula sistemas operativos de red reales. Aporta mayor flexibilidad. | Gratuita y de código abierto.                    |
| Lucidchart          | Crea diagramas y topologías colaborativas desde la nube.            | Freemium.                                        |

Para esta práctica se selecciona **Cisco Packet Tracer**. Permite representar el aula y las redes domésticas con equipos virtuales. También permite probar conectividad y configuraciones básicas. El diagrama de Packet Tracer se entrega fuera de este manual, según la indicación de la práctica.
