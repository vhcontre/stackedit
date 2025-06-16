### 🎮 **Sistema de Gestión de Jugadores**

#### 📝 Enunciado:

Se debe desarrollar un programa en Python que permita gestionar jugadores de un videojuego. Cada jugador se representará como una lista de datos y todos los jugadores se almacenarán en una lista principal (una "matriz").

----------

### 🎯 **Estructura del Jugador:**

Cada jugador debe tener la siguiente información:

1.  **Nombre** (str) – Nombre del jugador.
    
2.  **Usuario** (str) – Nickname único en la plataforma.
    
3.  **ID** (str) – Identificador único.
    
4.  **Nivel** (int) – Nivel del jugador (empieza en 1).
    
5.  **Estado** (str) – Puede ser:
    
    -   `"activo"`: cuando el jugador está en uso regular.
        
    -   `"suspendido"`: cuando se le detectó mal comportamiento.
        
    -   `"baneado"`: cuando fue expulsado definitivamente.
        

----------

### 📌 **Reglas de negocio y validaciones**:

-   El **ID** debe ser único.
    
-   Un jugador se **puede eliminar** solo si está en **nivel 1** y su estado es `"activo"`.
    
-   El nivel debe ser un número entero positivo.
    
-   El estado solo puede ser `"activo"`, `"suspendido"` o `"baneado"`.
    
-   Al agregar un jugador, su nivel debe iniciar en `1` y su estado en `"activo"`.
    

----------

### 🛠️ **Funciones requeridas:**

1.  `id_duplicado(id)`  
    Verifica si un ID ya está registrado.
    
2.  `buscar_por_id(id)`  
    Retorna el índice del jugador con ese ID, o `-1` si no existe.
    
3.  `agregar_jugador()`  
    Permite registrar un nuevo jugador con los datos iniciales.
    
4.  `modificar_estado_nivel()`  
    Permite actualizar el **estado** y el **nivel** de un jugador. Ambos deben validarse.
    
5.  `eliminar_jugador()`  
    Elimina un jugador solo si cumple las condiciones permitidas.
    
6.  `listar_jugadores()`  
    Muestra el listado completo con todos los datos de los jugadores registrados.
    
7.  `mostrar_estadisticas()`  
    Muestra:
    
    -   Total de jugadores
        
    -   Cantidad de jugadores por estado (`activo`, `suspendido`, `baneado`)
        
8.  `menu()`  
    Muestra el menú interactivo para acceder a las funcionalidades anteriores.
    


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTMzMzg4NzA4MSwxMTc3ODU1NjE4XX0=
-->