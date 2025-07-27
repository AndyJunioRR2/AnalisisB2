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
## Implementación básica

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





