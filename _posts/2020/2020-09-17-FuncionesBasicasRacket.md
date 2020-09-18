---
layout: article
title: Funciones básicas en Racket.
date: 2020-09-17 15:33:00+0200
coverPhoto: https://superawesomevectors.com/wp-content/uploads/2017/07/abacus-free-flat-vector-icon-800x566.jpg
---

Este es solamente un resumen rápido sobre las funciones que se pueden encontrar en Racket y algunos ejemplos para saber cómo se utilizan.

## Operaciones numéricas elementales.
- Suma.
- Substracción.
- Multiplicación.
- División.

Lo importante es adaptarse a la nomenclatura. Por ejemplo, para realizar una operación como  $$7 + 3 \cdot (1 + \frac{5}{2})$$ se escribe así:
```python
> (+ 7 (* 3 (+ 1 (/ 5 2))))
```
## Operaciones numéricas adicionales.
- **Valor absoluto:**  `(abs arg1)`
- **Valor mínimo entre los argumentos:** `(min arg1 arg2 ... argN)` 
- **Valor máximo entre los argumentos:** `(max arg1 arg2 ... argN)`
- **Truncar:** trunca el valor real al entero inmediato inferior. `(truncate arg1)`
- **Redondear:** redondea al entero más cercano. `(round arg1)`
- **Cociente:** retorna la división entera de sus argumentos (enteros). `(quotient arg1 arg2)`
- **Residuo:** retorna el residuo entre `arg1` y `arg2` (enteros). Tiene el mismo signo que `arg1`.  `(remainder arg1 arg2)`
- **Potencia:** retorna $(arg1) ^{arg2}$. `(expt arg1 arg2)`
- **Raíz cuadrada:** `(sqrt arg1)`

## Predicados numéricos.
 Los predicados son funciones que devuelves únicamente el valor de verdadero o falso. El valor de verdadero se representa mediante el símbolo de `#t` y el valor de falso se representa mediante el símbolo de `#f`.

- **Si dos números son iguales:** `(= arg1 arg2 ... argN)`
- **Si dos valores son iguales:** solo recibe dos argumentos. `(equal? arg1 arg2)`. En caso de ser enteros funciona como `(= arg1 arg2)`. 
- Relación de orden:
	- **Menor estricto:** `(< arg1 arg2 ... argN)`
	- **Mayor estricto:** `(> arg1 arg2 ... argN)`
	- **Menor igual:** `(<= arg1 arg2 ... argN)`
	- **Mayor igual:** `(>= arg1 arg2 ... argN)`
- **¿Es cero? :** `(zero? arg1)`
- **¿Es positivo? :** `(positive? arg1)`
- **¿Es negativo? :** `(negative? arg1)`
- **¿Es número par? :** `(even? arg1)`
- **¿Es impar? :** `(zero? arg1)`
- **¿Es un número? :** `(number? arg1)`
- **¿Es un entero? :** `(integer? arg1)`
- **¿Es un real? :** `(real? arg1)`

## Predicados lógicos.
Son funciones que implementan las principales conectivas de la lógica simbólica. En general reciben como entradas valores de `#f` y `#t` y producen uno de esos valores como su salida.

- **Si todos los argumentos son verdaderos:** `(and arg1 arg2 ... argN)`
- **Si alguno de los argumentos son verdaderos:** `(or arg1 arg2 ... argN)`

## Funciones COND y DEFINE.

La función **`cond`** permite seleccionar una opción de múltiples alternativas. La sintaxis es:
```python
> (cond ( condicion1 
			funcion1)
		( condicion2
			funcion2)
			...
		( condicionN
			funcionN))
```
También acepta `else` como condición final.

La función **`define`** puede utilizarse de varias maneras:
- **Crear variables:**  `(define nombreVariable valorVariable)`
- **Definir funciones:** `(define nombreFuncion arg1 arg2 ... argN)`

Se puede utilizar junto a `cond` para crear funciones complejas.

## Función LET
Es usual que las fórmulas que se desean programar tengan una estructura muy compleja por lo que resulta útil emplear variables intermedias para el cálculo. Para ello se utiliza la función **`let`**, la cual tiene la siguiente sintaxis: 
```python 
> (let ( (variable1 funcion1)
		 (variable2 funcion2)
		 ...
		 (variableN funcionN) 
		)
		cuerpoFuncion)
```
Por ejemplo:
``` python
> (define (f x y)
	(let ( (a (- 1 y))
		(b (+ 1 y))
		)
		(+ (* y a)
		(* a b)
		(* 2 x b b))))
```

Existe otra función **`let*`**. La principal diferencia es que `let` asocia las variables de manera paralela (como si todas estuvieran en la misma línea de código) pero ``let*`` define cada variable conforme avanza en el código. Estas dos funciones permiten ligar valores a variables.

## Función QUOTE.
La función `(quote arg1)` o `'arg1` retorna el argumento literal (parecido a un string).
```python
> '(zero? 52)
(zero? 52)
```

## Función APPLY.

La función `(apply fun '(arg1 arg2 ... argN))` es utilizada por el ambiente de interpretación. Recibe dos argumentos, el primero es una función y el segundo son los argumentos de la función. Realiza el siguiente proceso:
```python
> (apply fun '(arg1 arg2 ... argN))
(fun arg1 arg2 ... argN)
```
## Función EVAL.
Cuando se le presenta una nueva expresión a Scheme, este automáticamente le solicita a la función `eval` que evalúe dicha expresión. La función `(eval expresion)` es una función usada por el ambiente de interpretación del lenguaje.
```python
> (eval '(+ 1 2 3))
6
```

## Evaluación de las funciones.
Sea: `S = (f arg1 ... argN)`

El algoritmo que utiliza racket para evaluar las funciones se describe de la siguiente manera:

![Algoritmo de Racket para evaluar funciones](https://user-images.githubusercontent.com/38998436/93536328-f8a5f580-f905-11ea-8959-b679c4a2f1eb.png)

El intérprete evalúa números, símbolos y funciones. Utiliza además un algoritmo de evaluación que **evalúa primero la función y los parámetros y luego aplica la función a los mismos**.

-----
**Referencia:** *Introducción a la programación con Scheme por José E. Helo Guzmán.*

![Mountastic  footer](https://user-images.githubusercontent.com/38998436/87217793-5fa59d80-c30a-11ea-94e7-81be3d541319.png)

