# AnalisisB2
## 1. Algoritmos y Probabilidad

Los algoritmos no siempre siguen caminos deterministas y predecibles. En el mundo de la computación moderna, existen enfoques en los que la incertidumbre y el azar juegan un papel central: los **algoritmos probabilísticos**.

## ¿Qué son los algoritmos probabilísticos?

Se trata de algoritmos que incorporan el azar como parte de su funcionamiento. A diferencia de los algoritmos deterministas, que producen el mismo resultado para una entrada dada, los algoritmos probabilísticos pueden ofrecer distintos resultados en ejecuciones diferentes, incluso si la entrada no cambia.

Esto se debe a que estos algoritmos hacen uso de generadores de números aleatorios para tomar decisiones durante su ejecución.

## ¿Por qué utilizar la probabilidad en algoritmos?

Los beneficios de emplear algoritmos probabilísticos emergen principalmente cuando se enfrentan los siguientes escenarios:

- **Alta complejidad computacional**: cuando una solución exacta requiere demasiado tiempo o recursos.
- **Problemas mal definidos o dinámicos**: donde los datos cambian o son ruidosos.
- **Necesidad de respuestas rápidas**: cuando una solución buena es preferible a una solución óptima que llegue demasiado tarde.
- **Ausencia de métodos deterministas eficientes**: en ciertos dominios, simplemente no existen algoritmos deterministas prácticos.

## Clasificación de algoritmos probabilísticos

Los algoritmos basados en probabilidad se dividen, principalmente, en dos categorías:

### 🔹 Algoritmos de tipo Monte Carlo

- **Resultado**: No siempre es correcto.
- **Ventaja**: Tienen tiempos de ejecución limitados y controlables.
- **Uso típico**: Problemas donde se puede aceptar cierto margen de error a cambio de mayor velocidad.
- **Ejemplo**: Algoritmos para verificar si un número es primo.

### 🔹 Algoritmos de tipo Las Vegas

- **Resultado**: Siempre correcto.
- **Inconveniente**: El tiempo de ejecución es impredecible.
- **Uso típico**: Problemas donde no se puede permitir un resultado erróneo, pero sí variar el tiempo que se tarda en obtenerlo.
- **Ejemplo**: QuickSort con pivote aleatorio.

## Aplicaciones prácticas

El uso de algoritmos probabilísticos se extiende a muchos campos:

- **Seguridad informática y criptografía**: generación de claves, protocolos seguros.
- **Simulación y modelado**: métodos de Monte Carlo para simulaciones físicas o financieras.
- **Biología computacional**: búsqueda de secuencias genéticas.
- **Gráficos por computadora**: para simular fenómenos como el comportamiento de la luz.
- **Inteligencia artificial**: aprendizaje reforzado y redes bayesianas.

## Un ejemplo práctico: el dilema de la búsqueda

Imagina tener una base de datos no ordenada con millones de entradas. Un algoritmo determinista tendría que revisar cada elemento uno por uno. En cambio, un enfoque probabilístico podría hacer selecciones aleatorias y, con cierta probabilidad, encontrar la entrada buscada más rápido, especialmente si el valor aparece múltiples veces.

## Consideraciones importantes

### ✅ Ventajas

- Soluciones rápidas en promedio.
- Fáciles de implementar.
- Eficaces para problemas complejos o inciertos.

### ⚠️ Desventajas

- Resultado no garantizado (en algunos casos).
- Dependencia de una fuente fiable de aleatoriedad.
- Dificultad para analizar el peor caso de rendimiento.

## Reflexión final

La inclusión de la probabilidad en el diseño de algoritmos amplía significativamente las herramientas disponibles para los desarrolladores. Aunque pueda parecer contraproducente confiar en el azar, en muchos casos esta estrategia ofrece un equilibrio ideal entre eficiencia y precisión.

Los algoritmos probabilísticos enriquecen el panorama de paradigmas de resolución de problemas, y reflejan cómo la computación puede beneficiarse incluso de lo impredecible.

---
## 2. Paradigma: Divide y Vencerás  
## Caso aplicado: Búsqueda Binaria

La programación algorítmica cuenta con varios paradigmas poderosos para resolver problemas. Uno de los más conocidos es **Divide y Vencerás**, una estrategia que ha dado lugar a algunos de los algoritmos más eficientes. En esta ocasión, exploraremos cómo este paradigma se aplica en la **búsqueda binaria**, una técnica fundamental en la informática.

## ¿En qué consiste el paradigma de Divide y Vencerás?

Este enfoque divide un problema complejo en subproblemas más pequeños y más manejables. Luego, se resuelve cada subproblema (a menudo de forma recursiva), y finalmente se combinan las soluciones parciales para obtener el resultado final.

Las tres etapas principales son:

1. **Dividir**: Separar el problema en partes.
2. **Vencer (resolver)**: Resolver cada parte por separado.
3. **Combinar**: Integrar las soluciones de las partes para formar la solución total.

Este patrón está presente en algoritmos como MergeSort, QuickSort, Fast Fourier Transform (FFT), y también en **búsqueda binaria**.

## ¿Qué es la Búsqueda Binaria?

La **búsqueda binaria** es un algoritmo diseñado para buscar un elemento en una lista ordenada. En lugar de revisar todos los elementos uno por uno, el algoritmo descarta la mitad de la lista en cada paso.

### Idea básica

Dado un arreglo ordenado `A` y un valor `x` a buscar:

1. Se compara `x` con el elemento del medio.
2. Si son iguales, se encontró el elemento.
3. Si `x` es menor, se repite el proceso en la mitad izquierda.
4. Si `x` es mayor, se repite en la mitad derecha.

Este proceso se repite hasta encontrar el valor o hasta que el subarreglo sea vacío.

---

## Ejemplo: Prueba de Escritorio (nuevo)

### Tupla de entrada:
```python
T = [5, 12, 18, 27, 33, 41, 60, 73, 85, 99]
x = 41
```

### Pasos del algoritmo:

1. `Inicio = 0`, `Fin = 9`  
   `Mitad = (0 + 9) // 2 = 4 → T[4] = 33`  
   Como `41 > 33`, se busca a la derecha.

2. `Inicio = 5`, `Fin = 9`  
   `Mitad = (5 + 9) // 2 = 7 → T[7] = 73`  
   Como `41 < 73`, se busca a la izquierda.

3. `Inicio = 5`, `Fin = 6`  
   `Mitad = (5 + 6) // 2 = 5 → T[5] = 41`  
   ¡Elemento encontrado!

### Resultado:

El elemento `x = 41` se encuentra en la **posición 5** del arreglo.

---


---

## Complejidad del algoritmo

- **Tiempo**: O(log n)  
- **Espacio**: O(1) (versión iterativa) u O(log n) (versión recursiva)

La eficiencia del algoritmo es producto del paradigma de **divide y vencerás**, que reduce el tamaño del problema a la mitad en cada iteración.

## Ventajas de la búsqueda binaria

- Muy rápida en arreglos ordenados.
- Fácil de implementar.
- Ideal para grandes volúmenes de datos.

## Limitaciones

- Solo funciona en estructuras ordenadas.
- Requiere acceso aleatorio a los elementos (por ejemplo, en arreglos; no en listas enlazadas).
- Puede ser menos eficiente que una búsqueda lineal si el conjunto es muy pequeño.

## Aplicaciones comunes

- Verificación rápida de existencia en bases de datos.
- Localización de límites o umbrales (por ejemplo, en problemas de optimización).
- Implementación de estructuras como árboles de búsqueda binaria (BST).
- Uso en librerías estándar (`binary_search` en C++, `bisect` en Python).
## Implementación básica (Iterativa)

La búsqueda binaria puede implementarse de distintas formas, pero una de las más comunes es el enfoque iterativo, el cual utiliza un bucle para reducir progresivamente el intervalo de búsqueda.

A continuación, se muestra una versión en Java que realiza esta tarea. El algoritmo parte del arreglo ordenado y compara el valor objetivo con el elemento central. Dependiendo del resultado, se descarta la mitad izquierda o derecha del arreglo, repitiendo el proceso hasta encontrar el elemento o agotar las opciones.

```java
public static int busquedaBinaria(int[] arreglo, int x) {
    int inicio = 0;
    int fin = arreglo.length - 1;

    while (inicio <= fin) {
        int mitad = (inicio + fin) / 2;

        if (arreglo[mitad] == x)
            return mitad; // Elemento encontrado
        else if (x < arreglo[mitad])
            fin = mitad - 1; // Buscar en la mitad izquierda
        else
            inicio = mitad + 1; // Buscar en la mitad derecha
    }
    return -1; // Elemento no encontrado
}
```

## Reflexión final

La **búsqueda binaria** es un claro ejemplo de cómo el paradigma de **divide y vencerás** puede transformar una operación aparentemente simple como buscar un número, en una operación altamente eficiente. Al reducir el espacio de búsqueda a la mitad en cada paso, se consigue un rendimiento excelente en escenarios donde la rapidez es clave.

Comprender este paradigma no solo mejora nuestras habilidades de resolución de problemas, sino que también nos brinda herramientas para diseñar algoritmos elegantes y poderosos.
---
## 3. Merge Sort – Ordenamiento por Mezcla

## ¿Qué es Merge Sort?

**Merge Sort** es un algoritmo de ordenamiento que sigue el paradigma de **Divide y Vencerás**. Es eficiente, estable y garantiza un rendimiento de O(n log n) en todos los casos.

Este algoritmo divide una lista en sublistas más pequeñas, ordena cada una de ellas y luego las combina (fusiona) en una lista final ordenada.

---

## 🔧 Principio del algoritmo

1. **División**: Se divide la lista en dos mitades.
2. **Conquista**: Se ordenan recursivamente ambas mitades usando el mismo algoritmo.
3. **Combinación**: Se fusionan ambas mitades ordenadas en una nueva lista ordenada.

---

## Representación simplificada del algoritmo

```python
función mergeSort(lista):
    si longitud(lista) ≤ 1:
        retornar lista
    mitad = longitud(lista) / 2
    izquierda = mergeSort(lista[0:mitad])
    derecha = mergeSort(lista[mitad:])
    retornar merge(izquierda, derecha)

función merge(izquierda, derecha):
    resultado = []
    mientras izquierda y derecha no estén vacías:
        si izquierda[0] < derecha[0]:
            agregar izquierda[0] a resultado
            eliminar izquierda[0]
        sino:
            agregar derecha[0] a resultado
            eliminar derecha[0]
    agregar elementos restantes de izquierda y derecha a resultado
    retornar resultado
```

---

## ✅ Ventajas

- Rendimiento garantizado O(n log n)
- Estable: mantiene el orden relativo de elementos iguales
- Funciona bien con listas enlazadas
- Predecible incluso en el peor caso

## ⚠️ Desventajas

- Requiere espacio adicional (arreglos auxiliares)
- Puede ser más lento que algoritmos como QuickSort para listas pequeñas
- Mayor complejidad de implementación

---

## 📌 Aplicaciones comunes

- Sistemas de archivos y bases de datos que requieren ordenamiento estable
- Grandes volúmenes de datos que no caben en memoria (ordenamiento externo)
- Algoritmos híbridos como **Timsort** (usado en Python y Java) que usan Merge Sort como parte de su lógica
- Ordenamiento en listas enlazadas

---

## Conclusión

**Merge Sort** es un algoritmo robusto, confiable y eficiente para el ordenamiento de listas. Su estructura basada en el paradigma *Divide y Vencerás* lo hace ideal para manejar grandes volúmenes de datos de manera predecible.

Aunque puede no ser el más rápido en todos los casos, su rendimiento consistente y su estabilidad lo convierten en una excelente opción cuando se necesita precisión y consistencia en el ordenamiento.

## 4. QuickSort – Ordenamiento Rápido

## ¿Qué es QuickSort?

**QuickSort** es un algoritmo de ordenamiento basado en el paradigma de **Divide y Vencerás**. Se destaca por su alta eficiencia en la práctica y su bajo consumo de memoria.

El algoritmo selecciona un elemento como pivote y divide el arreglo en dos partes: los elementos menores al pivote y los mayores. Luego, aplica el mismo procedimiento recursivamente a ambas sublistas.

---

## Principio del algoritmo

1. **División**: Elegir un elemento como pivote.
2. **Conquista**: Reorganizar los elementos de manera que los menores al pivote queden a su izquierda y los mayores a su derecha.
3. **Combinación**: Aplicar recursivamente QuickSort a las dos sublistas generadas.

---

## Representación simplificada del algoritmo

```python
función quickSort(lista):
    si longitud(lista) ≤ 1:
        retornar lista
    pivote = lista[0]
    menores = [elemento para elemento en lista[1:] si elemento < pivote]
    mayores = [elemento para elemento en lista[1:] si elemento ≥ pivote]
    retornar quickSort(menores) + [pivote] + quickSort(mayores)

```
---

## ✅ Ventajas

- Muy eficiente en promedio: O(n log n)
- No requiere memoria adicional significativa
- Generalmente más rápido que MergeSort para listas en memoria
- Fácil de implementar

## ⚠️ Desventajas

- Peor caso O(n²) si el pivote no se elige bien
- No es estable (puede cambiar el orden de elementos iguales)
- Rendimiento sensible a la elección del pivote

---

## 📌 Aplicaciones comunes

- Ordenamiento de grandes arreglos en memoria
- Sistemas que priorizan velocidad sobre estabilidad
- Implementaciones de ordenamiento estándar en muchos lenguajes (C, Java, etc.)
- Algoritmos híbridos como introsort

---

## Conclusión

**QuickSort** es uno de los algoritmos de ordenamiento más populares por su gran rendimiento promedio y bajo uso de memoria. Aunque su rendimiento puede degradarse en casos específicos, una buena elección de pivote y versiones optimizadas lo hacen extremadamente útil en aplicaciones reales.
---
## 5.  Algoritmos Voraces

## ¿Qué es un Algoritmo Voraz?

Un **algoritmo voraz** (o *greedy*) es una estrategia de diseño de algoritmos que toma decisiones paso a paso, eligiendo la opción que parece ser la mejor en ese momento sin reconsiderar decisiones anteriores.

El objetivo es construir una solución aproximada óptima o, en algunos casos, óptima exacta, tomando en cada paso la decisión más inmediata y favorable.

---

## 🔧 Principio del Algoritmo Voraz

1. Se divide el problema en etapas.
2. En cada etapa, se toma la mejor decisión local posible.
3. No se vuelve atrás ni se reconsideran decisiones anteriores.
4. Al final, la combinación de decisiones locales produce una solución global.

---

## Representación simplificada

```python
función algoritmoVoraz(problema):
    solución = solución vacía
    mientras problema no esté resuelto:
        elegir la mejor opción local disponible
        agregar esa opción a solución
    retornar solución

```
---

## ✅ Ventajas

- Fácil de implementar.
- Rápido, generalmente con complejidad polinomial.
- Funciona bien para muchos problemas prácticos.
- Ideal para problemas donde la elección local lleva a solución global óptima.
## ⚠️ Desventajas

- No garantiza la solución óptima para todos los problemas.
- Puede ser necesario analizar cuidadosamente si el enfoque voraz es adecuado.
- Algunas soluciones requieren técnicas más complejas (programación dinámica, backtracking).
---

## 📌 Aplicaciones comunes

- Problema de la mochila fraccionaria.
- Algoritmos de código Huffman para compresión.
- Selección de actividades que no se traslapan (problema de scheduling).
- Construcción de árboles de expansión mínima (Prim, Kruskal).
- Optimización en redes y rutas.

---

## Conclusión

Los **algoritmos voraces** son una herramienta poderosa para resolver problemas complejos de manera eficiente cuando las condiciones del problema permiten que las decisiones locales óptimas lleven a soluciones globales óptimas.

Sin embargo, su simplicidad también puede ser una limitación, y es crucial verificar que el problema en cuestión sea apto para esta estrategia antes de aplicarla.



