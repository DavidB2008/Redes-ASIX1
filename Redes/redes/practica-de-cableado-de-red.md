---
description: Análisis del cableado de aula para el módulo 0370 de ASIX.
icon: network-wired
---

# Práctica de Cableado de Red

## Práctica de cableado de red

**Módulo:** 0370 · **Ciclo formativo:** ASIX · **Alumnos:** Eulalia y David

Este manual reúne el análisis realizado en pareja. Las instalaciones domésticas se documentan de forma individual.

### Análisis del aula

El aula utiliza cable de par trenzado **UTP**. Este cable dispone de cuatro pares trenzados y no incorpora apantallamiento. El trenzado reduce la diafonía y las interferencias. Su flexibilidad y coste lo hacen adecuado para aulas y oficinas.

El tendido observado incluye un cable de comunicaciones Cat 6 UTP de **23 AWG**, con conductores de unos **0,57 mm**. Su cubierta **LSZH** limita la emisión de humo y gases halogenados. El cable verde corresponde a la instalación eléctrica. Ambos tendidos deben mantenerse separados según la normativa aplicable.

#### Normativa

TIA/EIA-568-B.2-1 define requisitos de transmisión para cableado balanceado de categoría 6. La familia ANSI/TIA-568 establece requisitos generales para cableado estructurado, sus componentes y su verificación.

La conformidad final exige comprobar el etiquetado del cable, la instalación, la separación de energía y los resultados de certificación. La inscripción del cable, por sí sola, no certifica toda la instalación.

#### UTP, FTP y STP

| Tipo      | Protección                    | Uso recomendado                                  |
| --------- | ----------------------------- | ------------------------------------------------ |
| UTP       | Sin pantalla                  | Aulas y oficinas con bajo ruido eléctrico.       |
| FTP/F-UTP | Pantalla global de lámina     | Oficinas o comercios con interferencia moderada. |
| STP/S-FTP | Pantalla global y/o por pares | Industria o zonas próximas a motores y potencia. |

Los cables apantallados requieren conectores, paneles y puesta a tierra adecuados. Sin esa continuidad, el apantallamiento pierde eficacia.

#### Cable directo y cruzado

Un cable **directo** mantiene el mismo esquema en ambos extremos. Históricamente conectaba equipos de distinto tipo, como PC a switch. Un cable **cruzado** intercambia los pares de transmisión y recepción. Se usaba entre equipos equivalentes.

La mayoría de interfaces actuales soportan **Auto-MDI/MDIX**. Esta función detecta los pares y permite usar habitualmente un cable directo en ambos casos.

### Categorías de par trenzado

| Categoría | Frecuencia nominal | Velocidad habitual máxima                       |
| --------- | -----------------: | ----------------------------------------------- |
| Cat 3     |             16 MHz | 10 Mb/s                                         |
| Cat 5     |            100 MHz | 100 Mb/s                                        |
| Cat 5e    |            100 MHz | 1 Gb/s                                          |
| Cat 6     |            250 MHz | 1 Gb/s a 100 m; 10 Gb/s hasta 55 m              |
| Cat 6A    |            500 MHz | 10 Gb/s a 100 m                                 |
| Cat 7     |            600 MHz | 10 Gb/s, según sistema y conector               |
| Cat 8     |          2.000 MHz | 25/40 Gb/s en enlaces cortos de centro de datos |

La velocidad efectiva depende de la categoría, la longitud, los conectores y la certificación del enlace.

### Los ocho pines de RJ45

En 10BASE-T y 100BASE-TX se utilizan dos pares. En 1000BASE-T se usan los cuatro pares simultáneamente y de forma bidireccional.

| Pines | Par T568B                | Función en 10/100BASE-TX              |
| ----- | ------------------------ | ------------------------------------- |
| 1–2   | Blanco-naranja / naranja | Transmisión (TX+ / TX−)               |
| 3–6   | Blanco-verde / verde     | Recepción (RX+ / RX−)                 |
| 4–5   | Azul / blanco-azul       | Sin datos en 10/100; datos en Gigabit |
| 7–8   | Blanco-marrón / marrón   | Sin datos en 10/100; datos en Gigabit |

PoE puede alimentar equipos mediante pares de datos o pares dedicados, según el estándar empleado.

### Normas TIA-568A, TIA-568B y TIA-568C

| Norma     | Orden inicial de pines    | Uso y alcance                                                                   |
| --------- | ------------------------- | ------------------------------------------------------------------------------- |
| T568A     | Blanco-verde, verde       | Esquema de terminación reconocido por TIA.                                      |
| T568B     | Blanco-naranja, naranja   | Esquema muy extendido en instalaciones existentes.                              |
| TIA-568-C | No define un tercer orden | Revisión de la familia de normas. Integra requisitos del cableado estructurado. |

T568A y T568B ofrecen el mismo rendimiento. Un enlace directo usa el mismo esquema en ambos extremos. Un cable cruzado combina T568A en un extremo y T568B en el otro.
