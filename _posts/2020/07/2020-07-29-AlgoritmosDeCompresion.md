---
layout: article
title: Algoritmos de Compresión.
date: 2020-07-29 
author: Tomás Segura
coverPhoto: https://cdn1.vectorstock.com/i/1000x1000/21/20/data-compression-vector-19122120.jpg
---


La compresión de Datos es el proceso mediante el cual se puede **disminuir el total de memoria necesaria para almacenar un archivo**. De este modo, la transferencia de los archivos es más rápida y almacenar un conjunto de archivos requiere menos memoria. 

Comprimir un archivo implica que debe poder ser descomprimido, [Loyvan](https://www.loyvan.com/informatica/que-es-la-compresion-de-datos/) resume este proceso:
> La compresión de datos implica la aplicación de un algoritmo que hace que algunos de los bits repetitivos sean innecesarios. Es un poco como una especie de mapa abreviado que se almacena con el archivo comprimido. Cuando el fichero es descomprimido, el mapa restaura todos los bits que faltan, reconstituyendo el archivo completo. Algunos tipos de ficheros se comprimen mejor que otros.

## Tipos de compresión.

### Lossless compression.
Reduce la información identificando y eliminando datos rendondantes. **No se pierde información.** Por lo tanto, el mensaje original puede ser recuperado tal cual era.

Algunos de estos algoritmos son:
- Huffman Code. 
- LZ77. 
- LZ78. 
- LZW.

### Lossy compression.
Consiste en el uso de algoritmos que identifican información innecesaria y la eliminan. Utiliza aproximaciones inexactas, por lo tanto no se puede recuperar el mensaje completo al decoficarlo. 

No obstante, algunos algoritmos **reducen significativamente el consumo de memoria antes de degradar notoriamente el archivo.**

Podría sonar un poco triste perder información en el proceso de compresión pero [Khan Academy](https://www.khanacademy.org/computing/computers-and-internet/xcae6f4a7ff015e7d:digital-information/xcae6f4a7ff015e7d:data-compression/a/lossy-compression) explica lo siguiente: 

> Computers can capture an incredible amount of detail in a photo—but how much of that detail can humans actually perceive? As it turns out, there's a lot of detail that we can remove. Lossy compression algorithms are all about figuring out clever ways to remove detail without humans noticing (too much).

Ahora cobra más sentido la situación. De hecho, hasta me siento mejor al respecto. Suena muy bien pensar que no estoy perdiendo valor significativo para mí pero estoy ganando espacio de memoria. Una situación muy importante, cuando utilizo Google Photos para almacenar mis recuerdos, por ejemplo.

Si todavía no estás convencido, observas estas dos imágenes:
> Figura 1:
![Image post lossy compression](https://cdn.kastatic.org/ka-perseus-images/acf4c90e754c7e8b2f4430908459fb6fca9e8fee.jpg)

>Figura 2:
![Image pre Lossy compression](https://cdn.kastatic.org/ka-perseus-images/249d175f16a1081aaeb64636b4a99ad988871b1d.jpg)

Resulta que la imagen con mayor calidad es la segunda ¿Notaste la diferencia? Realmente es poca. 

En caso de querer aprender más, recomiendo leer el artículo completo de [Khan Academy](https://www.khanacademy.org/computing/computers-and-internet/xcae6f4a7ff015e7d:digital-information/xcae6f4a7ff015e7d:data-compression/a/lossy-compression).

Las principales aplicaciones son:
- Multimedia (audio, video, fotos).
- Aplicaciones de streaming.

![Lossy compression example](https://bitmovin.com/wp-content/uploads/2020/03/LossyCompressionDoggo.jpeg)

---
> Un dato curioso es que el formato PNG usa lossless compression y JPEG usa lossy compression.
---
### Arithmetic Coding.
Usado en algoritmos lossless y lossy.  Los símbolos vistos con mayor frecuencia se codifican con menos bits que los menos utilizados. **Codifica el mensaje entero en un solo código compacto.**

## Huffman Code.

Según [EcuRed](https://www.ecured.cu/C%C3%B3digo_de_Huffman):

> La idea básica de los códigos de Huffman se basa en utilizar cadenas cortas de bits para los caracteres de uso frecuente y utilizar cadenas de bits de mayor tamaño para los caracteres que tienen una frecuencia de menor de uso.

Además, indica que se definen fácilmente  mediante un árbol con raíz. Este algoritmo creado en 1952 puede utilizarse para la compresión de imágenes, textos, entre otros.

David Huffaman desarrolló este algoritmo cuando era estudiante en el MIT durante 1950. 

Podría explicar cómo funciona el algoritmo pero no podría superar la sencillez ni el efecto visual de este video:

<iframe width="560" height="315" src="https://www.youtube.com/embed/JsTptu56GM8" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### ¿Cómo se aplica el código de Huffman en la vida real?
Huffman, a parte de diseñar este algoritmo, también demostró matemáticamente que es imposible encontrar una manera más eficiente de **comprimir un archivo de texto** letra por letra. Este es el principal uso que se le ha dado.  

La razón principal es la eficiencia que tiene para convertir la representación binaria estándar de un caracter a una propia del archivo mediante el árbol que genera en el proceso de compresión. Tal como lo explica Scott en su [video](https://www.youtube.com/watch?v=JsTptu56GM8).

Ahora bien, hoy en día los textos pueden ser analizados por bloques de caracteres (el principio que siguen los archivos actuales). 

### ¿Se puede aplicar el código de Huffman a la seguridad de la información? ¿Cómo?
Sí, tal como lo plantean  los autores del paper [A New Approach to Encryption using Huffman Coding](http://ijpsat.ijsht-journals.org/index.php/ijpsat/article/download/25/20)  donde analizan todo el proceso. Ellos desarrollan la idea de comprimir el texto que se desea encriptar y luego encriptarlo. De esta manera consiguen data más corta para encriptarla pero más complicada de desencriptar con ventajas como:
> - Es fácil de entender e implementar ya que se usan operaciones binarias simples. 
> - Como se utiliza una llave privada (la comprimida por Huffman) es computacionalmente inviable desencriptar el contenido sin tener acceso a la llave.

### ¿Qué relevancia tiene el código de Huffman para la Ingeniería en Computadores?
En Computadores nos especializamos en dispositivos que se caracterizan por tener software de bajo nivel. Además, estos suelen ser pequeños o de espacio limitado. Por lo tanto, requieren de mucha eficiencia en el manejo de la memoria. 
Con el algoritmo de Huffman y otros algoritmos de compresión, es posible obtener archivos que ocupen menos memoria que el original. Por este motivo, pueden resultar esenciales para dispositivos que requieran de tanta eficiencia como los descritos anteriormente. 

## Algoritmo LZ77.

Este aloritmo fue desarrollado por Abraham Lempel y Jacob Zic en 1977. De aquí surge el nombre LZ77 o Lmpel-Zic. **El principio de este algoritmo es utilizar secuencias de caracteres repetidas para formar el diccionario de un archivo.** El método se puede comparar con una ventana que se desliza ¿Por qué?
![Lz77 algorithm](https://images.slideplayer.com/32/10096653/slides/slide_4.jpg)

Términos importantes:
- **Input stream:** la secuencia de bytes que se debe comprimir.

- **Byte:** la unidad básica de la información almacenada en el input stream.

- **Coding position:** la posición (del input stream) que se está analizando. También corresponde al inicio del lookahead buffer.

- **Lookahead buffer:** la secuencia de bytes que comienza con el coding position y termina al final del input stream.

- **Window (ventana):** un buffer the tamaño $w$. Inicia con el coding position y termina $w$ bytes atrás. Al inicio del proceso la ventana está vacía, conforme avanza el algoritmo alcanza el tamaño $w$ y luego se desliza con el current position por el input stream.  

- **Pointer:** es la información que corresponde al offset (número de bytes que recorre hacia atrás) y el largo del substream para incluir en el diccionario.

En el siguiente se explica de forma visual y casual este algoritmo (recomiendo mucho):

<iframe width="400" height="250" src="https://www.youtube.com/embed/goOa3DGezUA" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


## Algoritmo LZ78.
Se diferencia del LZ77 porque no utiliza una entana en la información que será comprimida. Existe un diccionario que tiene las cadenas de caracteres que ya han concurrido previamente. 

Al inicio el diccionario está vacío y su tamaño es limitado por la memoria disponible. 

El codeword consiste únicamente de dos indicadores: un puntero y un índice que identifica la posición del string en el diccionario. Además de un espacio que contiene el último símbolo que fue leído desde la entrada. 

El diccionario se puede representar mediante un árbol conocido como trie.

El código es bastante sencillo.

[Google Developers](https://www.youtube.com/watch?v=Jqc418tQDkg) explica más sobre la familia de algoritmos LZ y algunas aplicaciones, si deseas expandir tu conocimiento. 

![Mountastic  footer](https://user-images.githubusercontent.com/38998436/87217793-5fa59d80-c30a-11ea-94e7-81be3d541319.png)
