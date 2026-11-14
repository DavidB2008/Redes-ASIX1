---
description: Fundamentos de la comunicación en red y las reglas que definen los protocolos.
---

# 📡 Comunicación y protocolos de red

> **Objetivo:** comprender qué necesita una red para que dos equipos puedan comunicarse correctamente y qué reglas definen los protocolos.

## 1. ¿Qué es un protocolo de red?

Cuando dos equipos intercambian información necesitan seguir unas **reglas comunes**. Un **protocolo de red** define esas reglas para que el emisor y el receptor puedan interpretar los datos de la misma forma.

Un protocolo puede definir, entre otros aspectos:

* **Codificación:** cómo se representa la información mediante bits.
* **Formato y encapsulación:** cómo se estructuran los datos y qué información de control se añade.
* **Tamaño del mensaje:** límites mínimos o máximos cuando corresponda.
* **Temporización:** cuándo se envían los datos y cuánto tiempo puede esperarse una respuesta.
* **Métodos de entrega:** comunicación entre un origen y uno o varios destinos.
* **Control y validación:** mecanismos para detectar errores, confirmar recepciones o iniciar y finalizar comunicaciones.

## 2. Ejemplo práctico

Imagina que un equipo envía un mensaje a otro:

1. La información se codifica en una forma que ambos sistemas puedan interpretar.
2. Se organiza según el protocolo utilizado.
3. Se encapsula con información de control.
4. La red transporta los datos hasta el destino.
5. El receptor valida la información y la entrega a la aplicación correspondiente.

Dependiendo del protocolo, pueden existir mecanismos como:

* **Acuse de recibo:** confirma que determinada información ha sido recibida.
* **Comprobación de integridad:** ayuda a detectar si la información se ha alterado durante el transporte.
* **Establecimiento y cierre:** permite iniciar y finalizar una comunicación de forma organizada.

## 3. Comunicación orientada y no orientada a conexión

### Orientada a conexión

Antes de intercambiar información se establece una comunicación lógica entre los extremos.

**Ejemplo habitual:** TCP.

Características:

* Establecimiento previo de la conexión.
* Confirmaciones y mecanismos de recuperación.
* Entrega ordenada cuando el protocolo lo proporciona.
* Mayor control, con una sobrecarga superior.

### No orientada a conexión

Los datos se envían sin establecer previamente una conexión formal entre los extremos.

**Ejemplo habitual:** UDP.

Características:

* Menor sobrecarga.
* No garantiza por sí mismo entrega ni orden.
* Puede ser adecuado para aplicaciones sensibles a la latencia.

## 4. Pila de protocolos

El conjunto de protocolos utilizados por una arquitectura se denomina **pila de protocolos** o _protocol stack_.

Los modelos por capas permiten dividir la comunicación en funciones independientes. Cada capa:

* Utiliza servicios de la capa inferior.
* Ofrece servicios a la capa superior.
* Se comunica conceptualmente con su capa equivalente en el sistema remoto mediante protocolos.

Esta organización facilita la **interoperabilidad**, el desarrollo de tecnologías y la resolución de problemas.

## 5. Conceptos clave para estudiar

| Concepto           | Idea principal                                        |
| ------------------ | ----------------------------------------------------- |
| Protocolo          | Conjunto de reglas para comunicar sistemas            |
| Encapsulación      | Añadir información de control al bajar por la pila    |
| Desencapsulación   | Eliminar e interpretar esa información al recibirla   |
| Pila de protocolos | Conjunto organizado de protocolos de una arquitectura |
| Latencia           | Tiempo que tarda la información en llegar             |
| Interoperabilidad  | Capacidad de sistemas diferentes para comunicarse     |

> **Idea para el trabajo:** conocer los protocolos permite entender qué ocurre realmente cuando se diagnostica una incidencia. No basta con saber que «no funciona Internet»: hay que determinar en qué parte de la comunicación está el problema.
