# Taller-2-API-lados
____________________________________ 

*Desarrollo del Taller 2 en la asignatura de Programacion de Computadores - UNAL*
Coordial saludo, nuestro grupo de Programacion se llama API-lados, a continuacion presentamos nuestro grandioso logo.

[![Whats-App-Image-2024-02-28-at-9-47-06-AM.jpg](https://i.postimg.cc/W4qjTqyc/Whats-App-Image-2024-02-28-at-9-47-06-AM.jpg)](https://postimg.cc/rdT79scf)

## Integrantes:
+ Michael Kaleth Mora Mejia (1086774311)
+ Angie Carolina Salazar Lara (1052837889)
+ Alejandro	Urrego Valencia (1000364014)
__________________________________
## Desarrollo 
### Punto 11 BONO.
A continuacion, el programa en Python que determina si una matriz cuadrada es magica. **NOTA**: *Una matriz es magica si la suma de cada una de sus filas, columnas y diagonales es la misma*.

**Enfoque**:
+ Primero, calculamos la suma de la primera fila. Esta suma servira como referencia.
+ Luego, verificamos si todas las demas filas, columnas y diagonales tienen la misma suma que la referencia.
+ Si alguna fila, columna o diagonal no coincide con la suma de referencia, la matriz no es magica.

```python
def es_matriz_magica(matriz):
    n = len(matriz)  # tamaño de la matriz (n x n)
    
    # calc la + de la primera fila como referencia
    suma_referencia = 0
    for j in range(n):
        suma_referencia += matriz[0][j]
    
    # verifica si todas las filas tienen la misma +
    for i in range(1, n):
        suma_fila = 0
        for j in range(n):
            suma_fila += matriz[i][j]
        if suma_fila != suma_referencia:
            return False
    
    # verfica si todas las columnas tienen la misma +
    for j in range(n):
        suma_columna = 0
        for i in range(n):
            suma_columna += matriz[i][j]
        if suma_columna != suma_referencia:
            return False
    
    # verifica la + de la diagonal principal
    suma_diagonal_principal = 0
    for i in range(n):
        suma_diagonal_principal += matriz[i][i]
    if suma_diagonal_principal != suma_referencia:
        return False
    
    # verfica la + de la diagonal secundaria
    suma_diagonal_secundaria = 0
    for i in range(n):
        suma_diagonal_secundaria += matriz[i][n - i - 1]
    if suma_diagonal_secundaria != suma_referencia:
        return False
    
    # SI todas las + son =, la matriz es |magica|
    return True

# ejemplo

# definimos una matriz 
matriz = [
    [2, 7, 6],
    [9, 5, 1],
    [4, 3, 8]
]

# llama a la funcion para verif si la matriz es |magica|
if es_matriz_magica(matriz):
    print("La matriz es magica.")
else:
    print("La matriz no es magica.")
```

**Explicación:**
1. Funcion `es_matriz_magica(matriz)`:
   + Parametro: `matriz` es una lista de listas que representa la matriz cuadrada.
   + Variable `n`: Determina el tamaño de la matriz `(n x n)`.
   + Suma de referencia: Se calcula la suma de la primera fila y se usa como referencia.
    
2. Verificacion de filas:
    + Se verifica si la suma de cada fila es igual a la suma de referencia.

3. Verificacion de columnas:
    + Se verifica si la suma de cada columna es igual a la suma de referencia.

4. Verificacion de diagonales:
    + Se calcula y compara la suma de la diagonal principal (de la esquina superior izquierda a la inferior derecha).
    + Se calcula y compara la suma de la diagonal secundaria (de la esquina superior derecha a la inferior izquierda).

5. Resultado:
    + Si todas las sumas coinciden con la referencia, la funcion devuelve `True`, indicando que la matriz es `magica`.
    + De lo contrario, devuelve `False`.
   
________________________________________
### Punto 1. 
Desarrollar un programa que ingrese un numero entero n y separe todos los digitos que componen el numero. Pista: Utilice los operadores modulo (%) y division entera (//).

```python
# Prog para separar los digitos de un numero entero

numero = int(input("Ingresa un numero entero: "))

#Lista para almacenar los dig
digitos = []

# verificar si el numero es -
if numero < 0:
    numero = -numero  # Convertir a +

# usar ciclo while 
while numero > 0:
    digito = numero % 10 
    digitos.append(digito) 
    numero = numero // 10  # quitar ultimo dig del num

# invertir la lista de dig pq se agregaron al rev

digitos.reverse()
```

**Explicación:**

El objetivo de este programa es tomar un numero entero `n` y separar todos los digitos que lo componen. Para lograrlo, el programa utiliza los operadores modulo `(%)` y division entera `(//)`. 
+ **Entrada**: Se solicita al usuario que ingrese un numero entero mediante `input()` y se convierte a entero con `int()`.

+ **Lista digitos**: Inicializamos una lista vacia para almacenar los digitos extraidos.

+ **Bucle while**: Continuamos extrayendo digitos mientras n sea mayor que cero.

    - Usamos n % 10 para obtener el ultimo digito del numero.
    - Ese digito se añade a la lista digitos.
    - Luego, eliminamos el ultimo digito del numero usando n = n // 10.
+ **Salida**: Finalmente, se imprime la lista digitos, que contiene los digitos del numero en orden inverso al que se extrajeron.

Es un enfoque simple pero efectivo.

________________________________________

### Punto 2.

```python
# Ingresar un número flotante
n = float(input("Ingresa un número flotante: "))

# Obtener la parte entera
parte_entera = int(n)

# Calcular la parte decimal restando la parte entera
parte_decimal = n - parte_entera

# Mostrar los dígitos de la parte entera
print("Dígitos de la parte entera:")
while parte_entera > 0:
    digito = parte_entera % 10
    print(digito)
    parte_entera //= 10

# Mostrar los dígitos de la parte decimal
print("Dígitos de la parte decimal:")
while parte_decimal > 0:
    parte_decimal *= 10
    digito = int(parte_decimal)
    print(digito)
    parte_decimal -= digito
```

**Explicación:**

Para la realización de este programa se separa un número flotante en su parte entera y decimal, y luego imprime los dígitos de ambas partes.

Ingreso: El usuario ingresa un número flotante.

Separación: La parte entera se obtiene con `int()`, y la decimal restando la parte entera del número original.

Descomposición:
- Para la parte entera, se extraen los dígitos uno por uno usando el operador `% 10` y se eliminan con `// 10`.
- Para la parte decimal, se multiplica por 10, se extrae el dígito más significativo, y se elimina del número.
  
Este proceso se repite hasta que no queden dígitos en ambas partes.

_________________________________________
### Punto 3. 

Desarrollar un programa que permita ingresar dos numeros enteros y determinar si se tratan de numeros espejos, definiendo numeros espejos como dos numeros a y b tales que a se lee de izquierda a derecha igual que se lee b de derecha a izquierda, y viceversa.
```python
    # inicio de la variable que almacenara el numero invertido
    invertido = 0
    
    # mientras queden dig en n
    while n > 0:
        # obtenemos el ult dig de n
        ultimo_digito = n % 10
        # dezplamaos los dig ya invertidos a la izquierda (X por 10) y + el ult dig
        invertido = invertido * 10 + ultimo_digito
        # quitamos el ult dig de n
        n = n // 10
    
    # retornamos el num invertido
    return invertido

def son_espejos(a, b):
    # invertimos el num a
    a_invertido = invertir_numero(a)
    
    # comparar el num invertido de a con b
    if a_invertido == b:
        return True
    else:
        return False

numero1 = int(input("Ingresa el primer numero: "))
numero2 = int(input("Ingresa el segundo numero: "))

# verifica si son nums espejos
if son_espejos(numero1, numero2):
    print("Los numeros son espejos.")
else:
    print("Los numeros no son espejos.")
```

**Explicación:**
Un numero espejo es un par de numeros donde uno es la version invertida del otro. Por ejemplo, 123 y 321 son numeros espejos porque si se invierte el numero 123, se obtiene 321.

Para resolver el problema:

+ **Invertir un número**: Se puede invertir un numero al reves usando operaciones matematicas. Se obtiene el ultimo digito utilizando el modulo `(%)` y se elimina el ultimo digito utilizando la division entera `(//)`. Luego, se construye el numero invertido sumando estos digitos en orden inverso.
+ **Comparar los numeros**: Despues de invertir uno de los numeros, se compara con el otro para determinar si son espejos.
________________________________________

### Punto 4.

```python
import math

def aproximacion_coseno(x, n):
    # Inicializar la aproximación y las variables para el cálculo de términos
    aproximacion = 0
    termino = 1  # El primer término de la serie es 1 (x^0 / 0!)
    signo = 1  # Para alternar los signos en la serie

    for i in range(n):
        aproximacion += signo * termino
        signo *= -1  # Alterna el signo
        # Actualizar el término siguiente de la serie: x^(2i) / (2i)!
        termino *= (x ** 2) / ((2 * i + 1) * (2 * i + 2))

    return aproximacion

def calcular_error(x, error_deseado):
    # Calcular el valor real de cos(x)
    valor_real = math.cos(x)
    n = 1
    
    while True:
        valor_aproximado = aproximacion_coseno(x, n)
        diferencia = abs(valor_real - valor_aproximado)
        error_relativo = diferencia / abs(valor_real)
        
        if error_relativo <= error_deseado:
            return n
        
        n += 1

# Ejemplo de uso
x = float(input("Ingresa un valor para x: "))

# Calcular para diferentes errores deseados
error_10 = calcular_error(x, 0.1)
print(f"Para un error del 10%, se necesitan {error_10} términos.")

error_1 = calcular_error(x, 0.01)
print(f"Para un error del 1%, se necesitan {error_1} términos.")

error_01 = calcular_error(x, 0.001)
print(f"Para un error del 0.1%, se necesitan {error_01} términos.")

error_001 = calcular_error(x, 0.0001)
print(f"Para un error del 0.01%, se necesitan {error_001} términos.")
```

**Explicación:**

Para este code se utilizó:

- Función `aproximacion_coseno(x, n)`: Calcula la aproximación de la función coseno usando n términos de la serie de Taylor.

- Función `calcular_error(x, error_deseado)`: Calcula cuántos términos son necesarios en la serie para que el error relativo entre el coseno calculado y el real sea menor o igual al `error_deseado`.

Ejemplo: Se llama a `calcular_error` para diferentes errores deseados (10%, 1%, 0.1%, 0.01%) y se imprime cuántos términos son necesarios en cada caso.

________________________________________

### Punto 5.
Para determinar el Minimo Comun Multiplo (MCM) de dos numeros enteros, podemos usar la relacion entre el MCM y el Maximo Comun Divisor (MCD) de dos numeros. Esta relacion se expresa como:

$$\\text{MCM}(a, b) = \frac{|a \times b|}{\text{MCD}(a, b)}\$$ 

Donde $$|a x b|$$ es el valor absoluto del producto de los dos numeros.

**Algoritmo de Euclides para el MCD**

El MCD se puede calcular de manera eficiente usando el Algoritmo de Euclides, que se basa en la siguiente idea: <p>MCD(<em>a</em>, <em>b</em>) = MCD(<em>b</em>, <em>a</em> % <em>b</em>)</p>


Este proceso se repite hasta que uno de los numeros sea cero, y el otro numero es el MCD.



**Enfoque Iterativo**

```python
def mcd_iterativo(a, b):
    # usamos el algoritmo de Euclides de manera iterativa
    while b != 0:
        a, b = b, a % b
    return a

def mcm(a, b):
    # se calcula el MCM usando la relacion entre MCM y MCD
    return abs(a * b) // mcd_iterativo(a, b)

# ingresa dos num enteros
numero1 = int(input("Ingresa el primer numero: "))
numero2 = int(input("Ingresa el segundo numero: "))

# calcula el MCM y lo muestra
resultado = mcm(numero1, numero2)
print(f"El minimo comun Multiplo de {numero1} y {numero2} es: {resultado}")

```
**Enfoque Recursivo**

```python
def mcd_recursivo(a, b):
    # usamos el algoritmo de Euclides de manera recursiva
    if b == 0:
        return a
    else:
        return mcd_recursivo(b, a % b)

def mcm(a, b):
    # se calcula el MCM usando la relacion entre MCM y MCD
    return abs(a * b) // mcd_recursivo(a, b)

# ingresa dos num enteros
numero1 = int(input("Ingresa el primer numero: "))
numero2 = int(input("Ingresa el segundo numero: "))

# calcula el MCM y lo muestra
resultado = mcm(numero1, numero2)
print(f"El minimo comun Multiplo de {numero1} y {numero2} es: {resultado}")
```

**Explicacion:**
1. Calculo del MCD (iterativo y recursivo):
+ *Iterativo*: Utilizamos un ciclo `while` para aplicar el Algoritmo de Euclides. Continuamos intercambiando `a` y `b` con `b` y `a % b` hasta que `b` sea 0. El valor de a en ese momento es el MCD.
+ *Recursivo*: Aplicamos el Algoritmo de Euclides recursivamente. Si `b` es 0, el MCD es a. Si no, llamamos recursivamente a la funcion con `b` y `a % b`.

2. Calculo del MCM:
+ Usamos la formula $$\\text{MCM}(a, b) = \frac{|a \times b|}{\text{MCD}(a, b)}\$$ para calcular el MCM de los dos numeros.
+ Utilizamos la funcion del MCD (ya sea la iterativa o la recursiva) para obtener el MCD y luego calcular el MCM.

3. Entrada:
+ El programa solicita que ingrese dos numeros enteros y luego calcula y muestra el MCM utilizando las funciones definidas.
________________________________________

### Punto 6.

```python
# Inicializamos una variable que indica si hay repetidos
hay_repetidos = False

# Leemos la cantidad de números a ingresar
cantidad = int(input("Ingrese la cantidad de números: "))

# Iteramos sobre cada número
for i in range(cantidad):
    # Pedimos al usuario que ingrese un número
    numero = int(input(f"Ingrese el número {i + 1}: "))
    
    # Variable auxiliar para almacenar el siguiente número a comparar
    numero_siguiente = numero
    
    # Comparación entre el número actual y los números siguientes
    for j in range(i + 1, cantidad):
        numero_siguiente = int(input(f"Ingrese nuevamente el número {j + 1} para comparar: "))
        
        # Si encontramos un número igual al actual, marcamos como repetido
        if numero == numero_siguiente:
            hay_repetidos = True
    
    # Si se encontró un repetido, salimos del ciclo
    if hay_repetidos:
        break

# Imprimimos el resultado
if hay_repetidos:
    print("Existen elementos repetidos.")
else:
    print("No existen elementos repetidos.")
```

**Explicación:**
Para este programa utilizamos: 
1. Entrada del número de elementos: Primero, pedimos al usuario que ingrese la cantidad de números que desea ingresar.

2. Comparación de elementos: Para cada número, comparamos ese número con todos los números que siguen. Si encontramos un número que ya se ingresó antes, cambiamos la `variable hay_repetidos` a `True`.

3. Salida del resultado: Finalmente, dependiendo de si se encontraron elementos repetidos o no, mostramos el mensaje correspondiente.
________________________________________
### Punto 7.

```python
def contar_vocales(cadena):
    vocales = 0
    for char in cadena:
        if char in 'aeiouAEIOU':
            vocales += 1
        if vocales >= 2:
            return vocales
    return vocales

def buscar_cadena_con_vocales(cadena1, cadena2, cadena3, cadena4, cadena5):
    if contar_vocales(cadena1) >= 2:
        print(cadena1)
        return
    if contar_vocales(cadena2) >= 2:
        print(cadena2)
        return
    if contar_vocales(cadena3) >= 2:
        print(cadena3)
        return
    if contar_vocales(cadena4) >= 2:
        print(cadena4)
        return
    if contar_vocales(cadena5) >= 2:
        print(cadena5)
        return
    
    print("No existe")
```

**Explicación:**

Este código verifica si alguna de las cinco cadenas tiene dos o más vocales :

- `contar_vocales(cadena)`: Recorre cada carácter de la cadena y cuenta vocales. Si encuentra dos o más, retorna el conteo; si no, sigue contando hasta terminar.

- `buscar_cadena_con_vocales`(cadena1, cadena2, cadena3, cadena4, cadena5): Llama a `contar_vocales` para cada cadena. Si alguna tiene dos o más vocales, la imprime; si ninguna las tiene, imprime "No existe".


________________________________________
### Punto 8.

```python
def diferenciar_elementos(lista1, lista2):
    return [elemento for elemento in lista1 if elemento not in lista2]

lista1 = [int(x) for x in input("Por favor, ingrese los elementos de la primera lista (separados por espacio): ").split()]
lista2 = [int(x) for x in input("Por favor, ingrese los elementos de la segunda lista (separados por espacio): ").split()]

elementos = diferenciar_elementos(lista1, lista2)

if elementos:
    print("Los elementos que tiene la primera lista que no tiene la segunda lista son:", elementos)
else:
    print("La primera lista no contiene elementos que no tenga la segunda lista.")
```

**Explicación:**

Este código define una función llamada diferenciar_elementos que recibe dos listas como parámetros y retorna una nueva lista con los elementos que están en la primera lista pero no en la segunda.

- `def diferenciar_elementos(lista1, lista2)`: Define la función diferenciar_elementos que recibe las listas: lista1 y lista2


- `return`: Retorna una nueva lista que contiene los elementos que están en lista1 pero no en lista2. Esto mediante una verificación por iteración. Si no está, se agrega a la nueva lista.

- `lista`: Solicita al usuario que ingrese los elementos de la lista 

- `elementos`: Llama a la función diferenciar_elementos con lista1 y lista2 como argumentos y almacena el resultado en la variable.

- `print`: Si la lista elementos no está vacía, los imprime.

________________________________________
### Punto 9.

```python
import numpy as np

# Ingreso de números
numeros = [float(input(f"Por favor ingrese el número {i+1}: ")) for i in range(5)]

# Cálculo de operaciones
promedio = np.mean(numeros)
mediana = np.median(numeros)
promedio = np.prod(numeros) ** (1/len(numeros))
ascendente = np.sort(numeros)
descendente = np.sort(numeros)[::-1]
potencia = max(numeros) ** min(numeros)
raiz_cubica = np.cbrt(min(numeros))

# Impresión de resultados
print(f"Promedio: {promedio}")
print(f"Mediana: {mediana}")
print(f"Promedio: {promedio}")
print(f"Números en orden ascendente: {ascendente}")
print(f"Números en orden descendente: {descendente}")
print(f"La potencia del mayor número elevado al menor número: {potencia}")
print(f"La raíz cúbica del menor número: {raiz_cubica}")

```

**Explicación:**

Este código calcula y muestra varias operaciones matemáticas con una lista de 5 números.

- `import numpy as np`: Se importa la biblioteca NumPy, la cual proporciona funciones para operaciones matemáticas.

- `numeros`: Se solicita al usuario que ingrese 5 números, que se almacenan en una lista. 

- `promedio`: Se calcula el promedio de los números utilizando la función np.mean() de NumPy.

- `mediana`: Se calcula la mediana de los números utilizando la función np.median() de NumPy.

- `promedio`: Se calcula el promedio elevando el producto de los números a la potencia de 1 dividido por la cantidad de números.

- `ascendente`: Se ordenan los números en orden ascendente utilizando la función np.sort() de NumPy.

- `descendente`: Se ordenan los números en orden descendente invirtiendo la lista ordenada ascendente.

- `potencia`: Se calcula la potencia del mayor número elevado al menor número.

- `raiz_cubica`: Se calcula la raíz cúbica del menor número utilizando la función np.cbrt() de NumPy.



______________________________________
### Punto 10.
**Acumulación**

```python
def multiplos_3_ac(lista):
    
    lista_multiplos_de_3 = []
    
    for numero in lista:
       
        if numero % 3 == 0:
            lista_multiplos_de_3.append(numero)

    return lista_multiplos_de_3

# Ejemplo
lista_a = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15]
resultado = multiplos_3_ac(lista_a)
print(resultado) 
```
**Explicación:**

Este código define una función la cual recibe una lista de números como argumento y devuelve una nueva lista con solo los números que son múltiplos de 3.


- `def multiplos_3_ac(lista)`: Se define la función multiplos_3_ac 

- `lista_multiplos_de_3 = []`: Se crea una lista vacía llamada lista_multiplos_de_3 que almacenará los múltiplos de 3.

- `if numero % 3 == 0`: Se verifica si el número actual es múltiplo de 3 utilizando el operador módulo (%). Si el resto de la división del número entre 3 es 0, entonces es múltiplo de 3.

- `lista_multiplos_de_3.append(numero)`: Si el número es múltiplo de 3, se añade a la lista lista_multiplos_de_3 utilizando el método append.



**Compresión de listas**

```python
def multiplos_3_comprension(lista):
    
    return [numero for numero in lista if numero % 3 == 0]

# Ejemplo
lista_a = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15]
resultado = multiplos_3_comprension(lista_a)
print(resultado) 
```


**Explicación:**

Este código define una función llamada multiplos_3_comprension que utiliza una comprensión de listas para filtrar los múltiplos de 3 en una lista de números.

- `def multiplos_3_comprension(lista):`: Se define la función multiplos_3_comprension que toma una lista como argumento.
 
- `return [numero for numero in lista if numero % 3 == 0]`: Se utiliza una comprensión de listas para crear una nueva lista con solo los números que son múltiplos de 3.

- `numero for numero in lista`: Se itera sobre cada número en la lista lista.

- `if numero % 3 == 0`: Se verifica si el número actual es múltiplo de 3 utilizando el operador módulo (%). Si el resto de la división del número entre 3 es 0, entonces es múltiplo de 3.

- `resultado = multiplos_3_comprension(lista_a)`: Se llama a la función multiplos_3_comprension con la lista lista_a como argumento y se almacena el resultado en la variable resultado.


_____________________________________

