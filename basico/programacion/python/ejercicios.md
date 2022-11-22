---
description: Aquí encontrarás ejercicios para poner en práctica lo visto en las unidades.
---

# Ejercicios

## Ejercicio 1  \~ La liga

### Enunciado:

Hoy en día todos los deportes están enmarcados en competiciones donde hay clasificaciones. Habrá deportes donde existan diferentes sistemas de puntuación, por lo que los puntos que obtenga un equipo o individuo va a variar dependiendo de dónde se encuentre.

Por ello, surge la necesidad de realizar un programa donde se pueda calcular el número mínimo de victorias necesarias para alcanzar al equipo o individuo líder.&#x20;

### Entrada:

Dos números enteros, uno por línea, tal que el primer número representa el número de puntos de diferencia del líder respecto a ti, y el segundo represente el número de puntos por victoria en la competición.

### Salida:

Se debe representar únicamente el número de victorias que separan a un equipo del líder. No debe haber decimales.

### Librerías necesarias:

Se puede importar la librería math y sus métodos asociados mediante:

`import [método] from [librería]`

### Casos de prueba:

En color verde entradas por teclado, en blanco lo que sale por pantalla:

![](<../../../.gitbook/assets/image (2).png>)

![](<../../../.gitbook/assets/image (5).png>)

### Solución:

```python
from math import ceil

puntodiff = int(input())
puntovict = int(input())

n_victorias = ceil(puntodiff / puntovict)

print(n_victorias)
```

## Ejercicio 2 \~ La almendra

### Enunciado:

En una de las ruedas de prensa, a Fernando Simón le jugó una mala pasada una almendra. Para evitar que se repita esto, necesita ser capaz de calcular cuántas almendras puede comerse antes de atragantarse. Cada almendra, cuyo peso viene dado en gramos, tiene un cierto valor nutritivo.

Dado un peso máximo y un valor nutritivo, el objetivo de Fernando es comprobar si puede comer suficientes almendras sin pasar del peso máximo para obtener un valor nutritivo dado. Para no pasarse del peso, puede comerse solo un trozo de almendra, obteniendo la parte proporcional de su valor nutritivo.

### Entrada:

La primera línea contiene dos enteros N y P que indican el número de almendras que tiene Fernando Simón en la bolsa, y el número de pruebas de valor nutritivo que se van a hacer.

Las siguientes N líneas contienen dos enteros V y A que indican el valor nutritivo y el peso de cada almendra.

Las siguientes P líneas contienen dos enteros MV y MA que indican el valor nutritivo a obtener y el peso máximo que puede tomar Fernando Simón antes de que le dé un ataque de tos.

### Salida:

Por cada caso, se imprimirá por consola en una línea nueva la cadena PUEDE si es capaz de obtener los nutrientes necesarios o TOS si le da un ataque de tos por superar el peso máximo.

### Casos de prueba:

Igual que el anterior; lo que entra por teclado en verde, lo que sale por pantalla en blanco:

![](<../../../.gitbook/assets/image (7).png>)

![](<../../../.gitbook/assets/image (4).png>)

### Solución:

```python
def almendrita(data):
    value = 0
    free_weight = data['maxweight']
    n = len(data['ratio'])
    i = 0
    isSol = False
    while (i < n and isSol == False and free_weight <= data['maxweight']):
        pos = data['positions'][i]
        if data['weight'][pos] <= free_weight:
            free_weight -= data['weight'][pos]
            value += data['profit'][pos]
            isSol = value >= data['wanted']
        else:
            mult = free_weight/data['weight'][pos]
            value += data['profit'][pos] * mult
            isSol = True
        i += 1
    if value >= data['wanted']:
        return "PUEDE"
    else:
        return "TOS"

#Función para obtener los ratios ordenados en otro campo del diccionario por índice
def position_sort(data):
    tuplas = []
    for i in range(len(data['ratio'])):
        tuplas.append((data['ratio'][i], i))
    tuplas.sort(reverse=True)
    for i in range(len(data['ratio'])):
        data['positions'].append(tuplas[i][1])


data = {
    'profit': [],
    'weight': [],
    'ratio': [],
    'positions': [],
    'wanted': 0,
    'maxweight': 0
}

n_almendras, n_pruebas = map(int, input().strip().split())

for _ in range(n_almendras):
    nutriente, gramos = map(int, input().strip().split())
    data['profit'].append(nutriente)
    data['weight'].append(gramos)
    data['ratio'].append(float(nutriente/gramos))

position_sort(data)


for _ in range(n_pruebas):
    max_nutriente, max_gramos = map(int, input().strip().split())
    data['wanted'] = max_nutriente
    data['maxweight'] = max_gramos

    print(almendrita(data))
```
