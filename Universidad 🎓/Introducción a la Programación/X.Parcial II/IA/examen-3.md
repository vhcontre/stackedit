Diseñar evaluaciones que integren el uso de IA pero que **obliguen a demostrar comprensión** es una forma moderna y efectiva de enseñar y evaluar. Te paso una serie de **ejemplos concretos**, divididos por tipo de habilidad que querés evaluar.

---

## 🧠 1. **Comprensión del código generado (lectura y análisis)**

> ⚙️ *Contexto:* Se les permite usar IA para generar código. Luego, deben interpretar lo que hace.

### 📝 Pregunta:

> La IA te generó el siguiente código para buscar un número en una lista:
>
> ```python
> def buscar_numero(lista, numero):
>     for i, n in enumerate(lista):
>         if n == numero:
>             return i
>     return -1
> ```
>
> **Preguntas:**
>
> 1. ¿Qué hace esta función? Explicalo en tus propias palabras.
> 2. ¿Qué devuelve si el número no está en la lista?
> 3. ¿Cómo podrías modificarla para que devuelva todos los índices donde aparece el número?

---

## 🔧 2. **Modificación sobre código dado por IA**

> ⚙️ *Contexto:* Parten de una base generada por IA y deben ajustarla.

### 📝 Tarea:

> La IA te ayudó a crear esta función para calcular el promedio de una lista:
>
> ```python
> def promedio(lista):
>     return sum(lista) / len(lista)
> ```
>
> **Desafío:** Modificá la función para que:
>
> * Devuelva 0 si la lista está vacía (evitando división por cero).
> * Ignore los valores negativos de la lista.

---

## 🔍 3. **Debugging (detección de errores)**

> ⚙️ *Contexto:* Se les da código con errores sutiles, como a veces puede generar la IA.

### 📝 Pregunta:

> Analizá el siguiente código que la IA te generó para contar palabras:
>
> ```python
> def contar_palabras(texto):
>     palabras = texto.split(" ")
>     return len(palabras)
> ```
>
> 1. ¿Hay algún problema con este código si el texto contiene múltiples espacios seguidos o saltos de línea?
> 2. Proponé una corrección.

---

## 🔄 4. **Refactorización y mejora**

> ⚙️ *Contexto:* Usan IA para crear algo funcional, pero deben mejorar su estilo o rendimiento.

### 📝 Tarea:

> La IA generó esta función:
>
> ```python
> def es_par(num):
>     if num % 2 == 0:
>         return True
>     else:
>         return False
> ```
>
> Refactorizala para que sea más concisa sin cambiar su funcionalidad.

---

## 📈 5. **Interpretación de resultados o salida**

> ⚙️ *Contexto:* La IA les da código que imprime o devuelve resultados.

### 📝 Pregunta:

> Este código fue generado con IA:
>
> ```python
> def saludar(nombre):
>     return f"Hola {nombre.upper()}"
>
> print(saludar("ana"))
> ```
>
> **Respuestas:**
>
> 1. ¿Qué imprime?
> 2. ¿Qué pasaría si en vez de `"ana"` se pasa un número?
> 3. Modificá la función para que detecte ese caso y devuelva un mensaje de error.

---

## 🧪 6. **Evaluación de código generado por IA**

> ⚙️ *Contexto:* Se les pide revisar código de IA como si fueran code reviewers.

### 📝 Actividad:

> La IA generó la siguiente función para calcular factorial:
>
> ```python
> def factorial(n):
>     if n == 0:
>         return 1
>     else:
>         return n * factorial(n - 1)
> ```
>
> **Tareas:**
>
> 1. ¿Qué hace esta función? ¿Está correcta?
> 2. ¿Qué problema tendría si se llama con un número negativo?
> 3. Proponé una mejora para manejar esos casos.

---

## 📚 7. **Documentar o explicar código generado**

> ⚙️ *Contexto:* Se fomenta la comunicación clara.

### 📝 Tarea:

> Usá la IA para generar una función que ordene una lista de tuplas por el segundo elemento.
> Luego, documentá esa función usando comentarios o docstrings, explicando:
>
> * Qué hace
> * Qué parámetros recibe
> * Qué retorna

---

## 🧩 8. **Comparar soluciones (IA vs. humana)**

> ⚙️ *Contexto:* Que piensen críticamente.

### 📝 Actividad:

> Escribí tu propia versión de una función que cuente vocales en un texto.
> Luego, pedile a la IA una versión alternativa.
> Compará ambas soluciones:
>
> * ¿Cuál es más eficiente?
> * ¿Cuál es más clara?
> * ¿Qué aprendiste del enfoque de la IA?

---

## 🧠 Sugerencia adicional: rúbrica de evaluación

Podés usar criterios como:

| Criterio                         | Excelente (10) | Aceptable (7) | Insuficiente (<7) |
| -------------------------------- | -------------- | ------------- | ----------------- |
| Explicación clara y comprensible | ✅              | ⚠️            | ❌                 |
| Identifica errores lógicos       | ✅              | ⚠️            | ❌                 |
| Refactoriza correctamente        | ✅              | ⚠️            | ❌                 |
| Usa IA con criterio              | ✅              | ⚠️            | ❌                 |
| Argumenta decisiones             | ✅              | ⚠️            | ❌                 |

---

>Perfecto. Aquí tienes varios ejemplos de preguntas y tareas pensadas específicamente para evaluar comprensión profunda, aunque los estudiantes usen inteligencia artificial como apoyo. Estas propuestas están diseñadas para:

-   Fomentar el pensamiento crítico.
    
-   Detectar si el estudiante realmente entiende el código.
    
-   Impedir que la simple copia con IA sea suficiente para aprobar.
    

----------

### 🔍 **Tipo 1: "Completar con criterio"**

**Ejemplo 1:**

> Se te da la siguiente función incompleta. Completala para que devuelva el promedio de una lista de números, ignorando los valores negativos:

```python
def promedio_sin_negativos(lista):
    # Tu código aquí
    pass

```

**Preguntas adicionales:**

-   ¿Qué sucede si la lista está vacía?
    
-   ¿Por qué es importante validar los negativos explícitamente?
    

----------

### 🧠 **Tipo 2: "Detectar y explicar errores"**

**Ejemplo 2:**

> Analiza el siguiente código y explica qué hace, qué errores tiene y cómo lo mejorarías:

```python
def buscar(lista, valor):
    for i in range(len(lista)):
        if lista[i] == valor:
            return i
        else:
            return -1

```

**Lo que se evalúa:**

-   Comprensión del flujo de control.
    
-   Capacidad para razonar sobre comportamiento esperado vs real.
    

----------

### 🧩 **Tipo 3: "Reescribir según una consigna"**

**Ejemplo 3:**

> Tienes el siguiente programa que imprime los números del 1 al 10. Reescríbelo usando comprensión de listas y una función `imprimir_lista(lista)` para mostrar los resultados.

```python
for i in range(1, 11):
    print(i)

```

**Lo que se evalúa:**

-   Capacidad de transformación semántica de código.
    
-   Uso correcto de funciones y estructuras más avanzadas.
    

----------

### 💡 **Tipo 4: "Justificar el uso de IA"**

**Ejemplo 4:**

> Puedes usar ChatGPT o GitHub Copilot para ayudarte a resolver este problema. Luego responde:

1.  ¿Qué pediste a la IA?
    
2.  ¿Qué sugerencias te dio?
    
3.  ¿Cómo supiste que eran correctas o incorrectas?
    
4.  ¿Cambiaste algo de lo que propuso? ¿Por qué?
    

**Lo que se evalúa:**

-   Uso consciente y reflexivo de herramientas de IA.
    
-   Desarrollo de juicio técnico.
    

----------

### 🧪 **Tipo 5: "Pruebas y predicción de resultados"**

**Ejemplo 5:**

> Observa el siguiente código y predice qué imprimirá. Justifica tu respuesta.

```python
def mystery(a, b):
    a.append(b)
    return a

lista1 = [1, 2]
lista2 = mystery(lista1, 3)
lista3 = mystery(lista1, 4)
print(lista1)

```

**Lo que se evalúa:**

-   Comprensión de listas mutables y referencias.
    

----------

### 🔧 **Tipo 6: "Revisión de código generado por IA"**

**Ejemplo 6:**

> A continuación se muestra una solución generada por IA para contar cuántas veces aparece una palabra en un texto. Revisa el código y mejora su eficiencia o legibilidad:

```python
def contar(palabra, texto):
    return texto.split().count(palabra)

```

**Lo que se evalúa:**

-   Razonamiento crítico.
    
-   Capacidad de refactorización.
    

----------
Excelente decisión. Aquí te dejo **las respuestas esperadas** o razonadas para cada uno de los retos anteriores, con explicaciones breves que podrías usar como guía para corregir o discutir con los estudiantes.

----------

### 🔍 **Tipo 1: Completar con criterio**

**Ejemplo 1:**

```python
def promedio_sin_negativos(lista):
    positivos = [x for x in lista if x >= 0]
    if len(positivos) == 0:
        return 0  # o None, según cómo lo quieras manejar
    return sum(positivos) / len(positivos)

```

**Respuesta esperada a las preguntas:**

-   Si la lista está vacía o todos los elementos son negativos, la función debe devolver `0` o `None` para evitar dividir por cero.
    
-   Validar los negativos evita que afecten el cálculo del promedio con valores que no queremos considerar.
    

----------

### 🧠 **Tipo 2: Detectar y explicar errores**

**Código:**

```python
def buscar(lista, valor):
    for i in range(len(lista)):
        if lista[i] == valor:
            return i
        else:
            return -1

```

**Errores esperados:**

-   El `return -1` está dentro del `for`, por lo tanto la función retorna después de la primera comparación, sin revisar el resto de los elementos.
    

**Corrección sugerida:**

```python
def buscar(lista, valor):
    for i in range(len(lista)):
        if lista[i] == valor:
            return i
    return -1

```

----------

### 🧩 **Tipo 3: Reescribir según una consigna**

**Versión con comprensión de listas y función:**

```python
def imprimir_lista(lista):
    for elem in lista:
        print(elem)

imprimir_lista([i for i in range(1, 11)])

```

**Objetivo:** Que el estudiante entienda que puede separar la lógica de generación de la lógica de impresión.

----------

### 💡 **Tipo 4: Justificar el uso de IA**

**Respuestas esperadas (ejemplo):**

1.  _¿Qué pediste a la IA?_  
    “Le pedí cómo calcular un promedio sin contar números negativos en Python.”
    
2.  _¿Qué sugerencias te dio?_  
    “Me mostró una lista por comprensión con un `if`, luego usó `sum()` y `len()`.”
    
3.  _¿Cómo supiste que eran correctas o incorrectas?_  
    “Probé con una lista de ejemplo y vi que funcionaba; también revisé si cubría el caso de lista vacía.”
    
4.  _¿Cambiaste algo de lo que propuso? ¿Por qué?_  
    “Sí, agregué una condición para devolver `0` si no hay números válidos.”
    

----------

### 🧪 **Tipo 5: Pruebas y predicción de resultados**

**Código:**

```python
def mystery(a, b):
    a.append(b)
    return a

lista1 = [1, 2]
lista2 = mystery(lista1, 3)
lista3 = mystery(lista1, 4)
print(lista1)

```

**Resultado esperado:**

```
[1, 2, 3, 4]

```

**Explicación:**  
La lista `a` se pasa por referencia, así que cuando se modifica `a` dentro de la función, se modifica también fuera de ella. Es un caso clásico de aliasing y mutabilidad.

----------

### 🔧 **Tipo 6: Revisión de código generado por IA**

**Código original:**

```python
def contar(palabra, texto):
    return texto.split().count(palabra)

```

**Potenciales mejoras y observaciones:**

-   Este método es sensible a mayúsculas/minúsculas y signos de puntuación.
    
-   Se puede mejorar con normalización:
    

```python
import string

def contar(palabra, texto):
    texto = texto.lower().translate(str.maketrans('', '', string.punctuation))
    palabras = texto.split()
    return palabras.count(palabra.lower())

```

**Respuesta esperada:**  
Que el estudiante detecte esas debilidades (como `"gato"` ≠ `"Gato"` o `"gato."`) y las corrija con alguna técnica de limpieza de texto.



<!--stackedit_data:
eyJoaXN0b3J5IjpbMjAzMzgwMTgxNF19
-->