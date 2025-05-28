## **Unidad 1: Introducción a Python**

1. **Hola Mundo**:
   ```python
   print("Hola, mundo")
   ```

2. **Suma de dos números**:
   ```python
   num1 = float(input("Ingrese el primer número: "))
   num2 = float(input("Ingrese el segundo número: "))
   suma = num1 + num2
   print("La suma es:", suma)
   ```

3. **Área de un Círculo**:
   ```python
   import math
   radio = float(input("Ingrese el radio: "))
   area = math.pi * (radio ** 2)
   print("El área del círculo es:", area)
   ```

4. **Conversión de Temperatura**:
   ```python
   celsius = float(input("Ingrese la temperatura en Celsius: "))
   fahrenheit = (celsius * 9/5) + 32
   print("La temperatura en Fahrenheit es:", fahrenheit)
   ```

5. **Generar un Número Aleatorio**:
   ```python
   import random
   numero_aleatorio = random.randint(1, 100)
   print("Número aleatorio entre 1 y 100:", numero_aleatorio)
   ```

6. **Contar de 1 a 10**:
   ```python
   for i in range(1, 11):
       print(i)
   ```

7. **Sumar Números de una Lista**:
   ```python
   numeros = [1, 2, 3, 4, 5]
   suma = sum(numeros)
   print("La suma de la lista es:", suma)
   ```

8. **Manejo de Errores**:
   ```python
   try:
       numero = int(input("Ingrese un número: "))
   except ValueError:
       print("No es un número válido.")
   ```

9. **Mostrar Números Pares**:
   ```python
   for i in range(1, 21):
       if i % 2 == 0:
           print(i)
   ```

10. **Inverso de un Número**:
    ```python
    numero = float(input("Ingrese un número: "))
    print("El inverso es:", 1 / numero if numero != 0 else "Infinito")
    ```

11. **Suma de Dígitos**:
    ```python
    numero = input("Ingrese un número: ")
    suma = sum(int(d) for d in numero)
    print("La suma de los dígitos es:", suma)
    ```

12. **Factorial de un Número**:
    ```python
    import math
    numero = int(input("Ingrese un número: "))
    print("El factorial es:", math.factorial(numero))
    ```

13. **Calcular el Precio Final**:
    ```python
    precio = float(input("Ingrese el precio: "))
    descuento = float(input("Ingrese el descuento en %: "))
    precio_final = precio * (1 - descuento / 100)
    print("El precio final es:", precio_final)
    ```

14. **Verificación de Edad**:
    ```python
    edad = int(input("Ingrese su edad: "))
    if edad >= 18:
        print("Eres mayor de edad.")
    else:
        print("Eres menor de edad.")
    ```

15. **Dibujo de un Triángulo**:
    ```python
    altura = int(input("Ingrese la altura del triángulo: "))
    for i in range(1, altura + 1):
        print(" " * (altura - i) + "*" * (2 * i - 1))
    ```

16. **Reverso de una Cadena**:
    ```python
    cadena = input("Ingrese una cadena: ")
    print("Cadena invertida:", cadena[::-1])
    ```

17. **Suma de Números Pares**:
    ```python
    suma = sum(i for i in range(1, 101) if i % 2 == 0)
    print("La suma de los números pares del 1 al 100 es:", suma)
    ```

18. **Generador de Números Aleatorios**:
    ```python
    import random
    print("Número aleatorio entre 1 y 100:", random.randint(1, 100))
    ```

19. **Calculadora Simple**:
    ```python
    num1 = float(input("Ingrese el primer número: "))
    operador = input("Ingrese el operador (+, -, *, /): ")
    num2 = float(input("Ingrese el segundo número: "))
    if operador == "+":
        print("Resultado:", num1 + num2)
    elif operador == "-":
        print("Resultado:", num1 - num2)
    elif operador == "*":
        print("Resultado:", num1 * num2)
    elif operador == "/":
        print("Resultado:", num1 / num2 if num2 != 0 else "No se puede dividir por cero.")
    else:
        print("Operador no válido.")
    ```

20. **Contador de Palabras**:
    ```python
    frase = input("Ingrese una frase: ")
    palabras = frase.split()
    print("Número de palabras:", len(palabras))
    ```

---
## **Unidad 2: Tipos de Datos, Operadores y Uso Combinado**

1. **Tipos de Datos: Declarar variables de tipo int, float, str y bool, e imprimir sus tipos**:
   ```python
   entero = 10
   flotante = 10.5
   cadena = "Hola"
   booleano = True
   
   print(type(entero))     # <class 'int'>
   print(type(flotante))   # <class 'float'>
   print(type(cadena))     # <class 'str'>
   print(type(booleano))   # <class 'bool'>
   ```

2. **Operaciones Aritméticas: Recibir dos números y mostrar su suma, resta, multiplicación y división**:
   ```python
   a = float(input("Ingresa el primer número: "))
   b = float(input("Ingresa el segundo número: "))
   
   print("Suma:", a + b)
   print("Resta:", a - b)
   print("Multiplicación:", a * b)
   print("División:", a / b)
   ```

3. **Promedio de Notas: Pedir cinco notas al usuario y calcular el promedio**:
   ```python
   notas = []
   for i in range(5):
       nota = float(input(f"Ingrese la nota {i+1}: "))
       notas.append(nota)
   
   promedio = sum(notas) / len(notas)
   print("El promedio es:", promedio)
   ```

4. **Comparaciones: Comparar dos números ingresados por el usuario e indicar cuál es mayor**:
   ```python
   a = float(input("Ingresa el primer número: "))
   b = float(input("Ingresa el segundo número: "))
   
   if a > b:
       print(f"{a} es mayor que {b}")
   elif a < b:
       print(f"{b} es mayor que {a}")
   else:
       print("Ambos números son iguales")
   ```

5. **Uso de Módulos: Determinar si un número es par o impar usando el operador módulo**:
   ```python
   numero = int(input("Ingresa un número: "))
   
   if numero % 2 == 0:
       print(f"{numero} es par")
   else:
       print(f"{numero} es impar")
   ```

6. **Concatenación de Cadenas: Pedir dos cadenas y mostrarlas concatenadas**:
   ```python
   cadena1 = input("Ingresa la primera cadena: ")
   cadena2 = input("Ingresa la segunda cadena: ")
   
   print("Cadenas concatenadas:", cadena1 + " " + cadena2)
   ```

7. **Cálculo de Área: Calcular el área de un círculo a partir de su radio**:
   ```python
   import math
   radio = float(input("Ingresa el radio del círculo: "))
   area = math.pi * (radio ** 2)
   print("El área del círculo es:", area)
   ```

8. **Conversión de Moneda: Convertir una cantidad en dólares a pesos**:
   ```python
   dolares = float(input("Ingresa la cantidad en dólares: "))
   tipo_cambio = 20.0  # Supongamos un tipo de cambio de 20 pesos por dólar
   pesos = dolares * tipo_cambio
   print(f"{dolares} dólares son {pesos} pesos")
   ```

9. **Uso de la Función len: Pedir una cadena y mostrar su longitud**:
   ```python
   cadena = input("Ingresa una cadena: ")
   print("La longitud de la cadena es:", len(cadena))
   ```

10. **Búsqueda de Subcadenas: Verificar si una subcadena está presente en una cadena**:
   ```python
   cadena = input("Ingresa una cadena: ")
   subcadena = input("Ingresa una subcadena: ")
   
   if subcadena in cadena:
       print(f"La subcadena '{subcadena}' está presente en la cadena.")
   else:
       print(f"La subcadena '{subcadena}' no está presente en la cadena.")
   ```

11. **Contador de Caracteres: Contar la cantidad de caracteres en una cadena**:
   ```python
   cadena = input("Ingresa una cadena: ")
   print("La cadena tiene", len(cadena), "caracteres.")
   ```

12. **Condiciones Compuestas: Evaluar si un número es positivo y par**:
   ```python
   numero = int(input("Ingresa un número: "))
   
   if numero > 0 and numero % 2 == 0:
       print(f"{numero} es positivo y par")
   else:
       print(f"{numero} no cumple ambas condiciones")
   ```

13. **Cálculo de Descuentos: Mostrar el precio final después de aplicar un descuento**:
   ```python
   precio = float(input("Ingresa el precio: "))
   descuento = float(input("Ingresa el porcentaje de descuento: "))
   
   precio_final = precio - (precio * (descuento / 100))
   print(f"El precio final con descuento es: {precio_final}")
   ```

14. **Cálculo de IMC: Solicitar peso y altura y calcular el Índice de Masa Corporal (IMC)**:
   ```python
   peso = float(input("Ingresa tu peso en kg: "))
   altura = float(input("Ingresa tu altura en metros: "))
   
   imc = peso / (altura ** 2)
   print(f"Tu Índice de Masa Corporal es: {imc}")
   ```

15. **Cálculo de Notas: Mostrar "Aprobado" o "Reprobado" dependiendo de la calificación**:
   ```python
   nota = float(input("Ingresa la calificación: "))
   
   if nota >= 60:
       print("Aprobado")
   else:
       print("Reprobado")
   ```

16. **Contador de Palabras: Contar cuántas palabras hay en una cadena ingresada**:
   ```python
   cadena = input("Ingresa una cadena: ")
   palabras = cadena.split()
   print(f"La cadena tiene {len(palabras)} palabras.")
   ```

17. **Mayor de Tres Números: Pedir tres números y mostrar el mayor**:
   ```python
   a = float(input("Ingresa el primer número: "))
   b = float(input("Ingresa el segundo número: "))
   c = float(input("Ingresa el tercer número: "))
   
   mayor = max(a, b, c)
   print(f"El mayor de los tres números es: {mayor}")
   ```

18. **Operaciones Lógicas: Verificar si un número está entre 1 y 10**:
   ```python
   numero = int(input("Ingresa un número: "))
   
   if 1 <= numero <= 10:
       print(f"{numero} está entre 1 y 10")
   else:
       print(f"{numero} no está entre 1 y 10")
   ```

19. **Escalera de Números: Imprimir los números del 1 al 20, indicando si son pares o impares**:
   ```python
   for i in range(1, 21):
       if i % 2 == 0:
           print(f"{i} es par")
       else:
           print(f"{i} es impar")
   ```

20. **Cálculo de Intereses: Calcular el interés simple**:
   ```python
   capital = float(input("Ingresa el capital inicial: "))
   interes = float(input("Ingresa el porcentaje de interés anual: "))
   tiempo = float(input("Ingresa el tiempo en años: "))
   
   interes_simple = capital * (interes / 100) * tiempo
   print(f"El interés simple es: {interes_simple}")
   ```

---

## **Unidad 3: Estructuras de Control de Flujo**

1. **Condicional Simple**:
   ```python
   numero = int(input("Ingrese un número: "))
   if numero > 0:
       print("El número es positivo.")
   ```

2. **Condicional Compuesto**:
   ```python
   numero = int(input("Ingrese un número: "))
   if numero > 0:
       print("El número es positivo.")
   elif numero < 0:
       print("El número es negativo.")
   else:
       print("El número es cero.")
   ```

3. **Condicional Anidado**:
   ```python
   edad = int(input("Ingrese su edad: "))
   if edad >= 18:
       print("Eres adulto.")
       if edad >= 65:
           print("Eres un anciano.")
   else:
       print("Eres menor de edad.")
   ```

4. **Bucles `for`**:
   ```python
   for i in range(5):
       print("Iteración", i)
   ```

5. **Bucles `while`**:
   ```python
   contador = 0
   while contador < 5:
       print("Contador:", contador)
       contador += 1
   ```

6. **Suma con `while`**:
   ```python
   suma = 0
   numero = 0
   while numero != -1:
       numero = int(input("Ingrese un número (-1 para terminar): "))
       suma += numero
   print("La suma total es:", suma)
   ```

7. **Tabla de Multiplicar con `for`**:
   ```python
   num = int(input("Ingrese un número: "))
   for i in range(1, 11):
       print(f"{num} x {i} = {num * i}")
   ```

8. **Contador de Pares e Impares**:
   ```python
   pares = 0
   impares = 0
   for i in range(1, 101):
       if i % 2 == 0:
           pares += 1
       else:
           impares += 1
   print("Pares:", pares, "Impares:", impares)
   ```

9. **Números del 1 al 10**:
   ```python
   for i in range(1, 11):
       print(i)
   ```

10. **Contar Vocales en una Cadena**:
    ```python
    cadena = input("Ingrese una cadena: ")
    vocales = "aeiouAEIOU"
    contador = sum(1 for letra in cadena if letra in vocales)
    print("Número de vocales:", contador)
    ```

11. **Encontrar Mínimo y Máximo en una Lista**:
    ```python
    lista = [3, 1, 4, 1, 5, 9, 2, 6]
    print("Mínimo:", min(lista))
    print("Máximo:", max(lista))
    ```

12. **Verificar Número Primo**:
    ```python
    numero = int(input("Ingrese un número: "))
    primo = True
    for i in range(2, int(numero ** 0.5) + 1):
        if numero % i == 0:
            primo = False
            break
    print("Es primo:", primo)
    ```

13. **Imprimir Números Fibonacci**:
    ```python
    n = int(input("Ingrese cuántos números Fibonacci desea: "))
    a, b = 0, 1
    for _ in range(n):
        print(a, end=" ")
        a, b = b, a + b
    ```

14. **Contar Consonantes en una Cadena**:
    ```python
    cadena = input("Ingrese una cadena: ")
    consonantes = "bcdfghjklmnpqrstvwxyzBCDFGHJKLMNPQRSTVWXYZ"
    contador = sum(1 for letra in cadena if letra in consonantes)
    print("Número de consonantes:", contador)
    ```

15. **Invertir una Lista**:
    ```python
    lista = [1, 2, 3, 4, 5]
    lista_invertida = lista[::-1]
    print("Lista invertida:", lista_invertida)
    ```

16. **Multiplicar Elementos de una Lista**:
    ```python
    lista = [1, 2, 3, 4, 5]
    producto = 1
    for num in lista:
        producto *= num
    print("El producto de la lista es:", producto)
    ```

17. **Encontrar el Elemento Mayor de una Lista**:
    ```python
    lista = [10, 20, 30, 40, 50]
    maximo = max(lista)
    print("El mayor elemento es:", maximo)
    ```

18. **Cálculo del Promedio de Números**:
    ```python
    numeros = [10, 20, 30, 40, 50]
    promedio = sum(numeros) / len(numeros)
    print("El promedio es:", promedio)
    ```

19. **Eliminar Elementos Duplicados de una Lista**:
    ```python
    lista = [1, 2, 2, 3, 4, 4, 5]
    lista_sin_duplicados = list(set(lista))
    print("Lista sin duplicados:", lista_sin_duplicados)
    ```

20. **Clasificar Números en Pares e Impares**:
    ```python
    lista = [1, 2, 3, 4, 5, 6]
    pares = [num for num in lista if num % 2 == 0]
    impares = [num for num in lista if num % 2 != 0]
    print("Números pares:", pares)
    print("Números impares:", impares)
    ```

---

## **Unidad 4: Funciones y Módulos**

1. **Función para Sumar dos Números**:
   ```python
   def suma(a, b):
       return a + b

   print(suma(5, 3))
   ```

2. **Función para Calcular el Factorial**:
   ```python
   def factorial(n):
       if n == 0:
           return 1
       return n * factorial(n - 1)

   print(factorial(5))
   ```

3. **Función que Retorna el Máximo de Tres Números**:
   ```python
   def maximo(a, b, c):
       return max(a, b, c)

   print(maximo(5, 8, 3))
   ```

4. **Función que Verifica si un Número es Par**:
   ```python
   def es_par(num):
       return num % 2 == 0

   print(es_par(4))
   ```

5. **Función que Retorna la Longitud de una Cadena**:
   ```python
   def longitud(cadena):
       return len(cadena)

   print(longitud("Hola"))
   ```

6. **Función que Convierte Celsius a Fahrenheit**:
   ```python
   def celsius_a_fahrenheit(celsius):
       return (celsius * 9/5) + 32

   print(celsius_a_fahrenheit(25))
   ```

7. **Función que Imprime los Números de una Lista**:
   ```python
   def imprimir_lista(lista):
       for num in lista:
           print(num)

   imprimir_lista([1, 2, 3])
   ```

8. **Función que Retorna la Suma de Elementos en una Lista**:
   ```python
   def suma_lista(lista):
       return sum(lista)

   print(suma_lista([1, 2, 3, 4]))
   ```

9. **Función que Retorna una Cadena Invertida**:
   ```python
   def invertir_cadena(cadena):
       return cadena[::-1]

   print(invertir_cadena("Hola"))
   ```

10. **Uso de Módulos (Math)**:
    ```python
    import math
    print(math.sqrt(16))
    ```

11. **Función que Retorna los Números Primos en un Rango**:
    ```python
    def primos_en_rango(n):
        primos = []
        for num in range(2, n + 1):
            es_primo = True
            for i in range(2, int(num ** 0.5) + 1):
                if num % i == 0:
                    es_primo = False
                    break
            if es_primo:
                primos.append(num)
        return primos

    print(primos_en_rango(20))
    ```

12. **Función que Retorna la Suma de los Primeros N Números**:
    ```python
    def suma_primeros_n(n):
        return sum(range(1, n + 1))

    print(suma_primeros_n(10))
    ```

13. **Función que Cuenta Vocales en una Cadena**:
    ```python
    def contar_vocales(cadena):
        return sum(1 for letra in cadena if letra.lower() in "aeiou")

    print(contar_vocales("Hola Mundo"))
    ```

14. **Función que Retorna la Media de una Lista**:
    ```python
    def media(lista):
        return sum(lista) / len(lista)

    print(media([1, 2, 3, 4, 5]))
    ```

15. **Función que Retorna el Elemento Más Pequeño de una Lista**:
    ```python
    def minimo(lista):
        return min(lista)

    print(minimo([10, 20, 30, 5]))
    ```

16. **Función que Ordena una Lista**:
    ```python
    def ordenar_lista(lista):
        return sorted(lista)

    print(ordenar_lista([3, 1, 4, 1, 5]))
    ```

17. **Función que Verifica si una Cadena es Palíndromo**:
    ```python
    def es_palindromo(cadena):
        return cadena == cadena[::-1]

    print(es_palindromo("anilina"))
    ```

18. **Función que Retorna la Cantidad de Palabras en una Cadena**:
    ```python
    def contar_palabras(cadena):
        return len(cadena.split())

    print(contar_palabras("Hola mundo"))
    ```

19. **Función que Duplica los Elementos de una Lista**:
    ```python
    def duplicar_lista(lista):
        return [num * 2 for num in lista]

    print(duplicar_lista([1, 2, 3]))
    ```

20. **Función que Retorna una Lista con Números en un Rango**:
    ```python
    def rango_lista(inicio, fin):
        return list(range(inicio, fin + 1))

    print(rango_lista(1, 10))
    ```

---

## **Unidad 5: Listas y Vectores**

1. **Crear una Lista**:
   ```python
   lista = [1, 2, 3, 4, 5]
   print(lista)
   ```

2. **Acceder a Elementos de una Lista**:
   ```python
   lista = [10, 20, 30, 40]
   print(lista[0])  # Primer elemento
   ```

3. **Modificar Elementos de una Lista**:
   ```python
   lista = [10, 20, 30, 40]
   lista[1] = 25
   print(lista)
   ```

4. **Agregar Elementos a una Lista**:
   ```python
   lista = [1, 2, 3]
   lista.append(4)
   print(lista)
   ```

5. **Eliminar Elementos de una Lista**:
   ```python
   lista = [1, 2, 3, 4]
   lista.remove(3)
   print(lista)
   ```

6. **Longitud de una Lista**:
   ```python
   lista = [1, 2, 3]
   print("Longitud:", len(lista))
   ```

7. **Recorrer una Lista con `for`**:
   ```python
   lista = [1, 2, 3]
   for num in lista:
       print(num)
   ```

8. **Listas Anidadas**:
   ```python
   matriz = [[1, 2], [3, 4]]
   print(matriz[0][1])  # Acceder al elemento 2
   ```

9. **Ordenar una Lista**:
   ```python
   lista = [3, 1, 2]
   lista.sort()
   print(lista)
   ```

10. **Contar Elementos en una Lista**:
    ```python
    lista = [1, 2, 2, 3]
    print(lista.count(2))  # Contar cuántas veces aparece el 2
    ```

11. **Crear una Lista de Números Cuadrados**:
    ```python
    lista = [x**2 for x in range(1, 6)]
    print(lista)
    ```

12. **Concatenar Listas**:
    ```python
    lista1 = [1, 2]
    lista2 = [3, 4]
    lista_concatenada = lista1 + lista2
    print(lista_concatenada)
    ```

13. **Invertir una Lista**:
    ```python
    lista = [1, 2, 3]
    lista.reverse()
    print(lista)
    ```

14. **Crear una Lista de Números Aleatorios**:
    ```python
    import random
    lista = [random.randint(1, 10) for _ in range(5)]
    print(lista)
    ```

15. **Buscar un Elemento en una Lista**:
    ```python
    lista = [1, 2, 3]
    print(2 in lista)  # Devuelve True si 2 está en la lista
    ```

16. **Duplicar Elementos de una Lista**:
    ```python
    lista = [1, 2, 3]
    lista_doblada = [x * 2 for x in lista]
    print(lista_doblada)
    ```

17. **Filtrar Elementos en una Lista**:
    ```python
    lista = [1, 2, 3, 4, 5]
    lista_pares = [x for x in lista if x % 2 == 0]
    print(lista_pares)
    ```

18. **Unir dos Listas en una Cadena**:
    ```python
    lista = ["Hola", "mundo"]
    cadena = " ".join(lista)
    print(cadena)
    ```

19. **Transformar una Lista de Cadenas a Mayúsculas**:
    ```python
    lista = ["hola", "mundo"]
    lista_mayusculas = [x.upper() for x in lista]
    print(lista_mayusculas)
    ```

20. **Crear una Lista de Números Pares del 1 al 20**:
    ```python
    lista_pares = [x for x in range(1, 21) if x % 2 == 0]
    print(lista_pares)
    ```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMzUxODAzMzI3XX0=
-->