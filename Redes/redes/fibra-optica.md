---
description: Fundamentos, tipos, ventajas y limitaciones de la fibra óptica.
icon: lightbulb
---

# Fibra Óptica

## Fibra óptica

La fibra óptica transmite información mediante pulsos de luz. Su gran capacidad y alcance la hacen adecuada para redes de operadores, edificios y centros de datos.

### Ventajas y comparación con cobre

| Aspecto          | Fibra óptica                          | Cobre                                   |
| ---------------- | ------------------------------------- | --------------------------------------- |
| Ancho de banda   | Muy alto y escalable                  | Menor y dependiente de la categoría     |
| Alcance          | Kilómetros, según óptica y enlace     | Habitualmente hasta 100 m en Ethernet   |
| Interferencias   | Inmune a EMI/RFI                      | Sensible al ruido electromagnético      |
| Seguridad física | No irradia señal eléctrica            | Puede emitir radiación electromagnética |
| Instalación      | Ligera, pero requiere especialización | Sencilla y con electrónica económica    |

Sus ventajas principales son la alta velocidad, la baja atenuación, la inmunidad electromagnética y el menor peso. Como contrapartida, requiere transceptores ópticos y técnicos especializados.

### Principio de transmisión

1. Un emisor LED o láser convierte los bits en pulsos de luz.
2. El pulso se propaga por el núcleo de vidrio o plástico.
3. Un fotodetector lo convierte de nuevo en señal eléctrica.

La guía de la luz se produce por **reflexión interna total**. El núcleo tiene un índice de refracción mayor que el revestimiento. Si la luz alcanza la interfaz con un ángulo superior al crítico, se refleja dentro del núcleo y continúa su recorrido.

### Estructura del cable

* **Núcleo:** zona central por la que viaja la luz.
* **Revestimiento:** capa que confina la luz gracias a su menor índice de refracción.
* **Recubrimiento:** protección primaria de la fibra.
* **Cubierta y elementos de refuerzo:** protegen frente a tracción, humedad y daños mecánicos.

### Tipos de fibra

| Tipo            | Característica                               | Casos recomendados                                                       |
| --------------- | -------------------------------------------- | ------------------------------------------------------------------------ |
| Monomodo (SMF)  | Núcleo estrecho. Reduce la dispersión modal. | FTTH, redes metropolitanas, enlaces de larga distancia y alta capacidad. |
| Multimodo (MMF) | Núcleo mayor. Propaga varios modos de luz.   | LAN, edificios y centros de datos con enlaces cortos.                    |

La fibra monomodo se utiliza en FTTH y enlaces de decenas de kilómetros. La multimodo suele ser rentable dentro de edificios o centros de datos. Su alcance depende del tipo de fibra, la velocidad y la óptica instalada.

### Limitaciones de implementación y mantenimiento

#### Instalación

* La obra civil, los transceptores y las fusionadoras elevan el coste inicial.
* La fibra exige respetar el radio mínimo de curvatura.
* Las terminaciones necesitan limpieza, precisión y personal cualificado.

#### Operación

* Los empalmes requieren alineación precisa y equipos específicos.
* Excavaciones, torsiones y aplastamientos pueden dañar el enlace.
* Un OTDR permite localizar pérdidas o cortes en tendidos largos.
* Los equipos finales necesitan conversión óptico-eléctrica mediante ONT, SFP u otros transceptores.
