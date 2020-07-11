---
layout: article
title: Diseño de algoritmos
date: 2020-07-10 
author: Tomás Segura
coverPhoto: https://humanoriginproject.com/wp-content/uploads/2018/12/human-chromosome-function.jpg
---


El diseño consiste en el planeamiento de un producto cuyo fin es es mostrar la apariencia y funciones de un objeto antes de su construcción.

![Think before you act](https://www.accuform.com/files/damObject/Image/huge/MGNF921.jpg)

El proceso del diseño de algoritmos lleva algunos pasos significantes:

:bulb: Formular el problema con suficiente precisión matemática.
:bulb: Concretar la pregunta y comenzar a pensar en algoritmos para solucionar.
:bulb: Diseñar el algoritmo para el problema.
:bulb: Analizar el algoritmo para verificar si es correcto.
:bulb: Evaluar la eficiencia del resultado.

Ahora bien, este proceso de formulación de algoritmos se complementa de algunas **técnicas de diseño** particulares. Familiarizarse con ellas lleva su tiempo pero con la experiencia se vuelve más sencillo solucionar problemas. Algunas categorías de técnicas de diseño son:

![esquema resumen de diseño de algoritmos](https://mermaid.ink/img/eyJjb2RlIjoiZ3JhcGggTFIgXG5pZDAwW1TDiUNOSUNBUyBERSBESVNFw5FPXVxuaWQwMCAtLT4gaWQwMVxuaWQwMCAtLT4gaWQwM1xuaWQwMCAtLT4gaWQwNVxuaWQwMCAtLT4gaWQwN1xuaWQwMCAtLT4gaWQxMVxuXG5pZDAxW0RpdmlkZSB5IHZlbmNlcsOhcy5dXG5pZDAzW0JhY2t0cmFja2luZy5dXG5pZDA1W1Byb2dyYW1hY2nDs24gZGluw6FtaWNhLl1cblxuaWQwN1tBbGdvcml0bW9zIGhldXLDrXN0aWNvcy5dXG5pZDA4W0FsZ29yaXRtb3MgZ2Vuw6l0aWNvcy5dXG5pZDA5W0FsZ29yaXRtb3MgVm9yYWNlcy5dXG5cbmlkMDcgLS0-IGlkMDhcbmlkMDcgLS0-IGlkMDlcblxuaWQxMVtBbGdvcml0bW9zIHByb2JhYmlsw61zdGljb3MuXSIsIm1lcm1haWQiOnsidGhlbWUiOiJkZWZhdWx0In0sInVwZGF0ZUVkaXRvciI6ZmFsc2V9)

## Divide y vencerás (Divide and Conquer).

El proceso se interpreta de forma literal a su nombre. Tal como se aprecia en el siguiente ejemplo gráfico sobre el algoritmo de ordenamiento [merge sort]([https://medium.com/@pedro.nunes.loureiro/merge-sort-61c9ff5bb00d](https://medium.com/@pedro.nunes.loureiro/merge-sort-61c9ff5bb00d)):
![enter image description here](https://miro.medium.com/max/671/1*YrPtgdrrKHbLE2bVT2tupw.png)

El proceso se puede resumir de la siguiente manera:
1. Dividir el problema en subproblemas.
2. Conquistar los subproblemas de **forma recursiva**.
3. Combinar las soluciones.
4. Al alcanzar el problema más pequeño posible, **se definen los casos base** y se trabaja a partir de ahí.
5. Es altamente eficiente.

Este principio **busca múltiples soluciones de forma paralela.**

> [Khan Academy](https://www.khanacademy.org/computing/computer-science/algorithms/merge-sort/a/divide-and-conquer-algorithms) explica más este tema.

Algunos algoritmos que utilizan Divide y vencerás son:
- Quicksort.
- Strassen's Algorithm: multiplica dos matrices.
- Karatsuba Algorithm: permite multiplicar números muy grandes usando pequeñas tres multiplicaciones pequeñas.

## Backtracking.
El backtracking **consiste en una técnica para probar secuencias de decisiones hasta encontrar la correcta.** Puede terminar sin una solución.

La técnica de backtracking prueba decisiones y si encuentra una incorrecta entonces se devuelve. Parecido a caminar en un laberinto.

![3d maze](https://4.bp.blogspot.com/-gAwapNpsCRs/VtAv6B3hGVI/AAAAAAAAXsg/0PszZrXAhRU/s1600/laberinto-cubo-3d.gif)

Cuando caminamos por un laberinto y topamos con un camino cerrado (*solución incorrecta*) entonces nos devolvemos hasta la último camino correcto y escogemos otra ruta (*recursivamente*). Este es el principio del backtracking.

Las soluciones se pueden ver como un árbol de decisiones. Esto nos da un indicativo de que este algoritmo es recursivo.

![decision tree](https://elf11.github.io/images/decisionTree.png)

En [gestión de operaciones](https://www.gestiondeoperaciones.net/procesos/arbol-de-decision/) lo definen así:

> Es un método analítico que a través de una representación esquemática de las alternativas disponible facilita la toma de mejores decisiones, especialmente cuando existen riesgos, costos, beneficios y múltiples opciones. El nombre se deriva de la apariencia del modelo parecido a un árbol y su uso es amplio en el ámbito de la toma de decisiones bajo incertidumbre (**Teoría de Decisiones**) junto a otras herramientas como el **Análisis del Punto de Equilibrio.**

Los árboles de decisiones se caracterizan por:
- Plantear una pregunta en un nodo.
- Las ojas de esa raíz se convierten en soluciones.
- Los árboles básicos se plantean de forma binaria. Donde **la hoja izquierda es 1 y la derecha 0**.

Si un nodo conduce solo a errores, se retorna al nodo padre y se evaluan otros nodos. **Encuentra todas las soluciones posibles**. Se usa en lenguajes como Prolog.

> En caso de que te interese [GeekForGeeks](https://www.geeksforgeeks.org/top-20-backtracking-algorithm-interview-questions/) hizo una lista de las principales 20 preguntas sobre Backtracking  en entrevistas de trabajo.

Algunos problemas clásicos del backtracking son:
- Sudoku.
- N Queens Problem.
- Letter combination phone.
- The Knight’s Tour Problem.
- Coloring Graph Problem.

### N Queens Problem (problema de las n reinas).

 Consiste ubicar las $n$ reinas  en una matriz de $n*n$ sin que se relacionen en la misma diagonal, horizontal o vertical. 

Debido a que este problema se amplía mucho al desarrollarlo, recomiendo ver el siguiente video:

{% include youtube_embed.html id="0DeznFqrgAI" %}

> [Aquí](https://www.geeksforgeeks.org/n-queen-problem-backtracking-3/) se puede acceder al código y la explicación.

### Letter combination phone.

Dado un string que contiene dígitos [2, 9] inclusivo. Retorne todas las posibles combinaciones de las letras que representa cada uno de los dígitos. 

![Nokia 1200](https://tag-approved.co.uk/wp-content/uploads/2016/06/nokia-c-on-1.jpg)

**Por ejemplo:**
```python
> Input: "23"
Output: ["ad", "ae", "af", "bd", "be", "bf", "cd", "ce", "cf"].
```
## Programación dinámica.
Método para resolver problemas dividiéndolos en problemas más simples, con el fin solucionar problemas más complejos.

Algunas características son:
- Subestructura óptima: cada solución de un problema es óptima.
- **Overlapping de problemas**: el espacio de los subproblemas debe ser pequeño y se tiene que resolver el mismo subproblema una y otra vez.
- Se diferencia de Divide y vencerás porque se reutilizan los resultados.
- Cada vez que se soluciona un problema se guarda el resultado en una tabla.
- Al solucionar un problema nuevo, se revisa la tabla y si no está entonces proceso  y guardo la solución.

> But unlike, divide and conquer, these sub-problems are not solved independently. Rather, results of these smaller sub-problems are remembered and used for similar or overlapping sub-problems.

Tal como lo indica [Tutorials Point]([https://www.tutorialspoint.com/data_structures_algorithms/dynamic_programming.htm](https://www.tutorialspoint.com/data_structures_algorithms/dynamic_programming.htm)) la principal característica que  tienen los problemas en que se implementa este proceso es **el problema se debe poder dividir en *subproblemas similares*.** Es así como este diseño de algoritmos se vuelven eficientes. Además, **son algoritmos de optimización**.

Estos son algunos ejemplos clásicos que se pueden resolver usando programación dinámica:
-   Fibonacci number series.
-   Knapsack problem.
-   Tower of Hanoi.
-   All pair shortest path by Floyd-Warshall.
-   Shortest path by Dijkstra.
-   Project scheduling.

### Algoritmo de la mochila (0-1 the Knapsack Problem).
Se tiene una mochila con un máximo de peso con el que se puede cargar. Todos los productos disponibles tienen un valor de precio y peso. Consiste en un problema de optimización. Es decir, ganar el mayor valor posible dentro del peso aceptado.

En el siguiente artículo de [medium](https://medium.com/@fabianterh/how-to-solve-the-knapsack-problem-with-dynamic-programming-eb88c706d3cf) desarrollan de forma muy clara la aplicación de la programación dinámica para resolver este problema.

### La torre de Hanoi (Tower of Hanoi).
Consiste en que se tienen tres ejes en los que se colocan aros circulares con diferentes diámetros. **Solamente un aro de menor diámetro por encima de otro de mayor**. Todos los aros comienzan en el eje más izquierdo y el participante debe pasarlos al eje derecho siguiente la condición de orden. También trata de un problema de optimización. 

![Tower of Hanoi](https://image.winudf.com/v2/image1/am9oYW4ubW9sbGVyLnRvd2Vyb2ZoYW5vaV9zY3JlZW5fMF8xNTY3MDAwNDE4XzAyNg/screen-0.jpg?fakeurl=1&type=.jpg)

> Recomiendo muchísimo jugar [Tower of Hanoi](https://www.mathsisfun.com/games/towerofhanoi.html). Es un gran ejercicio para la lógica.

Se puede encontrar mucha información al respecto pero [edpresso](https://www.educative.io/edpresso/what-is-the-tower-of-hanoi-problem#:~:text=The%20Tower%20of%20Hanoi%2C%20is,to%20a%20cone%2Dshaped%20tower.) lo resume muy bien.

## Heuristic Algorithms (heurísticos).

Estos algoritmos que se caracterizan por garantizar que están muy cerca de ser óptimos. **Se utilizan en escenarios donde la precisión puede ser sacrificada por rendimiento**. 

Algunos ejemplos son:
- Genetic algorithms.
- Greedy algorithms.

### Genetic algorithms (algoritmos genéticos).

Los algoritmos genéticos consisten en un tipo de **búsqueda heurística** basada en la teoría de Darwin que dice que el que sobrevive es el que tiene las mejores características para adaptarse al medio, y combina esa idea de la evolución con la genética. Se basa en la utilización de mecanismos que imitan a la evolución biológica para formular  los pasos a seguir.

> En caso de tener interés en repasar la teoría de evolución de Darwin, [este](https://www.youtube.com/watch?v=xfY_Jw_2I8c) video explica la historia.

Es una técnica robusta y **puede tratar con éxito una gran variedad de problemas provenientes de diferentes áreas**. Aplicaciones  en sistemas de computación paralelos, química, negocios y comercio (modelización de sistemas económicos complejos, predicción de mercados), entre otros.

**Fue desarrollado por Dr. John Henry Holland (1929 - 2015)**. Un pionero en sistemas complejos y ciencia no lineal. También es conocido como el padre del Algoritmo genético. Profesor de Filosofía, de Ingeniería Eléctrica y de Ciencias de la computación en la Universidad de Míchigan.

![John Henry holland](https://static01.nyt.com/images/2015/08/20/us/20holland-obit/20holland-obit-jumbo.jpg)

En la naturaleza todo el proceso de evolución se hace de forma natural. Aplicar esta idea a la solución de problemas conlleva algunas implicaciones en la población generada:

:bulb: **Tamaño**.
:bulb: **Diversidad**.

Estos dos factores son fundamentales ya que permiten la correcta generación de las mutaciones entre generaciones.

Representa una exploración aleatoria usando información histórica de las generaciones para dirigir la búsqueda. Se busca una **función fitness** que se encarga de crear una nueva generación con los cambios correspondientes.

**Algunas definiciones importantes son:**
- **Cell:** contiene los cromosomas (cadena ADN).
- **Chromosome:** conjunto de genes (bloques de ADN).
- **Genotype:** colección de genes responsables de un rasgo.
- **Reproducción:** combinación de genes padre.
- **Mutación:** alteraciones durante la reproducción.
- **Fitness:** cuánto se puede reproducir antes de morir.

En este video se muestra un excelente ejemplo de los algoritmos genéticos. Donde se crean generaciones de carros con ciertas características. Estas van evolucionando usando "the fittest car" como base. Este término "the fittest" se utiliza para hacer referencia al individuo de mayor éxito de cierta generación.

{% include youtube_embed.html id="d92aCvexE1U" %}

**El proceso de los algoritmos genéticos se puede resumir en**:
1. **Generar una población base**. Puramente aleatoria.

2. **Selección**. Tras evaluar la generación, es decir mandar los individuos a la guerra, **se aplica la función fitness** para escoger quienes se pueden reproducir.

3. **Crossover**. Reproducir los individuos seleccionados por cruce. Se reproducen entre ellos.

4. **Mutaciones.** Se mutan algunas características de la generación base con el fin de incrementar la segunda población.

5. **Mezclar**. Se combina la población que se origina de los cruces con la población originada tras mutar la población base.

6. El algoritmo termina cuando no se puedan generar individuos significativamente diferentes. Entonces se dice que el algoritmo ha propuesto un set de soluciones al problema. Sino se continua con el ciclo.

Hay varios aspectos que son importantes a la hora de implementar este algoritmo:
- El tamaño de la población depende del problema.
- Una población pequeña puede crear un máximo limitante pero una población demasiado grande requiere de muchos recursos computacionales.
- Para las reproducciones se define un padre y una madre.

 [Vijini Mallawaarachchi](https://towardsdatascience.com/@vijinimallawaarachchi?source=post_page-----e396e98d8bf3----------------------) desarrolla un poco más los algoritmos genéticos y muestra un ejemplo en código.

Algunos problemas clásicos en los que se utilizan estos algoritmos son:
- [Travelling Salesman Problem.](https://www.geeksforgeeks.org/traveling-salesman-problem-using-genetic-algorithm/)
- Cashier Problem.

### Greedy algorithms (algoritmos voraces).

Los algoritmos voraces usan la filosofía de construir una solución a partir de pequeños pasos. En cada paso toma una decisión que los lleva gradualmente a una decisión final. Estos algoritmos **siempre escogen la opción que se ve mejor en el momento**. Esto quiere decir que una decisión local óptima se espera que lleve a una decisión global óptima.

En algunos casos, esta meta no es alcanzada y la solución final no es óptima. Igualmente, se obtiene una aproximación. Aún así, **son algoritmos rápidos**. 

**Los principales componentes son:**
1. **Set de candidatos.** A partir de este se creará la solución.

2. **Selección.** Esta función escoge los mejores candidatos para agregarlos a la solución.

3. **Factibilidad.** Esta función se utiliza para determinar si un candidato puede ser utilizado para contribuir a la solución.

4. **Objetivo.** Corresponde a la función encargada de asignar un valor a la solución global o parcial.

5. **Solución.** Se encarga de indicar cuándo se ha finalizado con la solución global.

Algunos problemas en los que se aplican algoritmos voraces son:
- Dijkstra Algorithm.
- Find largest sum.
- Cashier Algorithm.
- Kruskal and Prim Minimum Spanning Tree.
- Huffman Coding.
- Traveling Salesman Problem.

## Algoritmos probabilísticos.

Esta consiste en una técnica de diseño de algoritmos en la cual **se utilizan números al azar para decidir qué hacer**. Requieren de demasiados recursos computacionales para encontrar una solución óptima. 

Inclusive con el mismo input, estos algoritmos varían su comportamiento en cada ejecución.

**Categorías:**
- Numéricos: 
	- Solución aproximada.
	- 90% de probabilidades de dar una solución correcta.
	- Cuanto más se ejecuta más se incrementa la probabilidad.
- Las Vegas:
	- Toma decisiones random.
- Monte Carlo: 
	- Calcula la mejor solución de un alto grado de probabilidad.
	- Cuanto más se ejecuta más se incrementa la probabilidad.

En caso de querer ampliar el tema: [science4all](http://www.science4all.org/article/probabilistic-algorithms/).

Ejemplos de algoritmos de este tipo:
- Hashing.
- Sorting.
- Searching.
- Load Balancing.
- Minimum spanning trees.
- Shortest paths.

![Mountastic  footer](https://user-images.githubusercontent.com/38998436/87217793-5fa59d80-c30a-11ea-94e7-81be3d541319.png)

