---
layout: article
title: Algoritmos de búsqueda
date: 2020-07-05 
author: Tomás Segura
coverPhoto: https://lh3.googleusercontent.com/proxy/CCWT6HwNdt6lPr_PHenr9e8DV4E0ip6FB6whRkGJn4R55nZsqkRxL5E3T50_ShCW51t5UEQh5_-BMMmRUC0DtxXYI-KUU_gPg_nB0my1KxihBv9X9DABqN2CY_D38_5ljm-tF5g
---

### Linear search (búsqueda secuencial).
- **Complejidad $$\Omicron(n)$$ (en el peor de los casos se hará un número de comparaciones igual al tamaño del elemento)**.
- Es el algoritmo de búsqueda más sencillo.
- Busca un elemento en una lista o un vector.

![Algoritmo de búsqueda secuencial GIF](https://www.tutorialspoint.com/data_structures_algorithms/images/linear_search.gif)

### Binary Search (búsqueda binaria).
- Busca un número en un **arreglo ordenado**.
- Compara el elemento buscado con el central.
- Si el central es el elemento buscado, termina.
- Si el central es menor que el buscado, se realiza la búsqueda en la mitad supeior.
- Si el central es mayor, se realiza la búsqueda en la mitad inferior.

![Gif sobre binary search vs linear search](https://blog.penjee.com/wp-content/uploads/2015/04/binary-and-linear-search-animations.gif)

### Interpolation search (interpolación).
- **Complejidad $$\Omicron(n)$$**.
- Modificación de binary search.
- El código es prácticamente el mismo, a excepción del cálculo del elemento central.
- En cada etapa, trata de calcular dónde está el elemento central (con un pivote) usando la fórmula:

$$\ middle = low + \frac{ (buscado - a[low]) (high - low)}{a[high] - a[low]}$$

En [este visualizador](http://lti.cs.vt.edu/OpenDSA/AV/Development/interpolationSearchAV.html) se puede observar el desarrollo del algoritmo.

### Hashing (Hash).
- Mapea grandes data sets a unos más pequeños.
- Provee una forma de búsqueda rápida.
- Determina una función de *Hash* que permite buscar y encontrar un *índice* para una *llave*.

$$\ f(llave)$$ *----->* *índice único*
- **Se puede aplicar en encriptación** (SHA -256 o MD5).
- La forma más básica de un Hash es la función identidad.
- La función ideal es inyectiva y biyectiva, pero es muy difícil de hallar.

**Técnicas de Hash:**
- Restas sucesivas.
- Aritmética modular.
- Cuadrado medio.
- Truncado.
- Folding.

**Colisiones:**
- Una colisión es cuando una función tiene la misma imagen para distintas preimágines. Es decir, **dos o más llaves tienen el mismo índice.**
- Una tabla hash con muchas llaves es un causante de colisiones.
- Es difícil de evitar.

[Aquí](https://medium.com/tech-tales/what-is-hashing-6edba0ebfa67) se puede leer un artículo sobre el hash con el fin de aclarar más la definición y algunos usos en la encriptación de contraseñas y seguridad. Demasiado interesante, súper recomendado para leer.

### Pathfinding.
![Pathfinding](https://user-images.githubusercontent.com/38998436/86526063-5f119080-be4c-11ea-9872-373c9c12d2d5.png)
[Aquí](https://www.goconqr.com/en/mindmap/23461528/PATHFINDING) se puede  acceder a una vista dinámica del esquema.

El Pathfinding es la búsqueda de la ruta más corta entre dos puntos mediante métodos computacionales. Está basado en el [algoritmo de Dijkstra]([https://www.geeksforgeeks.org/dijkstras-shortest-path-algorithm-greedy-algo-7/](https://www.geeksforgeeks.org/dijkstras-shortest-path-algorithm-greedy-algo-7/)). 

El procedimiento se caracteriza por:
- Explora los nodos adyacentes y selecciona los más cercanos.
- Trabaja sobre una matriz, cada celda es un nodo.
- Es capaz de resolver laberintos.

Existen diferentes algoritmos para implementar el pathfinding. A continuación se muestran algunos.

{% mermaid %}
graph LR;
id00[IMPLEMENTACIONES];
id00 --> id01;
id00 --> id03;
id00 --> id05;
id00 --> id07;
id00 --> id11;
id00 --> id13;

id01[Sin obstáculos.];
id02[Mover los ejes de posición hasta igualar x,y al buscado.];

id01 --> id02;

id03[Random Bouncing.];
id04[Fuerza bruta.];

id03 --> id04;

id05[Object Tracing.];
id06[Rodear obstáculos.];

id05 --> id06;

id07[Breadth-first Search];
id08[Onda expansiva para detectar celdas alrededor.];
id09[Ineficiente.];
id10[Prueba con los nodos adyacentes y guarda las posiciones de los obstáculos hasta llegar al objetivo.];

id07 --> id08;
id07 --> id09;
id07 --> id10;

id11[Better heuristic pathfinding];
id12[Explicación abajo.];

id13[A*];

id11 --> id12;
id13 --> id12;
{% endmermaid %}


Los algoritmos Better Heuristic y A* son un poco más complicados e importantes. Por esto, se desarrollan un poco más.

#### Better Heuristic Algorithm (algoritmos heurísticos).

El término heurístico se utiliza cuando se hace referencia a una optimización de un algoritmo. En este caso, el pathfinding. Esta idea está más desarrollada [Northwestern University Open Text Book on Process Optimization]([https://optimization.mccormick.northwestern.edu/index.php/Heuristic_algorithms#:~:text=A%20heuristic%20algorithm%20is%20one,a%20class%20of%20decision%20problems.](https://optimization.mccormick.northwestern.edu/index.php/Heuristic_algorithms#:~:text=A%20heuristic%20algorithm%20is%20one,a%20class%20of%20decision%20problems.)) que lo describen así:

> A heuristic algorithm is one that is designed to solve a problem in a faster and more efficient fashion than traditional methods by sacrificing optimality, accuracy, precision, or completeness for speed.

Es muy importante destacar que para alcanzar el objetivo de optimización es posible que se sacrifiquen aspectos como: exactitud o presición. Esto porque **el enfoque es la velocidad**.
 
Se concentra en tomar la mejor decisión, es decir, que tarde menos tiempo en cálculos para la obtención de la ruta más corta. **No encontrará la ruta más óptima** pero sí algunas de las más cortas. 

El término, en la computación, también se utiliza para desribir soluciones más "inteligentes" que las originales.

Algunos de los algoritmos heurísticos más conocidos son:
- Swarm intelligence (inteligencia de enjambre).
- Artificial neural networks (redes neuronales).
- Genetic algorithms (algoritmos genéticos).

Estos algoritmos se pueden aplicar en el escaneo de virus en una computadora y como algoritmos de búsqueda y ordenamiento.

#### A* (A star).

Este es un algoritmo conocido por ser **preciso, rápido y confiable**. Se utiliza mucho en el desarrollo de videojuegos.

Como es un algoritmo derivado del principio del pathfinding, hace uso de una matriz para el cálculo de rutas. Las celdas las divide de la siguiente manera:
- Red wall.
- Blue goal.
- Green start.
- id: caminado / no caminado.

El proceso para entender este algoritmo lo explica [Computerphile]([https://www.youtube.com/watch?v=ySN5Wnu88nE](https://www.youtube.com/watch?v=ySN5Wnu88nE)) en su canal, pero recomiendo ver el video del  [algoritmo de Dijkstra]([https://www.youtube.com/watch?v=GazC3A4OQTE](https://www.youtube.com/watch?v=GazC3A4OQTE)) primero. 

A modo de resumen, la diferencia principal entre el algoritmo de Dijkstra y A* es:

**Dijkstra**: Es **expansivo** (busca todas las rutas posibles).
![gif del algoritmo de Dijkstra](https://reactjsexample.com/content/images/2019/10/dijkstra.gif)

**A star**: Es **selectivo** (escoge gradualmente las rutas más efectivas).
![Gif del algoritmo A*](https://camo.githubusercontent.com/8ce41f7333960e48f5d1e5b4f1a2a72908288231/687474703a2f2f672e7265636f726469742e636f2f51784d44503679577a422e676966)

Aplicar este algoritmo implica conocer los principales cálculos, como lo indica [Graph Everywhere]([https://www.grapheverywhere.com/algoritmo-a/](https://www.grapheverywhere.com/algoritmo-a/)), donde también se puede encontrar un ejemplo de apliación y un poco de historia:

> Para la aplicación de este algoritmo debemos comprender como se procede a dividir el costo de la ruta. En este caso se divide en dos partes donde $$g(n)$$ representa el costo de la ruta desde su origen hasta algún nodo n dentro del grafo. También tenemos que $$h (n)$$ representa el costo estimado de la ruta desde el nodo n al nodo de destino, calculado por una suposición inteligente.

**Por ejemplo:**
En el siguiente grafo, **el nodo origen sería A** y el **nodo destino es D**. 


{% mermaid %}
graph TB;
A((A)) -- 5 --> B((B));
A -- 4 --> C((C));
B -- 9 --> D((D));
C -- 3 --> G((G));
G -- 2 --> D;
C -- 9 --> F((F));
F -- 14 --> D;
{% endmermaid %}

Entonces, algunos valores $$g(n)$$ serían:
- *Del nodo C*: $$g(n) = 4$$.
- *Del nodo B*: $$g(n) = 5$$.
- *Del nodo F*: $$g(n) = 13$$.
- *Del nodo G*: $$g(n) = 7$$.

Por lo tanto, **$$g(n)$$ básicamente es el valor que cuesta llegar a un nodo por la suma de las aristas**. Luego, $$h(n)$$ es un valor aproximado. El método para calcular este valor varía según su aplicación. Por ejemplo, si fuera una aplicación de rutas como Google Maps entonces una posibilidad es que se calcula la línea recta (en metros)  desde un nodo hasta el nodo destino. 

Para este ejemplo definiré $$h(n)$$ de la siguiente manera: el mínimo de aristas faltantes para llegar al nodo. Entonces algunos valores quedarían así:
- *Del nodo C*: $$h(n) = 2$$.
- *Del nodo B*: $$h(n) = 1$$.
- *Del nodo F*: $$h(n) = 1$$.
- *Del nodo G*: $$h(n) = 1$$.

Ahora, el único valor faltante sería $$f(n)$$ el cual se define como 
$$f(n) = h(n) + g (n)$$ 
Por lo tanto, los valores quedarían así:
- *Del nodo C*: $$f(n) = 6$$.
- *Del nodo B*: $$f(n) = 6$$.
- *Del nodo F*: $$f(n) = 14$$.
- *Del nodo G*: $$f(n) = 8$$.

El objetivo que se obtenga el $$f(n)$$ más bajo posible. Para ver una expliación sobre un proceso completo de A* recomiendo [este](https://www.youtube.com/watch?v=PzEWHH2v3TE) video. 

{% include youtube_embed.html id="PzEWHH2v3TE" %}

