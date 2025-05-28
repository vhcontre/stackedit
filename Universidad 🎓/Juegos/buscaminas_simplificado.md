**Nivel 1: Buscaminas simplificado (5x5)**.

### 🎯 Objetivo del juego:

Que el jugador encuentre todas las celdas libres (sin minas) de una matriz 5x5, evitando las minas. Idealmente, hay entre 3 y 5 minas colocadas aleatoriamente.

----------

### 🧩 Mecánica del juego:

1.  Se genera una matriz 5x5 oculta con algunas minas (`'M'`) y espacios seguros (`' '`).
    
2.  El jugador elige coordenadas (fila y columna) para "revelar".
    
3.  Si toca una mina, pierde.
    
4.  Si revela una celda segura, puede seguir jugando.
    
5.  El juego termina cuando:
    
    -   El jugador pisa una mina → pierde.
        
    -   El jugador encuentra todas las celdas seguras → gana.
        

----------

### 💡 Reglas simplificadas:

-   No hay conteo de minas vecinas (se puede agregar como mejora en N2).
    
-   Solo se revela una celda por turno.
    
-   Se muestra un tablero con las casillas reveladas y ocultas (`'X'`).
    

----------

### 🧪 Ejemplo visual del progreso del tablero:

```
  0 1 2 3 4
0 X X X X X
1 X X X X X
2 X X X X X
3 X X X X X
4 X X X X X

Ingrese fila: 2
Ingrese columna: 3

  0 1 2 3 4
0 X X X X X
1 X X X X X
2 X X X   X
3 X X X X X
4 X X X X X

```

----------

### ✅ Posible implementación base

¡Excelente decisión! Aquí te dejo el código completo en Python de un **Buscaminas simplificado 5x5**, ideal para tus estudiantes de primer año. El código está bien comentado, estructurado y listo para usar o modificar con ellos.

----------

### 🧨 Buscaminas Simplificado (5x5) — Versión básica para estudiantes

```python
import random

# Dimensiones del tablero
TAMANO = 5
MINAS = 5

# Tablero oculto con minas y celdas seguras
tablero = [[' ' for _ in range(TAMANO)] for _ in range(TAMANO)]

# Tablero que ve el jugador
tablero_visible = [['X' for _ in range(TAMANO)] for _ in range(TAMANO)]

# Generar coordenadas únicas para las minas
minas_colocadas = 0
while minas_colocadas < MINAS:
    fila = random.randint(0, TAMANO - 1)
    col = random.randint(0, TAMANO - 1)
    if tablero[fila][col] != 'M':
        tablero[fila][col] = 'M'
        minas_colocadas += 1

# Contador de casillas seguras descubiertas
casillas_descubiertas = 0
total_seguras = TAMANO * TAMANO - MINAS

# Función para imprimir el tablero visible
def imprimir_tablero():
    print("\n   " + " ".join(str(i) for i in range(TAMANO)))
    for i in range(TAMANO):
        print(f"{i}  " + " ".join(tablero_visible[i]))
    print()

# Juego principal
def jugar():
    global casillas_descubiertas
    print("¡Bienvenido al Buscaminas 5x5! Evita las minas.")
    while True:
        imprimir_tablero()

        try:
            fila = int(input("Ingrese fila (0-4): "))
            col = int(input("Ingrese columna (0-4): "))
        except ValueError:
            print("Por favor, ingrese números válidos.")
            continue

        if not (0 <= fila < TAMANO and 0 <= col < TAMANO):
            print("Coordenadas fuera de rango. Intente nuevamente.")
            continue

        if tablero_visible[fila][col] != 'X':
            print("Ya descubriste esa casilla. Intenta otra.")
            continue

        if tablero[fila][col] == 'M':
            tablero_visible[fila][col] = 'M'
            imprimir_tablero()
            print("💥 ¡PISASTE UNA MINA! Fin del juego.")
            break
        else:
            tablero_visible[fila][col] = ' '
            casillas_descubiertas += 1

            if casillas_descubiertas == total_seguras:
                imprimir_tablero()
                print("🎉 ¡FELICITACIONES! Descubriste todas las casillas seguras.")
                break

# Ejecutar el juego
if __name__ == "__main__":
    jugar()

```

----------

### ✅ Características pedagógicas del código

-   **Estructura clara:** Separa lógica de generación, visualización y juego.
    
-   **Evita temas complejos:** No hay recursividad ni conteo de minas vecinas todavía.
    
-   **Ideal para practicar:**
    
    -   Listas bidimensionales.
        
    -   Bucles.
        
    -   Control de flujo (`if`, `while`).
        
    -   Entrada/salida.
        

----------

### 🧠 Sugerencias para actividades con estudiantes

-   Mostrar el tablero completo al final y comparar con lo jugado.
    
-   Agregar contador de minas alrededor (versión N2).
    
-   Permitir marcar una casilla como posible mina.
    
-   Cambiar el tamaño de la matriz dinámicamente.
    

¿Querés que después armemos juntos una versión más avanzada (con números alrededor de las minas como en el Buscaminas real)?
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjE3NjgxOTUzXX0=
-->