## 📘 Guía Sencilla de Electrónica para Robótica (Arduino)

**Versión “sin miedo a los cables”** 😄

### 1. Conceptos básicos (sin enredos)

* **Voltaje (V)** → Es la “fuerza” que empuja a los electrones. En Arduino trabajamos mayormente con **5V** (a veces 3.3V en sensores delicados).
* **Corriente (A)** → Es la “cantidad” de electrones que circulan. Más corriente = más potencia, pero cuidado con exceder lo que el circuito soporta.
* **Resistencia (Ω)** → Es lo que frena el paso de la corriente, evitando que algo se queme.
* **Ley de Ohm** → V = I × R (no te preocupes, la vamos a aplicar de forma muy sencilla).

💡 Ejemplo: Si tu LED funciona con 2V y la placa le da 5V, necesitas una **resistencia** para que no explote (sí, puede pasar).

---

### 2. Protoboard: tu mesa de trabajo

* Es la placa blanca llena de agujeritos.
* Las **líneas largas de los bordes** son rieles de alimentación: rojo (+) y azul/negro (–).
* El **centro** tiene columnas de 5 agujeros conectados entre sí.
* No hay conexión entre las dos mitades centrales, así que si querés pasar corriente de un lado a otro, hay que puentear.

---

### 3. Resistencias y código de colores

* Sirven para limitar la corriente.
* Cada resistencia tiene **anillos de colores** que indican su valor.
* Tranquilo: vamos a usar una tabla y no a memorizar todo.
* Lo importante: antes de conectar un LED, poné una resistencia en serie (generalmente 220Ω o 330Ω).

---

### 4. Uso seguro de sensores y motores

* **Sensores**: siempre revisar si trabajan a 3.3V o 5V antes de conectarlos.
* **Motores DC**: consumen más corriente, así que no se alimentan directamente de los pines de Arduino; usamos un **driver** (L298N o similar).
* **Servomotores**: se controlan desde un pin, pero la alimentación es directa a 5V y GND, cuidando no pasarse de consumo.
* **Motores paso a paso**: necesitan driver especial (ej. ULN2003).

---

### 5. Buenas prácticas desde el inicio

* Usar siempre **cables cortos** para evitar enredos.
* Conectar **primero GND** antes de encender.
* Probar los circuitos en el protoboard antes de soldar.
* Tener a mano un **multímetro** para medir voltaje y continuidad.
* Documentar el circuito (foto o dibujo) para repetirlo después.

---

💖 Con esto ya vamos a poder encarar la **Semana 1** con confianza:

* Día 1: repasamos esta guía mientras montamos un LED con resistencia.
* Día 2: hacemos el primer proyecto práctico (ej. un LED intermitente) y medimos con multímetro.


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE1Mjk0MjU4ODNdfQ==
-->