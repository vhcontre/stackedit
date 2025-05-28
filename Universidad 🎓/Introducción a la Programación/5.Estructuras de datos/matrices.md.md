### 🧩 Enunciado: Análisis de una Matriz Cuadrada

> Desarrollar un programa que trabaje con una **matriz de 3 filas por 3 columnas** (matriz cuadrada).  
> El programa debe realizar las siguientes acciones:

1.  Solicitar al usuario que ingrese un número entero para **cada posición de la matriz**.
    
2.  Mostrar la **matriz completa** con todos los valores ingresados.
    
3.  Imprimir únicamente los valores de la **diagonal principal** de la matriz (de izquierda a derecha, desde la esquina superior izquierda).
    
4.  Imprimir únicamente los valores de la **diagonal secundaria** o **contra-diagonal** (de derecha a izquierda, desde la esquina superior derecha).
    

> 💡 _Sugerencia:_ Para identificar las diagonales, se pueden usar las condiciones `i == j` (diagonal principal) y `i + j == tamaño - 1` (diagonal secundaria), siendo `i` la fila y `j` la columna.

----------

¡Perfecto! Vamos a revisar y **documentar paso a paso** el código Python que compartiste. Además, te explico si hay algo que pueda mejorarse:

----------

### ✅ CÓDIGO REVISADO Y DOCUMENTADO

```python
import numpy as np  # Se importa la biblioteca numpy para trabajar con matrices

# Se definen constantes para el tamaño de la matriz
FILAS = 3
COLUMNAS = 3

# Se crea una matriz de 3x3 inicializada con unos, de tipo entero
matrix = np.ones([FILAS, COLUMNAS], dtype=int)

# 🔢 Carga de datos en la matriz
for i in range(FILAS):
    for j in range(COLUMNAS):
        matrix[i][j] = int(input(f"Ingrese el valor para la coordenada [{i},{j}]: "))

# 📋 Muestra la matriz completa
print("MATRIZ COMPLETA")
for i in range(FILAS):
    for j in range(COLUMNAS):
        print(matrix[i][j], end=" ")
    print()  # Salto de línea por fila

# 🔷 Diagonal principal: posiciones donde fila == columna

print("\nDIAGONAL PRINCIPAL (solo elementos)")
for i in range(FILAS):
    for j in range(COLUMNAS):
        if i == j:
            print(matrix[i][j], end=" ")
        else:
            print("-", end=" ")
    print()

# 🔶 Contra diagonal: posiciones donde fila + columna == FILAS - 1
print("\nCONTRA DIAGONAL (solo elementos)")
for i in range(FILAS):
    for j in range(COLUMNAS):
        if i + j == FILAS - 1:
            print(matrix[i][j], end=" ")
        else:
            print("-", end=" ")
    print()

```

----------



**Versión del programa sin utilizar `numpy`**, usando solo estructuras básicas de Python.

----------

### 🧾 Enunciado breve del ejercicio

> Se desea cargar una matriz de 3x3 con valores ingresados por el usuario, mostrar la matriz completa, luego su **diagonal principal** y su **contra-diagonal**.

----------

### ✅ VERSIÓN SIN `numpy` Y COMENTADA

```python
# Definimos las dimensiones de la matriz
FILAS = 3
COLUMNAS = 3

# Creamos la matriz como una lista de listas vacía
matriz = []

# 🟡 Carga de datos en la matriz
for i in range(FILAS):
    fila = []  # Lista temporal para construir cada fila
    for j in range(COLUMNAS):
        numero = int(input(f"Ingrese el valor para la posición [{i},{j}]: "))
        fila.append(numero)  # Agregamos el número a la fila
    matriz.append(fila)  # Agregamos la fila completa a la matriz

# 🟢 Mostrar la matriz completa
print("\n📋 MATRIZ COMPLETA")
for i in range(FILAS):
    for j in range(COLUMNAS):
        print(matriz[i][j], end=" ")
    print()

# 🔵 Mostrar la diagonal principal (donde fila == columna)
print("\n🔷 DIAGONAL PRINCIPAL")
for i in range(FILAS):
    for j in range(COLUMNAS):
        if i == j:
            print(matriz[i][j], end=" ")
        else:
            print("-", end=" ")  # Marcamos con guiones los elementos no diagonales
    print()

# 🔴 Mostrar la contra-diagonal (donde fila + columna == FILAS - 1)
print("\n🔶 CONTRA DIAGONAL")
for i in range(FILAS):
    for j in range(COLUMNAS):
        if i + j == FILAS - 1:
            print(matriz[i][j], end=" ")
        else:
            print("-", end=" ")  # Marcamos con guiones los elementos no diagonales
    print()

```

----------

### 📌 Explicación de conceptos importantes

Parte del código

Explicación

`matriz = []`

Se inicia una lista vacía que contendrá filas.

`fila = []`

En cada iteración se construye una fila como una lista de números.

`if i == j:`

Detecta los elementos en la **diagonal principal**.

`if i + j == FILAS - 1:`

Detecta los elementos en la **contra-diagonal**.

`print("-", end=" ")`

Se usa para mantener la forma de la matriz, rellenando con guiones los elementos que no se deben mostrar.

----------

¿Querés que también lo prepare en PSeInt para prácticas de pseudocódigo?

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTIyNjc0MTQyMV19
-->