## 🧠 Ejercicio didáctico de matrices en Python

Aprender a:

-   Crear matrices (listas de listas)
    
-   Recorrer matrices con bucles
    
-   Sumar elementos
    
-   Imprimir matrices de forma ordenada
    

----------

## 🧪 Ejercicio: Suma de dos matrices

### 🎯 Enunciado

Crea dos matrices de tamaño 3x3. Pide al usuario que ingrese los valores de ambas matrices. Luego, crea una **tercera matriz** que sea la suma elemento a elemento de las dos anteriores. Finalmente, muestra todas las matrices.

----------

## 🧩 Paso a paso

### 1️⃣ Crear una función para pedir una matriz al usuario

```python
def pedir_matriz(filas, columnas):
    matriz = []
    print(f"Ingresando valores para una matriz de {filas}x{columnas}:")
    for i in range(filas):
        fila = []
        for j in range(columnas):
            valor = int(input(f"Ingrese el valor para la posición [{i}][{j}]: "))
            fila.append(valor)
        matriz.append(fila)
    return matriz

```

✅ Esta función crea una matriz pidiendo al usuario los valores uno por uno.

----------

### 2️⃣ Crear una función para sumar dos matrices

```python
def sumar_matrices(m1, m2):
    filas = len(m1)
    columnas = len(m1[0])
    resultado = []
    for i in range(filas):
        fila = []
        for j in range(columnas):
            suma = m1[i][j] + m2[i][j]
            fila.append(suma)
        resultado.append(fila)
    return resultado

```

✅ Esta función recorre cada elemento y suma los valores correspondientes.

----------

### 3️⃣ Crear una función para mostrar una matriz

```python
def mostrar_matriz(matriz, nombre="Matriz"):
    print(f"\n{nombre}:")
    for fila in matriz:
        print(fila)

```

✅ Imprime la matriz con cada fila como una lista.

----------

### 4️⃣ Programa principal

```python
# Tamaño de la matriz
filas = 3
columnas = 3

# Pedir matrices al usuario
matriz1 = pedir_matriz(filas, columnas)
matriz2 = pedir_matriz(filas, columnas)

# Sumar las matrices
resultado = sumar_matrices(matriz1, matriz2)

# Mostrar resultados
mostrar_matriz(matriz1, "Matriz 1")
mostrar_matriz(matriz2, "Matriz 2")
mostrar_matriz(resultado, "Matriz Resultado (Suma)")

```

----------

## 🎓 Conceptos clave para repasar 

-   ¿Qué es una **lista de listas** en Python?
    
-   ¿Cómo funcionan los **bucles anidados**?
    
-   ¿Qué hace `len(matriz)` y `len(matriz[0])`?
    
-   ¿Por qué es útil usar funciones para organizar el código?
    



## ✅ 1. ¿Qué es una **lista de listas** en Python?

Una **matriz** en Python se puede representar como una **lista de listas**. Cada "fila" es una lista, y todas las filas están contenidas dentro de una lista principal.

### 🧪 Ejercicio 1: Crear una matriz manualmente

```python
# Creamos una matriz de 2 filas y 3 columnas manualmente
matriz = [
    [1, 2, 3],
    [4, 5, 6]
]

print("Matriz:")
for fila in matriz:
    print(fila)
```

### 🧠 Explicación

* `matriz[0]` accede a la primera fila → `[1, 2, 3]`
* `matriz[1][2]` accede al tercer elemento de la segunda fila → `6`

### 🎯 Mini-desafío

* Accede al valor `5` y cambia su valor por `10`.
* Agrega una nueva fila `[7, 8, 9]` a la matriz.

---

## ✅ 2. ¿Cómo funcionan los **bucles anidados**?

Los bucles anidados son necesarios para **recorrer** todos los elementos de una matriz (fila por fila, columna por columna).

### 🧪 Ejercicio 2: Recorrer una matriz e imprimir los elementos

```python
matriz = [
    [1, 2, 3],
    [4, 5, 6]
]

print("Elementos de la matriz:")
for i in range(len(matriz)):  # Recorre las filas
    for j in range(len(matriz[i])):  # Recorre las columnas
        print(f"Elemento en [{i}][{j}]: {matriz[i][j]}")
```

### 🧠 Explicación

* `len(matriz)` da la cantidad de filas.
* `len(matriz[i])` da la cantidad de columnas de la fila `i`.

### 🎯 Mini-desafío

* Multiplica todos los elementos de la matriz por 2 y guarda el resultado en otra matriz.

---

## ✅ 3. ¿Qué hacen `len(matriz)` y `len(matriz[0])`?

Estas funciones ayudan a saber el **tamaño de la matriz**:

* `len(matriz)` → número de filas.
* `len(matriz[0])` → número de columnas (asumiendo que todas las filas tienen la misma longitud).

### 🧪 Ejercicio 3: Mostrar tamaño de una matriz

```python
matriz = [
    [10, 20],
    [30, 40],
    [50, 60]
]

filas = len(matriz)
columnas = len(matriz[0])

print(f"La matriz tiene {filas} filas y {columnas} columnas.")
```

### 🎯 Mini-desafío

* Haz que el usuario cree una matriz de cualquier tamaño (pidiendo número de filas y columnas).
* Muestra el tamaño usando `len`.

---

## ✅ 4. ¿Por qué es útil usar **funciones** para organizar el código?

Las funciones permiten **reutilizar código**, hacerlo más legible y mantenerlo organizado.

### 🧪 Ejercicio 4: Crear una función para imprimir cualquier matriz

```python
def imprimir_matriz(matriz, nombre="Matriz"):
    print(f"\n{nombre}:")
    for fila in matriz:
        print(fila)

# Prueba la función
matriz = [
    [7, 8],
    [9, 10]
]

imprimir_matriz(matriz, "Matriz de prueba")
```

### 🎯 Mini-desafío

* Crea una función que reciba una matriz y devuelva la **suma total de todos sus elementos**.
* Luego, reutilízala con varias matrices distintas.

---

## 📚 Resumen para reforzar con los estudiantes

| Concepto          | Qué hace                       | Ejemplo                                     |
| ----------------- | ------------------------------ | ------------------------------------------- |
| `lista de listas` | Representa matrices            | `[[1, 2], [3, 4]]`                          |
| `for` anidado     | Recorre filas y columnas       | `for i in range(...): for j in range(...):` |
| `len(matriz)`     | Cuenta filas                   | `len([[1,2],[3,4]]) → 2`                    |
| `len(matriz[0])`  | Cuenta columnas                | `len([[1,2],[3,4]][0]) → 2`                 |
| Funciones         | Organiza y reutiliza el código | `def sumar(m): ...`                         |

---


# 📝 **Actividad Práctica: Operaciones con Matrices en Python**

## 🎯 Objetivo de la actividad

El estudiante aplicará:

* Creación y manejo de matrices como listas de listas.
* Uso de bucles anidados para recorrer matrices.
* Uso de funciones para modularizar el código.
* Entrada/salida de datos desde el teclado.
* Operaciones aritméticas entre matrices.

---

## 🧩 Parte 1: Crear una matriz desde teclado

### ✅ Instrucciones

1. Pide al usuario que ingrese el número de **filas** y **columnas**.
2. Luego, solicita los valores para llenar la matriz.

### 📌 Código base sugerido

```python
def pedir_matriz(filas, columnas):
    matriz = []
    for i in range(filas):
        fila = []
        for j in range(columnas):
            valor = int(input(f"Ingrese el valor para la posición [{i}][{j}]: "))
            fila.append(valor)
        matriz.append(fila)
    return matriz
```

---

## 🔁 Parte 2: Imprimir la matriz

### ✅ Instrucciones

Crea una función que reciba una matriz y la imprima ordenadamente.

```python
def imprimir_matriz(matriz, nombre="Matriz"):
    print(f"\n{name}:")
    for fila in matriz:
        print(fila)
```

---

## ➕ Parte 3: Sumar dos matrices

### ✅ Instrucciones

1. Crea **dos matrices** del mismo tamaño (usando la función anterior).
2. Crea una tercera matriz que sea la suma **elemento por elemento** de las dos anteriores.

```python
def sumar_matrices(m1, m2):
    filas = len(m1)
    columnas = len(m1[0])
    resultado = []
    for i in range(filas):
        fila = []
        for j in range(columnas):
            suma = m1[i][j] + m2[i][j]
            fila.append(suma)
        resultado.append(fila)
    return resultado
```

---

## 🧮 Parte 4: Calcular la suma total de los elementos de una matriz

### ✅ Instrucciones

Crea una función que recorra la matriz y sume todos sus valores.

```python
def suma_total(matriz):
    total = 0
    for fila in matriz:
        for valor in fila:
            total += valor
    return total
```

---

## ✅ Parte 5: Programa principal (Integración)

Integra todo lo anterior en un único programa:

```python
# Paso 1: Ingreso del tamaño
filas = int(input("Ingrese el número de filas: "))
columnas = int(input("Ingrese el número de columnas: "))

# Paso 2: Ingreso de las dos matrices
print("\n--- Matriz A ---")
matrizA = pedir_matriz(filas, columnas)

print("\n--- Matriz B ---")
matrizB = pedir_matriz(filas, columnas)

# Paso 3: Suma de matrices
resultado = sumar_matrices(matrizA, matrizB)

# Paso 4: Mostrar las matrices
imprimir_matriz(matrizA, "Matriz A")
imprimir_matriz(matrizB, "Matriz B")
imprimir_matriz(resultado, "Matriz A + B")

# Paso 5: Suma total
total = suma_total(resultado)
print(f"\nLa suma total de todos los elementos de la matriz resultado es: {total}")
```

---

## 🎓 Criterios de evaluación

| Criterio                                                   | Puntaje    |
| ---------------------------------------------------------- | ---------- |
| Uso correcto de listas de listas para representar matrices | 2 pts      |
| Uso adecuado de bucles anidados para recorrer matrices     | 2 pts      |
| Modularización del código con funciones                    | 2 pts      |
| Correcto ingreso y visualización de datos                  | 2 pts      |
| Cálculo correcto de la suma de matrices y de la suma total | 2 pts      |
| **Total**                                                  | **10 pts** |

---

## 🏁 Extensión opcional (avanzados)

* Multiplica dos matrices si el número de columnas de la primera coincide con el número de filas de la segunda.
* Implementa una función que verifique si una matriz es **simétrica** (igual a su transpuesta).





# ✅ Solución completa: Actividad Práctica de Matrices en Python



## 🧩 Parte 1: Crear una matriz desde teclado

```python
def pedir_matriz(filas, columnas):
    matriz = []
    for i in range(filas):
        fila = []
        for j in range(columnas):
            valor = int(input(f"Ingrese el valor para la posición [{i}][{j}]: "))
            fila.append(valor)
        matriz.append(fila)
    return matriz
```

📌 **Ejemplo de uso**:

```python
matrizA = pedir_matriz(2, 2)
# Si el usuario ingresa: 1, 2, 3, 4
# matrizA será: [[1, 2], [3, 4]]
```



## 🧩 Crear una matriz desde teclado completa.

```python
def crear_matriz(filas, columnas):
    matriz = []
    for i in range(filas):
        fila = []
        for j in range(columnas):
            valor = int(input(f"Ingrese el valor para la posición [{i}][{j}]: "))
            fila.append(valor)
        matriz.append(fila)
    return matriz

matrix = crear_matriz(3, 3)
print ("\n")

print("\n📋 Matriz")
print("-" * (columnas * 5))  

for i in range(filas):
    print("[", end="") 
    for j in range(columnas):
        print(f"{matrix[i][j]:>3}", end=" ")
    print("]")

print("-" * (columnas * 5))  
```


---

## 🔁 Parte 2: Imprimir la matriz

```python
def imprimir_matriz(matriz, nombre="Matriz"):
    print(f"\n{nombre}:")
    for fila in matriz:
        print(fila)
```

📌 **Ejemplo de uso**:

```python
imprimir_matriz([[1, 2], [3, 4]], "Matriz A")
```

🖨️ Salida esperada:

```
Matriz A:
[1, 2]
[3, 4]
```

---

## ➕ Parte 3: Sumar dos matrices

```python
def sumar_matrices(m1, m2):
    filas = len(m1)
    columnas = len(m1[0])
    resultado = []
    for i in range(filas):
        fila = []
        for j in range(columnas):
            suma = m1[i][j] + m2[i][j]
            fila.append(suma)
        resultado.append(fila)
    return resultado
```

📌 **Ejemplo de uso**:

```python
A = [[1, 2], [3, 4]]
B = [[5, 6], [7, 8]]
C = sumar_matrices(A, B)
imprimir_matriz(C, "Suma de A + B")
```

🖨️ Salida esperada:

```
Suma de A + B:
[6, 8]
[10, 12]
```

---

## 🧮 Parte 4: Calcular la suma total de los elementos de una matriz

```python
def suma_total(matriz):
    total = 0
    for fila in matriz:
        for valor in fila:
            total += valor
    return total
```

📌 **Ejemplo de uso**:

```python
matriz = [[1, 2], [3, 4]]
print("Suma total:", suma_total(matriz))
```

🖨️ Salida esperada:

```
Suma total: 10
```

---

## ✅ Parte 5: Programa principal (integración completa)

```python
def pedir_matriz(filas, columnas):
    matriz = []
    for i in range(filas):
        fila = []
        for j in range(columnas):
            valor = int(input(f"Ingrese el valor para la posición [{i}][{j}]: "))
            fila.append(valor)
        matriz.append(fila)
    return matriz

def imprimir_matriz(matriz, nombre="Matriz"):
    print(f"\n{nombre}:")
    for fila in matriz:
        print(fila)

def sumar_matrices(m1, m2):
    filas = len(m1)
    columnas = len(m1[0])
    resultado = []
    for i in range(filas):
        fila = []
        for j in range(columnas):
            suma = m1[i][j] + m2[i][j]
            fila.append(suma)
        resultado.append(fila)
    return resultado

def suma_total(matriz):
    total = 0
    for fila in matriz:
        for valor in fila:
            total += valor
    return total

# ---------- Programa Principal ----------

# Paso 1: Tamaño de la matriz
filas = int(input("Ingrese el número de filas: "))
columnas = int(input("Ingrese el número de columnas: "))

# Paso 2: Ingreso de las matrices
print("\n--- Matriz A ---")
matrizA = pedir_matriz(filas, columnas)

print("\n--- Matriz B ---")
matrizB = pedir_matriz(filas, columnas)

# Paso 3: Sumar matrices
matrizResultado = sumar_matrices(matrizA, matrizB)

# Paso 4: Mostrar matrices
imprimir_matriz(matrizA, "Matriz A")
imprimir_matriz(matrizB, "Matriz B")
imprimir_matriz(matrizResultado, "Matriz A + B")

# Paso 5: Suma total
total = suma_total(matrizResultado)
print(f"\nLa suma total de los elementos de la matriz resultado es: {total}")
```

---

## ✅ Salida esperada (ejemplo de ejecución)

```
Ingrese el número de filas: 2
Ingrese el número de columnas: 2

--- Matriz A ---
Ingrese el valor para la posición [0][0]: 1
Ingrese el valor para la posición [0][1]: 2
Ingrese el valor para la posición [1][0]: 3
Ingrese el valor para la posición [1][1]: 4

--- Matriz B ---
Ingrese el valor para la posición [0][0]: 5
Ingrese el valor para la posición [0][1]: 6
Ingrese el valor para la posición [1][0]: 7
Ingrese el valor para la posición [1][1]: 8

Matriz A:
[1, 2]
[3, 4]

Matriz B:
[5, 6]
[7, 8]

Matriz A + B:
[6, 8]
[10, 12]

La suma total de los elementos de la matriz resultado es: 36
```



<!--stackedit_data:
eyJoaXN0b3J5IjpbLTExMjExMDU3NjZdfQ==
-->