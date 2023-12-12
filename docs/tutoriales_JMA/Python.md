---
sidebar_position: 3
---
 
 
---

![Python](./img/Pythonlogo.jpg)

---
### ENLACE DESCARGAR PYTHON
:::info

  [  DESCARGAR PYTHON](https://www.python.org/downloads/)
:::

---
### ENLACE DESCARGAR UN EDITOR DE CODIGO
:::info
  [ DESCARGAR VScode](https://code.visualstudio.com/)

:::

---
### CREAR UNA CARPETA DEL PROYECTO.


---


### VER LA VERSION DE PYTHON.

:::tip Python
En la terminal situada en la carpeta del proyecto o en entorno virtual escribimos el comando:

```
  py --version
```
:::

---

### CREAR UN ENTORNO VIRTUAL. entorno-virtual

:::tip Python
En la terminal situada en la carpeta del proyecto escribimos el comando:

```
 virtualenv -p python3 nombre_entorno_virtual
```

:::

---

### ACTIVAR EL ENTORNO VIRTUAL.
:::tip Python

En la terminal situada en la carpeta del proyecto escribimos el comando:

```
\nombre_entorno_virtual\Scripts\activate
```

:::

---

### DESACTIVAR EL ENTORNO VIRTUAL.
:::tip Python
En la terminal situada en el entorno virtual escribimos el comando:
```
  deactivate
```
o tambien pulsando las teclas: Ctrl + C

:::

---

### INSTALAR MODULOS O PAQUETES. (flask, jinja2, requests)
:::tip Python
En la terminal situada en la carpeta del proyecto o en entorno virtual escribimos el comando:
```
  pip install nombre del modulo
```
:::

---

### VER MODULOS O PAQUETES INSTALADOS.
:::tip Python
En la terminal situada en la carpeta del proyecto o en entorno virtual escribimos el comando:
```
  pip list
```
:::

---

### CREAR UN ARCHIVO DE TEXTO CON LOS MODULOS O PAQUETES INSTALADOS.
:::tip Python
En la terminal situada en la carpeta del proyecto o en entorno virtual escribimos el comando:
```
  pip freeze > requirements.txt
```
:::
---

### CREAR UN ARCHIVO app.py
:::tip Python
En la terminal situada en la carpeta del proyecto
```
  app.py
```  
:::

---

### ACTIVAR EL SERVIDOR Y EJECUTAR LA APLICACION.
:::tip Python
En la terminal situada en la carpeta del proyecto escribimos el comando:
```
  python app.py
```
:::

---

### VER LA APLICACION EN EL NAVEGADOR.
:::tip Python
127.0.0.1 = localhost

En el navegador escribimos :

http://localhost:8000 --------------> Pagina index.html

Pulsar crtl y hacer click en http://localhost:8000
:::

---

### DESACTIVAR EL SERVIDOR.
:::tip Python
Teclear las teclas Ctrl + c
:::

---



### Función sin parámetros o retorno de valores
:::info 

```python
def diHola():
  print("Hello!")
```

 llamada a la función, 'Hello!' se muestra en la consola

```python
diHola() 
```
:::
 
---
### Función con un parámetro
:::info

```python
def holaConNombre(name):
  print("Hello " + name + "!")
```
llamada a la función, 'Hello Ada!' se muestra en la consola
```python
holaConNombre("Ada") 
```
:::

---

### Función con múltiples parámetros con una sentencia de retorno
:::info funcion que multiplica dos valores.

```python
def multiplica(val1, val2):
  return val1 * val2
```
llamada a la función y la guarda en la variable **resultado** y luego  muestra 15 en la consola 

```python
resultado = multiplica(3, 5)
print( resultado )
```
llamada a la función y la guarda en la variable **resultado_1** y luego  muestra 75 en la consola 

```python
resultado_1 = multiplica(5, 15)
print( resultado_1 )
```

:::

---

### Funcion  Fibonacci
:::info funcion  Fibonacci series up to n

```python
 # This is a comment
 def fib(n):
     a, b = 0, 1
     while a < n:
         print(a, end=' ')
         a, b = b, a+b
     print()
 ```
 llamada a la función 
 ```python
 fib(1000)
 ``` 
 muestra la serie Fibonacci hasta el numero pasado como parametro.

0 1 1 2 3 5 8 13 21 34 55 89 144 233 377 610 987

:::

---

### Funcion lambda
:::info funcion  lambda
Por ejemplo, puedes escribir una función lambda que duplique sus argumentos

 `lambda x: x * 2`   y usarla con la función `map `para duplicar todos los elementos de una lista:
```python

mi_lista = [1, 2, 3, 4, 5, 6]
lista_nueva = list(map(lambda x: x * 2, mi_lista))
print(lista_nueva)  # [2, 4, 6, 8, 10, 12]

```
Así luce sin una función lambda
```python
def doble(x):
  return x*2
  
mi_lista = [1, 2, 3, 4, 5, 6]
lista_nueva = list(map(doble, mi_lista))
print(lista_nueva) # [2, 4, 6, 8, 10, 12]
```
:::

---

:::info funcion  lambda
También puedes escribir una función lambda que revise si un número es positivo,

`lambda x: x > 0`,  y usarla con la función `filter` para crear una lista de números positivos.
```python
# This is a comment
mi_lista = [18, -3, 5, 0, -1, 12]
lista_nueva = list(filter(lambda x: x > 0, mi_lista))
print(lista_nueva) # [18, 5, 12]

```
 
:::

---

## Bucle for

:::tip for

* Imprima cada fruta en una lista de frutas:
```python
fruits = ["apple", "banana", "cherry"]
for x in fruits:
  print(x)

 ``` 
* Con la instrucción `break` podemos detener el ciclo antes de que haya recorrido todos los elementos
```python
#Salga del bucle cuando `x` sea "plátano":

fruits = ["apple", "banana", "cherry"]
for x in fruits:
  print(x)
  if x == "banana":
    break
 ``` 



* Con la instrucción `continue` podemos detener la iteración actual del bucle y continuar con la siguiente:
```python
# No imprimir plátano:

fruits = ["apple", "banana", "cherry"]
for x in fruits:
  if x == "banana":
    continue
  print(x)
```


* Recorra las letras de la palabra "plátano":
```python
for x in "banana":
  print(x)
```

* La función `range()` devuelve una secuencia de números, que comienza en 0 de forma predeterminada, se incrementa en 1 (de forma predeterminada) y termina en un número específico

```python
# Tenga en cuenta que el rango (6) no son los valores de 0 a 6, 
# sino los valores de 0 a 5.
for x in range(6):
  print(x)
```
```python
# range(2, 6) , que significa valores del 2 al 6 (pero sin incluir 6):
for x in range(2, 6):
  print(x)
```
```python
# range(2, 30, 3 ), Incrementa la secuencia con 3 
# (el valor predeterminado es 1):
for x in range(2, 30, 3):
  print(x)
```

### Bucles anidados
* Un bucle anidado es un bucle dentro de un bucle.
* El "bucle interno" se ejecutará una vez por cada iteración del "bucle externo":
```python


adj = ["red", "big", "tasty"]
fruits = ["apple", "banana", "cherry"]

for x in adj:
  for y in fruits:
    print(x, y)
# Imprime cada adjetivo para cada fruta:
red apple
red banana
red cherry
big apple
big banana
big cherry
tasty apple
tasty banana
tasty cherry
```
### Otra cosa en el bucle For
* La  palabra clave `else` en un bucle  `for `especifica un bloque de código que se ejecutará cuando finalice el bucle:

```python
 
# Imprime todos los números del 0 al 5 
# e imprime un mensaje cuando el ciclo haya finalizado:

for x in range(6):
  print(x)
else:
  print("Finally finished!")
```
:::
 ---

 ## Bucle while

:::caution
* Con el bucle `while` podemos ejecutar un conjunto de declaraciones siempre que una condición sea verdadera.
```python
# Imprima i siempre que sea menor que 6:
i = 1
while i < 6:
  print(i)
  i += 1
```
* Con la sentencia `break` podemos detener el ciclo incluso si la condición while es verdadera:
```python
# Salga del ciclo cuando i sea 3:
i = 1
while i < 6:
  print(i)
  if i == 3:
    break
  i += 1
```
* Con la instrucción `continue` podemos detener la iteración actual y continuar con la siguiente:
```python
# Continúe con la siguiente iteración si i es 3:
i = 0
while i < 6:
  i += 1
  if i == 3:
    continue
  print(i)
```
* Con la instrucción  `else` podemos ejecutar un bloque de código una vez cuando la condición ya no sea verdadera:

```python
# Imprima un mensaje una vez que la condición sea falsa:

i = 1
while i < 6:
  print(i)
  i += 1
else:
  print("i is no longer less than 6")
```
:::

---


 