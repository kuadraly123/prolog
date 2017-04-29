## Ejercicios Con Haskell - Programación Lógica y Funcional
   
   ++**Indice:**++

* 01 - 10	Listas
* 11 - 20   Listas continuación.
* 21 - 28	Listas de nuevo
* 31 - 41	Aritmética
* 46 - 50   Lógica y códigos

#01 - 10	Listas#
##Problema 1##

_Encontrar el ultimo elemento de una lista._

**Ejemplo en Haskell**

	Prelude> myLast [1,2,3,4]
	4
	Prelude> myLast ['x','y','z']
	z'
![enter image description here](https://lh3.googleusercontent.com/-wXQpNvUlctE/WQPuSF8zwxI/AAAAAAAAPXI/C0VBJ0tMUz4PPTddL5HZr2FRy-fic_0mACLcB/s0/ejercicio1.png "ejercicio1.png")

##Problema 2##

_Encontrar el penúltimo elemento de una lista._

**Ejemplo en Haskell:**

	Prelude> myButLast [1,2,3,4]
	3
	Prelude> myButLast ['a'..'z']
	'y'
![enter image description here](https://lh3.googleusercontent.com/-pWu1jya6a7g/WQPwKensO7I/AAAAAAAAPXc/bzEOyzk__5UuS5WQSHJjdRtRpy9JpUh2ACLcB/s0/ejercicio2.png "ejercicio2.png")

##Problema 3##

Encuentra el K'th elemento de una lista. El primer elemento de la lista es el número 1

**Ejemplo en Haskell:**
	
	* (element-at '(a b c d e) 3)
	c
![enter image description here](https://lh3.googleusercontent.com/-OJM8Z-ygVqE/WQPxWkIdZ8I/AAAAAAAAPXo/0r8FJsjZFFA7QgQ7vXTUbxfg5wLTFShzgCLcB/s0/ejercicio3.png "ejercicio3.png")

##Problema 4##

Encontrar el número de elementos de una lista.

**Ejemplo en Haskell:**
	
	Prelude> myLength [123, 456, 789]
	3
	Prelude> myLength "Hello, world!"
	13
![enter image description here](https://lh3.googleusercontent.com/-2BCamoXwdCc/WQPyoALaIMI/AAAAAAAAPYA/N1oECcrJ1rEen_lCEtsceVxQ5ibhqJp_ACLcB/s0/ejercicio4.png "ejercicio4.png")

##Problema 5##
Invertir una lista.

**Ejemplo en Haskell:**

	Prelude> myReverse "A man, a plan, a canal, panama!"
	"!amanap ,lanac a ,nalp a ,nam A"
	Prelude> myReverse [1,2,3,4]
	[4,3,2,1]
![enter image description here](https://lh3.googleusercontent.com/-uguyZBFdS0U/WQP0IMmLQjI/AAAAAAAAPYU/uFkK9-miqPQ79eZ-wqGkhoRniLic3RIEQCLcB/s0/ejercicio5.png "ejercicio5.png")
##Problema 6##
Encontrar el palindromo de una lista. Un palindromo puede ser leido hacia 
adelante o hacia atras; Ejemplo (x a m a x).

**Ejemplo en Haskell:**

	*Main> isPalindrome [1,2,3]
	False
	*Main> isPalindrome "madamimadam"
	True
	*Main> isPalindrome [1,2,4,8,16,8,4,2,1]
	True
![enter image description here](https://lh3.googleusercontent.com/-aUCTOgO23T4/WQP1A6es7LI/AAAAAAAAPYk/Bfbbp1-Vqoge-Usd8vMU4IkoPE9RRHriQCLcB/s0/ejercicio6.png "ejercicio6.png")

##Problema 7##
Aplanar una estructura de lista anidada.

Transforma una lista, posiblemente conteniendo listas como elementos en una 
lista reemplazando cada lista por sus elementos (recursivamente).

**Ejemplo:**

	*(my-flatten '(a (b (c d) e)))
	 (A B C D E)

**Ejemplo en Haskell:**

Tenemos que definir un nuevo tipo de datos, porque las listas en Haskell son
homogéneas.

	 data NestedList a = Elem a | List [NestedList a]
	*Main> flatten (Elem 5)
	[5]
	*Main> flatten (List [Elem 1, List [Elem 2, List [Elem 3, Elem 4], Elem 5]])
	[1,2,3,4,5]
	*Main> flatten (List [])
	[]
![enter image description here](https://lh3.googleusercontent.com/-pvBvop1Qr8o/WQP2l__91FI/AAAAAAAAPY8/-FOD5bwPAlE37nn0pegC3jkB0EryBUeUACLcB/s0/ejercicio7.png "ejercicio7.png")

##Problema 8##
Eliminar duplicados consecutivos de elementos de lista.

Si una lista contiene elementos repetidos, debe reemplazarse por una
Copia del elemento. El orden de los elementos no debe cambiarse.

**Ejemplo:**

	* (compress '(a a a a b c c a a d e e e e))
	  (A B C A D E)

**Ejemplo en Haskell:**

	> compress "aaaabccaadeeee"
	"abcade"
![enter image description here](https://lh3.googleusercontent.com/-59qPO_A7cYk/WQP3n-FodRI/AAAAAAAAPZQ/4swlTl2ajuAL5tzEo9rOOOBEf3h0eBNowCLcB/s0/ejercicio8.png "ejercicio8.png")

##Problema 9##

Paquetes duplicados consecutivos de los elementos de la lista en sublistas.
Si una lista contiene elementos repetidos, deben colocarse en sublistas 
separadas.

**Ejemplo:**

	* (pack '(a a a a b c c a a d e e e e))
	  ((A A A A) (B) (C C) (A A) (D) (E E E E))

**Ejemplo en Haskell:**

	*Main> pack ['a', 'a', 'a', 'a', 'b', 'c', 'c', 'a', 'a', 'd', 'e', 'e', 'e', 'e']
	["aaaa","b","cc","aa","d","eeee"]
![enter image description here](https://lh3.googleusercontent.com/-QuKU9br5tyY/WQP4tuF7vDI/AAAAAAAAPZg/hQo76RL3bm4kbsLA9ZDCY6ViH6jax2NpgCLcB/s0/ejercicio9.png "ejercicio9.png")

##Problema 10##

Codificación de longitud de ejecución de una lista. Utilice el resultado
del problema P09 para implementar. El denominado método de compresión de datos
de codificación de longitud de ejecución. Consecutivo los duplicados de
elementos se codifican como listas (N E) donde N es el número de duplicados 
del elemento E.

**Ejemplo:**

	* (encode '(a a a a b c c a a d e e e e))
	  ((4 A) (1 B) (2 C) (2 A) (1 D)(4 E))

**Ejemplo en Haskell:**

	encode "aaaabccaadeeee"
	[(4,'a'),(1,'b'),(2,'c'),(2,'a'),(1,'d'),(4,'e')]
![enter image description here](https://lh3.googleusercontent.com/-GcJiDMcJhYU/WQP6APGW-tI/AAAAAAAAPZ4/bkCtH3UHV_ozK464yTF37Wc9_rOdAMYyACLcB/s0/ejercicio10.png "ejercicio10.png")

#11 - 20   Listas continuación.#
##Problema 11##
Codificación de longitud de ejecución modificada.

Modifique el resultado del problema 10 de tal manera que si un elemento no
tiene duplicados simplemente se copia en la lista de resultados. Sólo los
elementos con duplicados se transfieren como listas (N E).

**Ejemplo:**

	* (encode-modified '(a a a a b c c a a d e e e e))
	  ((4 A) B (2 C) (2 A) D (4 E))

**Ejemplo en Haskell:**

	P11> encodeModified "aaaabccaadeeee"
	[Multiple 4 'a',Single 'b',Multiple 2 'c',
	Multiple 2 'a',Single 'd',Multiple 4 'e']

##Problema 12#
Decodificar una lista codificada de longitud de ejecución.

Dada una lista de códigos de longitud de ejecución generada como se especifica 
en el problema 11. Construya su versión sin comprimir.

**Ejemplo in Haskell:**

	P12> decodeModified 
         [Multiple 4 'a',Single 'b',Multiple 2 'c',
         Multiple 2 'a',Single 'd',Multiple 4 'e']
	     "aaaabccaadeeee"
![enter image description here](https://lh3.googleusercontent.com/-bsY33bJNHTI/WQP7WOcB2LI/AAAAAAAAPaI/dJWNX-9E82w8q3x0ckI6rO4tYS34FG5-QCLcB/s0/ejercicio12.png "ejercicio12.png")

##Problema 13##
Codificación de longitud de ejecución de una lista (solución directa).

Implementar directamente el método de compresión de datos de codificación de
longitud de ejecución. Es decir. No crear explícitamente las sublistas que
contienen los duplicados, como en el problema 9, pero sólo contarlas. Como 
en el problema P11, simplifique la lista de resultados sustituyendo las listas 
de singleton (1 X) por X.

**Ejemplo:**

		* (encode-direct '(a a a a b c c a a d e e e e))
		  ((4 A) B (2 C) (2 A) D (4 E))

**Ejemplo en Haskell:**

	P13> encodeDirect "aaaabccaadeeee"
	[Multiple 4 'a',Single 'b',Multiple 2 'c',
	 Multiple 2 'a',Single 'd',Multiple 4 'e']
![enter image description here](https://lh3.googleusercontent.com/-lDfYVDD69os/WQP8IuZoq9I/AAAAAAAAPaY/4kbsCnQgBl033BB6hvyujXQXQC-aas72QCLcB/s0/ejercicio13.png "ejercicio13.png")

##Problema 14##
Duplicar los elementos de una lista.

**Ejemplo:**

	* (dupli '(a b c c d))
	  (A A B B C C C C D D)

**Ejemplo en Haskell:**

	> dupli [1, 2, 3]
	  [1,1,2,2,3,3]
![enter image description here](https://lh3.googleusercontent.com/-BOlRGPubUdY/WQP85tHZlNI/AAAAAAAAPas/igdSCGX-gq4bEQ-fw0aI57ABrYgATKXQwCLcB/s0/ejercicio14.png "ejercicio14.png")

##Problema 15##
Replicar los elementos de una lista un número determinado de veces.


**Ejemplo:**

	* (repli '(a b c) 3)
	  (A A A B B B C C C)
	  
**Ejemplo en Haskell:**

	> repli "abc" 3
	  "aaabbbccc"
![enter image description here](https://lh3.googleusercontent.com/-vA2pm5Bh78Q/WQP9nZLL6EI/AAAAAAAAPbA/OHdLyYRT7eg8D2AdNPpJt0YDpQ9g24SsACLcB/s0/ejercicio15.png "ejercicio15.png")

##Problema 16##
Eliminar cada elemento N'th de una lista.

**Ejemplo:**

	* (drop '(a b c d e f g h i k) 3)
	  (A B D E G H K)

**Ejemplo en Haskell:**

	*Main> dropEvery "abcdefghik" 3
	"abdeghk"
![enter image description here](https://lh3.googleusercontent.com/-5XWp7Y7c--I/WQQAFph1_TI/AAAAAAAAPbY/FWcqCDo0jBY9WRrs5kIf8lgf6b9jxVSDACLcB/s0/ejercicio16.png "ejercicio16.png")

##Problema 17##

Dividir una lista en dos partes; Se da la longitud de la primera parte.

No utilice predicados predefinidos.

**Ejemplo:**

	* (split '(a b c d e f g h i k) 3)
	  ( (A B C) (D E F G H I K))

**Ejemplo en Haskell:**

	*Main> split "abcdefghik" 3
	("abc", "defghik")
![enter image description here](https://lh3.googleusercontent.com/-FNs5Qt7nfWQ/WQQApsZ_SNI/AAAAAAAAPbo/-lofK-yednciO3R59uP3YAKsAKjqQzPFQCLcB/s0/ejercicio17.png "ejercicio17.png")

##Problema 18##
(**) Extraer una porción de una lista.

Dado dos índices, iyk, la rebanada es la lista que contiene los elementos 
entre el i'th y k'th elemento de la lista original (ambos límites incluidos). 
Comienza contando los elementos con 1.

**Ejemplo:**

	* (slice '(a b c d e f g h i k) 3 7)
   	  (C D E F G)

**Ejemplo en Haskell:**

	*Main> slice ['a','b','c','d','e','f','g','h','i','k'] 3 7
	"cdefg"
![enter image description here](https://lh3.googleusercontent.com/-JJ3b0IBxJSg/WQQBWb6h3vI/AAAAAAAAPb8/-67PqZ0C9B0DRr9xG4nbSEegng7WQpf4ACLcB/s0/ejercicio18.png "ejercicio18.png")

##Problema 19##
Gire una lista **N** hacia la izquierda.

Sugerencia: Utilice la longitud de las funciones predefinidas y (++).

**Ejemplos:**

	* (rotate '(a b c d e f g h) 3)
	  (D E F G H A B C)

	* (rotate '(a b c d e f g h) -2)
	  (G H A B C D E F)

**Ejemplos en Haskell:**

	*Main> rotate ['a','b','c','d','e','f','g','h'] 3
	"defghabc"
 
	*Main> rotate ['a','b','c','d','e','f','g','h'] (-2)
	"ghabcdef"
![enter image description here](https://lh3.googleusercontent.com/-UdapqQUkiNA/WQQC3_JyGBI/AAAAAAAAPcY/7B92vZTZrMgulp9vnE5UvTIerBLqQlNTQCLcB/s0/ejercicio19.png "ejercicio19.png")

##Problema 20##
Quite el K'th elemento de una lista.

**Ejemplo en Prolog:**

	?- remove_at(X,[a,b,c,d],2,R).
	X = b
	R = [a,c,d]

**Ejemplo en Lisp:**

	* (remove-at '(a b c d) 2)
	 (A C D)

Tenga en cuenta que esto sólo devuelve la lista de residuos, mientras que 
la versión Prolog también devuelve el elemento eliminado.

**Ejemplo en Haskell:**

	*Main> removeAt 2 "abcd"
	('b',"acd")
![enter image description here](https://lh3.googleusercontent.com/-9NkAiUfC4LE/WQQD_fJgXDI/AAAAAAAAPck/yRcCESNqGTc6v1s1JTlrldymp2xt-DRigCLcB/s0/ejercicio20.png "ejercicio20.png")

#21 - 28	Listas de nuevo#
##Problema 21##
Inserte un elemento en una posición determinada en una lista.

**Ejemplo:**

	* (insert-at 'alfa '(a b c d) 2)
	  (A ALFA B C D)

**Ejemplo en Haskell:**

	P21> insertAt 'X' "abcd" 2
	"aXbcd"
![enter image description here](https://lh3.googleusercontent.com/-ikROtdv0HtY/WQQExIELfJI/AAAAAAAAPc0/gJG4dE3-7u4t-mRo9aNbNSN050T_6-NqACLcB/s0/ejercicio21.png "ejercicio21.png")

##Problema 22##

Cree una lista que contenga todos los enteros dentro de un rango dado.

**Ejemplo:**

	* (range 4 9)
  	  (4 5 6 7 8 9)

**Ejemplo en Haskell:**

	Prelude> range 4 9
	[4,5,6,7,8,9]
![enter image description here](https://lh3.googleusercontent.com/-zWu82if1nGE/WQQFcn9cpRI/AAAAAAAAPdI/-H3ns4IcjvImgcby21eYj87b0gQTYxaeACLcB/s0/ejercicio22.png "ejercicio22.png")

##Problema 23##

Extraer un número dado de elementos seleccionados aleatoriamente de una lista.

**Ejemplo:**

	* (rnd-select '(a b c d e f g h) 3)
	  (E D A)

**Ejemplo en Haskell:**

	Prelude System.Random>rnd_select "abcdefgh" 3 >>= putStrLneda
![enter image description here](https://lh3.googleusercontent.com/-1yqyOEYFAyE/WQQJUBQtRII/AAAAAAAAPds/OsV0iexWnbg3oSQbJuTjLA9csVYTYh_zgCLcB/s0/ejercicio23.png "ejercicio23.png")

##Problema 24##
Lotto: Dibuja N números aleatorios diferentes del conjunto 1..M.

**Ejemplo:**

	* (rnd-select 6 49)
	  (23 1 17 33 21 37)

**Ejemplo en Haskell:**

	Prelude System.Random>diff_select 6 49
	Prelude System.Random>[23,1,17,33,21,37]

##Problema 25##
Generar una permutación aleatoria de los elementos de una lista.

**Ejemplo:**

	* (rnd-permu '(a b c d e f))
 	  (B A D C E F)

**Ejemplo en Haskell:**

	Prelude System.Random>rnd_permu "abcdef"
	Prelude System.Random>"badcef"
    

##Problema 26##
Generar las combinaciones de K objetos distintos elegidos de los N 
elementos de una lista
¿De cuántas maneras puede un comité de 3 ser elegido de un grupo de 12
personas? Todos sabemos que hay C (12,3) = 220 posibilidades (C (N, K) 
denota el bien conocido binomial coeficientes). Para los matemáticos puros,
este resultado puede ser grande. Pero queremos realmente generar todas las 
posibilidades en una lista.

**Ejemplo:**

	* (combinations 3 '(a b c d e f))
	  ((A B C) (A B D) (A B E) ... )

**Ejemplo en Haskell:**

	> combinations 3 "abcdef"
	["abc","abd","abe",...]
![enter image description here](https://lh3.googleusercontent.com/-9YEjH3xnTa0/WQQK0Z22wVI/AAAAAAAAPeE/NcTelGYIvlcfbVEcBzUCF_NqqhSA1U2zgCLcB/s0/ejercicio26.png "ejercicio26.png")

##Problema 27##

Agrupar los elementos de un conjunto en subconjuntos disjuntos.

**a)** 

¿De cuántas maneras puede un grupo de 9 personas trabajar en 3 subgrupos 
disjuntos de 2, 3 y 4 personas? Escribir una función que genera todas las
posibilidades y las devuelve en una lista.

**Ejemplo:**

	* (group3 '(aldo beat carla david evi flip gary hugo ida))
	  ( ( (ALDO BEAT) (CARLA DAVID EVI) (FLIP GARY HUGO IDA) )... )
	  
**b)** 

Generalizar el predicado anterior de una manera que podemos especificar 
una lista de tamaños de grupo y el predicado devolverá una lista de grupos.

**Ejemplo:**

	* (group '(aldo beat carla david evi flip gary hugo ida) '(2 2 5))
	( ( (ALDO BEAT) (CARLA DAVID) (EVI FLIP GARY HUGO IDA) )... )
	
Tenga en cuenta que no queremos permutaciones de los miembros del grupo;
Es decir ((ALDO BEAT) ...) es la misma solución que ((BEAT ALDO) ...). Sin
embargo, hacemos una diferencia entre ((ALDO BEAT) (CARLA DAVID) ...) y 
((CARLA DAVID) (ALDO BEAT) ...).

Puede encontrar más información sobre este problema combinatorio en un buen 
libro sobre matemáticas discretas bajo el término "coeficientes multinomiales".

**Ejemplo en Haskell:**

	P27> group [2,3,4] ["aldo","beat","carla","david","evi","flip","gary","hugo",
	"ida"]
	[[["aldo","beat"],["carla","david","evi"],["flip","gary","hugo","ida"]],...]
	(altogether 1260 solutions)
 
	27> group [2,2,5] ["aldo","beat","carla","david","evi","flip","gary","hugo",
	"ida"]
	[[["aldo","beat"],["carla","david"],["evi","flip","gary","hugo","ida"]],...]
	(altogether 756 solutions)
![enter image description here](https://lh3.googleusercontent.com/--dhcejWdhl4/WQQMLw17ozI/AAAAAAAAPeU/Jfq2eqvCb8YpBobOGQElBJHSjTMcnXBvgCLcB/s0/ejercicio27.png "ejercicio27.png")

##Problema 28##
Clasificación de una lista de listas según la longitud de las sublistas

a) Suponemos que una lista contiene elementos que son listas ellos mismos. 
El objetivo es clasificar los elementos de esta lista según su longitud. 
P.ej. Listas cortas primero, listas más largas más adelante o viceversa

**Ejemplo:**

	* (lsort '((a b c) (d e) (f g h) (d e) (i j k l) (m n) (o)))
	  ((O) (D E) (D E) (M N) (A B C) (F G H) (I J K L))

**Ejemplo en Haskell:**

	Prelude>lsort ["abc","de","fgh","de","ijkl","mn","o"]
	Prelude>["o","de","de","mn","abc","fgh","ijkl"]
	
**b)** 

Una vez más, suponemos que una lista contiene elementos que son listas 
ellos mismos. Pero esta vez el objetivo es clasificar los elementos de esta 
lista de acuerdo a su frecuencia de longitud; Es decir, en el predeterminado, 
donde la clasificación se hace de forma ascendente, las listas con longitudes
raras se colocan primero, otras con una longitud más frecuente vienen más
tarde.

**Ejemplo:**

	* (lfsort '((a b c) (d e) (f g h) (d e) (i j k l) (m n) (o)))
	  ((i j k l) (o) (a b c) (f g h) (d e) (d e) (m n))

**Ejemplo en Haskell:**

	lfsort ["abc", "de", "fgh", "de", "ijkl", "mn", "o"]
	["ijkl","o","abc","fgh","de","de","mn"]
![enter image description here](https://lh3.googleusercontent.com/-scnxhsCiw90/WQQM2tAV3aI/AAAAAAAAPeg/oZZs7uZ91CwX-osFb-S3arWVGOJtT3qDACLcB/s0/ejercicio28.png "ejercicio28.png")

#31 - 41	Aritmética#
##Problema 31##
Determine si un número entero dado es primo.

**Ejemplo:**

	* (is-prime 7)
	  T

**Ejemplo en Haskell:**

	P31> isPrime 7
	True
![enter image description here](https://lh3.googleusercontent.com/-5OLBvDZNjl4/WQQNuQE_LkI/AAAAAAAAPew/i0LktX3UzaofG5ekjz9YZQCkyrB0aiGagCLcB/s0/ejercicio31.png "ejercicio31.png")

##Problema 32##
Determinar el mayor divisor común de dos números enteros positivos. 
Utilice el algoritmo de Euclides.

**Ejemplo:**

	* (gcd 36 63)
	  9

**Exjemplo en Haskell:**

	[myGCD 36 63, myGCD (-3) (-6), myGCD (-3) 6]
	[9,3,3]
![enter image description here](https://lh3.googleusercontent.com/-m21vWXwCxfk/WQQOXIL3THI/AAAAAAAAPfE/y9nBUnLXD_QTiIPVGV0luDLBzdkFlj-wQCLcB/s0/ejercicio32.png "ejercicio32.png")

##Problema 33##

Determine si dos números enteros positivos son coprime. Dos números son 
coprime si su mayor divisor común es igual a 1.

**Ejemplo:**

	* (coprime 35 64)
	T

**Ejemplo en Haskell:**

	* coprime 35 64
	  True
![enter image description here](https://lh3.googleusercontent.com/-3hcSOdXE2QE/WQQOzP5DxgI/AAAAAAAAPfQ/JX1ACphwNLYro0GpPHyYsFsSiciuEcJEwCLcB/s0/ejercicio33.png "ejercicio33.png")

##Problema 34##
Calcule la función totent de Euler phi (m).

La función llamada totient phi (m) de Euler se define como el número de enteros
positivos que son coprime a m.

Ejemplo: m = 10: r = 1,3,7,9; Así phi (m) = 4. Observe el caso especial: 
phi (1) = 1.

**Ejemplo:**

	* (totient-phi 10)
	  4

**Ejemplo en Haskell:**

	* totient 10
	  4
![enter image description here](https://lh3.googleusercontent.com/-Vn6WocG1h7s/WQQPeYjYq5I/AAAAAAAAPfc/l_j9vRfnB2om-h0IbOuHf-LsexNTiRwsgCLcB/s0/ejercicio34.png "ejercicio34.png")

##Problema 35##
Determine los factores primos de un entero positivo dado. Construya una 
lista plana que contenga los factores primos en orden ascendente.

**Ejemplo:**

	* (prime-factors 315)
	  (3 3 5 7)

**Ejemplo en Haskell:**

	> primeFactors 315
	[3, 3, 5, 7]
![enter image description here](https://lh3.googleusercontent.com/-vID5NCibZHg/WQQQE6D-axI/AAAAAAAAPf0/oeNi9611pL8z3iO2wC5WMym3DKtxj1usgCLcB/s0/ejercicio35.png "ejercicio35.png")

##Problema 36##
Determine los factores primos de un entero positivo dado.

Construya una lista que contenga los factores primos y su multiplicidad.

**Ejemplo:**

	* (prime-factors-mult 315)
	  ((3 2) (5 1) (7 1))

**Ejemplon Haskell:**

	*Main> prime_factors_mult 315
	[(3,2),(5,1),(7,1)]
![enter image description here](https://lh3.googleusercontent.com/-wqDlStECKNo/WQQQ6CPSMKI/AAAAAAAAPgE/lRZHLALEEX4GCywFexfEHud7JjzbJw4CQCLcB/s0/ejercicio36.png "ejercicio36.png")

##Problema 37##
Calcule la función totent de Euler phi (m) (mejorado).

Véase el problema 34 para la definición de la función de togo de Euler. Si 
se conoce la lista de los factores primos de un número m en forma de problema
36, entonces la función phi (m) puede calcularse de la manera siguiente: 
(p1 m1) (p2 m2) (p3 m3) ... ) La lista de factores primos 
(y sus multiplicidades) de un número dado m. Entonces phi (m) se puede 
calcular con la siguiente fórmula:

	phi(m) = (p1 - 1) * p1 ** (m1 - 1) * 
         (p2 - 1) * p2 ** (m2 - 1) * 
         (p3 - 1) * p3 ** (m3 - 1) * ...

Note that a ** b stands for the b'th power of a.

##Problema 38##

Comparar los dos métodos de cálculo de la función totent de Euler.

Utilice las soluciones de los problemas 34 y 37 para comparar los algoritmos.
Tomar el número de reducciones como medida de eficiencia. Trate de calcular 
phi (10090) como un ejemplo.
(no se requiere solucion)


##Problema 39##
(*) Una lista de números primos.

Dada una gama de enteros por su límite inferior y superior, construya una 
lista de todos los números primos en ese rango.

Ejemplo en Haskell:

P29> primesR 10 20
[11,13,17,19]
![enter image description here](https://lh3.googleusercontent.com/-uzLbFqpKk0k/WQQS8hhEUSI/AAAAAAAAPgk/EXFTemG3AFsO1Py7onvmKOkJSUTY8zzqQCLcB/s0/ejercicio39.png "ejercicio39.png")

##Problema 40##
Conjetura de Goldbach.
La conjetura de Goldbach dice que cada número positivo igual mayor que 2 es
la suma de dos números primos. Ejemplo: 28 = 5 + 23. Es uno de los hechos 
más famosos en la teoría numérica que no ha sido demostrado ser correcto en 
el caso general. Se ha confirmado numéricamente hasta números muy grandes 
(mucho más grandes que podemos ir con nuestro sistema Prolog). Escribe un
predicado para encontrar los dos números primos que suman un entero par.

**Ejemplo:**

	* (goldbach 28)
	  (5 23)

**Ejemplo en Haskell:**

	*goldbach 28
	 (5, 23)
![enter image description here](https://lh3.googleusercontent.com/-_16kSu6IUEI/WQQUCfjWTVI/AAAAAAAAPg4/lKKrDEMvqLwMUNowLHVu76ebEvBwjteKQCLcB/s0/ejercicio40.png "ejercicio40.png")
 
##Problema 41##
Dado un rango de números enteros por su límite inferior y superior, 
imprima una lista de todos los números pares y su composición de Goldbach.

En la mayoría de los casos, si un número par está escrito como la suma de dos
números primos, uno de ellos es muy pequeño. Muy raramente, los primos son más
grandes que dicen 50. Intente descubrir cuántos tales casos hay en el rango
2..3000.

**Ejemplo:**

	* (goldbach-list 9 20)
	  10 = 3 + 7
	  12 = 5 + 7
	  14 = 3 + 11
	  16 = 3 + 13
	  18 = 5 + 13
	  20 = 3 + 17
	  * (goldbach-list 1 2000 50)
	  992 = 73 + 919
	  1382 = 61 + 1321
	  1856 = 67 + 1789
	  1928 = 61 + 1867

**Ejemplo en Haskell:**

	*Exercises> goldbachList 9 20
	[(3,7),(5,7),(3,11),(3,13),(5,13),(3,17)]
	*Exercises> goldbachList' 4 2000 50
	[(73,919),(61,1321),(67,1789),(61,1867)]
![enter image description here](https://lh3.googleusercontent.com/-GFYpfUl-tsA/WQQVesIG2KI/AAAAAAAAPhU/9zDa8Stu3oUITOVv-vMp_L3GOA9S6oOogCLcB/s0/ejercicio41.png "ejercicio41.png")

#46 - 50   Lógica y códigos#
##Problema 46##
(**) Define predicados y / 2, o / 2, nand / 2, ni / 2, xor / 2, impl / 2 y 
eq / 2 (Para la equivalencia lógica) que tienen éxito o fracasan según el
resultado de sus respectivas operaciones; p.ej. Y (A, B) tendrán éxito, si y
sólo si ambos A y B tienen éxito.

Una expresión lógica en dos variables se puede escribir como en el siguiente 
ejemplo: y (o (A, B), nand (A, B)).

Ahora, escriba una tabla de predicados / 3 que imprima la tabla de verdad de 
una expresión lógica dada en dos variables.

**Ejemplo:**

	(table A B (and A (or A B)))
	true true true
	true fail true
	fail true fail
	fail fail fail

**Ejemplo en Haskell:**

	> table (\a b -> (and' a (or' a b)))
	True True True
	True False True
	False True False
	False False False
![enter image description here](https://lh3.googleusercontent.com/-s_jJ3ZhRz2g/WQQWdqSc59I/AAAAAAAAPhk/UCMdjDTrtNUqxNv4KESKMkvodtl72WpGQCLcB/s0/ejercicio46.png "ejercicio46.png")

##Problema 47##
Tablas de verdades para expresiones lógicas (2).

Continúe el problema P46 definiendo y / 2, o / 2, etc como operadores. 
Esto permite escribir la expresión lógica de la manera más natural, como en 
el ejemplo: A y (A o no B). Defina la precedencia del operador como de
costumbre; Como en Java.

**Ejemplo:**

	* (table A B (A and (A or not B)))
 	  true true true
	  true fail true
	  fail true fail
	  fail fail fail

**Ejemplo en Haskell:**

	> table2 (\a b -> a `and'` (a `or'` not b))
	True True True
	True False True
	False True False
	False False False
![enter image description here](https://lh3.googleusercontent.com/-62hxL9bnEk8/WQQXHNCXqEI/AAAAAAAAPh0/_JfFzvbqbGQagLsQsohJxsjIsFfXtKFsACLcB/s0/ejercicio47.png "ejercicio47.png")

##Problema 48##
Tablas de verdades para expresiones lógicas (3).

Generalizar el problema P47 de tal manera que la expresión lógica puede
contener cualquier número de variables lógicas. Definir tabla / 2 de una 
manera que tabla (List, Expr) imprime la tabla de verdad para la expresión
Expr, que contiene las variables lógicas enumeradas en List.

**Ejemplo:**

	* (table (A,B,C) (A and (B or C) equ A and B or A and C))
	  true true true true
	  true true fail true
	  true fail true true
	  true fail fail true
	  fail true true true
	  fail true fail true
	  fail fail true true
	  fail fail fail true

**Ejemplo en haskell:**

	> tablen 3 (\[a,b,c] -> a `and'` (b `or'` c) `equ'` a `and'` b `or'` a `and'` c)
	-- infixl 3 `equ'`
	True  True  True  True
	True  True  False True
	True  False True  True
	True  False False True
	False True  True  True
	False True  False True
	False False True  True
	False False False True
 
	-- infixl 7 `equ'`
	True  True  True  True
	True  True  False True
	True  False True  True
	True  False False False
	False True  True  False
	False True  False False
	False False True  False
	False False False False
![enter image description here](https://lh3.googleusercontent.com/-_Cy02yWr_q4/WQQXwhyz6LI/AAAAAAAAPiI/aHsSdGRM2GApLa6DFzQwUUg1Za3ziijFQCLcB/s0/ejercicio48.png "ejercicio48.png")

##Problema 49##
Códigos de gris.

Un código Gray de n bits es una secuencia de cadenas de n bits construidas de 
acuerdo con ciertas reglas. Por ejemplo,

	n = 1: C(1) = ['0','1'].
	n = 2: C(2) = ['00','01','11','10'].
	n = 3: C(3) = ['000','001','011','010',´110´,´111´,´101´,´100´].

Averigüe las reglas de construcción y escriba un predicado con la siguiente 
especificación:

	% gray(N,C) :- C is the N-bit Gray code

¿Se puede aplicar el método de "caché de resultados" para hacer el predicado
más eficiente, cuando se va a utilizar de forma repetida?

Ejemplo en haskell:

P49> gray 3
["000","001","011","010","110","111","101","100"]

![enter image description here](https://lh3.googleusercontent.com/-j90M0AGDOLM/WQQYNcdEMMI/AAAAAAAAPiU/fkIlVVKQvN0_c1JxDPlubp1hUSivvzEcwCLcB/s0/ejercicio49.png "ejercicio49.png")

##Problema 50##
Códigos Huffman.
Suponemos un conjunto de símbolos con sus frecuencias, dado como una lista de
términos fr (S, F). Ejemplo: [fr (a, 45), fr (b, 13), fr (c, 12), fr (d, 16),
fr (e, 9), fr (f, 5)]. Nuestro objetivo es construir una lista hc (S, C)
términos, donde C es la palabra de código Huffman para el símbolo S. En 
nuestro ejemplo, el resultado podría ser Hs = [hc (a, '0'), hc (b , '101'),
hc (c, '100'), hc (d, '111'), hc (e, '1101' ), ... etc.]. La tarea será
realizada por el predicado huffman / 2 definido como sigue:

	% huffman(Fs,Hs) :- Hs 
	Es la tabla de códigos Huffman para la tabla de frecuencias Fs

**Ejemplo en Haskell:**

	*Exercises> huffman [('a',45),('b',13),('c',12),('d',16),('e',9),('f',5)]
	[('a',"0"),('b',"101"),('c',"100"),('d',"111"),('e',"1101"),('f',"1100")]
	
![enter image description here](https://lh3.googleusercontent.com/-HPmI7pHBD3Y/WQQYu877OFI/AAAAAAAAPik/JQ8W1d0NIbMEotg901CNH0jTp_VouBndQCLcB/s0/ejercicio50.png "ejercicio50.png")