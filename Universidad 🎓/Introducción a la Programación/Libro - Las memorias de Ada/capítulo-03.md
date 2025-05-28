### Capítulo 3: Toma de Decisiones y Repeticiones

Después de aprender a hablar el lenguaje de las computadoras, la joven programadora sabía que lo siguiente en su viaje era lograr que su programa tomara decisiones y pudiera realizar tareas de forma repetitiva. Había llegado a un punto donde ya no solo quería que su código hiciera operaciones, sino que también respondiera a las circunstancias, como un ser consciente.

¿Cómo podía un programa saber qué hacer dependiendo de la situación? ¿Cómo podría hacer que una computadora repitiera ciertas acciones una y otra vez, de manera eficiente? Estas preguntas la intrigaban, así que decidió continuar con su aventura en el mundo de la programación.

#### Estructuras de Control: La Toma de Decisiones

La primera herramienta que encontró fue el concepto de **estructuras de control**. Estas estructuras eran fundamentales para tomar decisiones dentro de un programa. Le permitían decirle a la computadora: "Si esto sucede, entonces haz esto; pero si no, haz lo otro".

El primer tipo de estructura de control que encontró fue el **if** (si), una instrucción que evaluaba una condición y, dependiendo de si esa condición era verdadera o falsa, ejecutaba una parte del código u otra.

**Ejemplo de estructura `if`**:

```python
edad = 12

if edad >= 18:
    print("Eres mayor de edad.")
else:
    print("Eres menor de edad.")
```

En este caso, el programa verificaba si la edad era mayor o igual a 18. Si la condición era verdadera, mostraba el mensaje “Eres mayor de edad”, pero si no lo era, mostraba el mensaje “Eres menor de edad”. Es como una bifurcación en un camino: una decisión que cambia el curso del programa.

> **Reflexión útil**: Imagina que estás frente a dos caminos en un bosque. Si tienes 18 años o más, eliges uno; si no, tomas el otro. Así de simple es el **if**: una bifurcación en la que el programa toma decisiones según las condiciones que le des.

#### El `if` y el `else`: Tomando Opciones

Ada se dio cuenta rápidamente de que las condiciones eran esenciales para manejar distintos escenarios dentro de un programa. Sin embargo, algunas veces las cosas no eran tan simples como un "sí" o un "no". Por eso, descubrió el **`else`**: una instrucción que servía para especificar qué hacer cuando la condición no se cumplía.

Con el uso combinado del **if** y **else**, Ada podía gestionar una mayor variedad de decisiones, como si estuviera creando su propio conjunto de reglas para un juego.

**Ejemplo con `else`**:

```python
edad = 16

if edad >= 18:
    print("Eres adulto.")
else:
    print("Eres un adolescente.")
```

Ahora, el programa estaba preparado para dos posibles caminos: uno para las personas adultas y otro para los adolescentes. La estructura **if-else** proporcionaba una manera muy clara de gestionar decisiones en función de los datos disponibles.

#### La Función `elif`: Más Opciones para Decidir

Pero Ada no se conformaba solo con "sí" o "no". Quería más opciones. Entonces, descubrió el **`elif`**, que permitía agregar condiciones adicionales para hacer más decisiones. Con **`elif`**, el programa podía verificar varias condiciones y ejecutar diferentes bloques de código según cuál de ellas fuera verdadera.

**Ejemplo con `elif`**:

```python
edad = 12

if edad >= 18:
    print("Eres adulto.")
elif edad >= 13:
    print("Eres un adolescente.")
else:
    print("Eres un niño.")
```

Con esta estructura, su programa ahora tenía tres posibles respuestas, dependiendo de la edad. Usar **`elif`** le permitía crear decisiones más matizadas y detalladas, adaptándose a diferentes situaciones.

#### Repetir Acciones: El Poder de los Bucles

A medida que avanzaba, Ada entendió que muchas veces necesitaría que su programa repitiera ciertas acciones una y otra vez. Por ejemplo, si estaba creando un juego, podría querer que un personaje saltara continuamente o que una animación se repitiera durante un tiempo. Para ello, aprendió sobre los **bucles**, unas estructuras que permiten repetir código varias veces sin tener que escribirlo una y otra vez.

El primer tipo de bucle que conoció fue el **bucle `for`**, que se usa cuando sabemos cuántas veces queremos repetir algo.

**Ejemplo de bucle `for`**:

```python
for i in range(5):
    print("¡Hola, mundo!")
```

Este programa imprimirá "¡Hola, mundo!" cinco veces. El bucle **`for`** es muy útil cuando tienes un número determinado de veces para repetir una acción, como contar del 1 al 10 o recorrer una lista de elementos.

#### Bucle `while`: Repetir Mientras se Cumpla una Condición

El otro tipo de bucle que Ada descubrió fue el **bucle `while`**, que permite repetir una acción mientras se cumpla una condición determinada. Este tipo de bucle se utiliza cuando no sabemos cuántas veces necesitamos repetir algo, sino que depende de una situación que pueda cambiar con el tiempo.

**Ejemplo de bucle `while`**:

```python
contador = 0

while contador < 5:
    print("Contando...")
    contador += 1
```

En este caso, el programa seguirá imprimiendo "Contando..." hasta que el valor de **`contador`** llegue a 5. Los bucles **`while`** son útiles cuando la cantidad de repeticiones depende de algo que puede cambiar durante el proceso, como la cantidad de veces que un usuario elige jugar un juego.

> **Nota útil**: Es importante tener cuidado con los bucles **`while`**, porque si la condición nunca se vuelve falsa, el programa podría entrar en un bucle infinito, repitiendo una acción sin fin.

#### Resumen del Capítulo

En este capítulo, Ada aprendió cómo hacer que su programa pudiera:

- **Tomar decisiones**: Usando **`if`**, **`else`** y **`elif`** para elegir diferentes caminos en función de las condiciones.
- **Repetir acciones**: Usando **bucles `for`** y **`while`** para ejecutar ciertas acciones varias veces, con control sobre el número de repeticiones.

> **Reflexión final**: Ada entendió que estas herramientas le permitían hacer que su programa fuera más inteligente, flexible y dinámico. Ahora, sus programas podían tomar decisiones complejas y adaptarse a diferentes situaciones, ¡como un verdadero ser pensante!

---

Con esta nueva habilidad, nuestra joven programadora estaba lista para los siguientes retos: aprender a organizar y estructurar mejor su código, dándole más orden y claridad. El viaje continuaba, y en el siguiente capítulo, descubriría cómo hacerlo a través de **funciones**. ¡El mundo de la programación era un campo sin fin de posibilidades!

<!--stackedit_data:
eyJoaXN0b3J5IjpbNzMzNjczNjQxXX0=
-->