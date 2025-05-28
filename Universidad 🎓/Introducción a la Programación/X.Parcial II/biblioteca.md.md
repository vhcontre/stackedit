### 📚 **Sistema de Gestión de Libros**

#### 📝 Enunciado:

Se debe desarrollar un programa en Python que permita gestionar el inventario de libros de una biblioteca. Cada libro será representado como una lista, y todos los libros se almacenarán en una lista principal (matriz).

----------

### 📦 **Estructura del Libro:**

Cada libro contiene los siguientes campos:

1.  **Código** (str): Identificador único del libro.
    
2.  **Título** (str): Título del libro.
    
3.  **Autor** (str): Autor del libro.
    
4.  **Año de publicación** (int): Año en el que fue publicado.
    
5.  **Estado** (str): Puede ser:
    
    -   `"disponible"`: el libro está en estantería.
        
    -   `"prestado"`: el libro fue retirado por un lector.
        
    -   `"reservado"`: el libro fue apartado, pero no retirado aún.
        

----------

### 🛡️ **Reglas de negocio y validaciones:**

-   El **código** debe ser único (como el ID).
    
-   El **año de publicación** debe ser un número positivo entre 1500 y el año actual.
    
-   El libro se puede **eliminar** solo si su estado es `"disponible"`.
    
-   El estado debe ser uno de los permitidos.
    
-   Al agregar un libro, el estado debe ser `"disponible"`.
    

----------

### 🛠️ **Funciones requeridas:**

1.  `codigo_duplicado(codigo)`  
    Verifica si un código ya existe.
    
2.  `buscar_por_codigo(codigo)`  
    Retorna el índice del libro con ese código, o `-1` si no existe.
    
3.  `agregar_libro()`  
    Registra un nuevo libro en la biblioteca.
    
4.  `modificar_estado()`  
    Permite cambiar el estado de un libro.
    
5.  `eliminar_libro()`  
    Elimina un libro si está disponible.
    
6.  `listar_libros()`  
    Muestra todos los libros registrados.
    
7.  `mostrar_estadisticas()`  
    Muestra:
    
    -   Total de libros
        
    -   Libros por estado
        
8.  `menu()`  
    Presenta las opciones al usuario para navegar por las funciones.
    


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTExNzYzMTU5NTddfQ==
-->