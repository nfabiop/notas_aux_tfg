---
tags:
  - "#TFG"
  - teoria-de-juegos
  - "#game-theory"
  - "#capitulo-2"
bibliography: game theoretical models in biology - brown-rychtar
---


# 2. Que es un Juego?

En este capitulo describimos los terminos que se utilizaran para la gran mayoria de los modelos de juegos evolutivos en este libro y en otros lugares. Como se indico al final del capitulo 1, este capitulo esta destinado principalmente a presentar algunos metodos matematicos importantes, y se deja para los capitulos 3 y 4 ver como estos usamos estas herramientas para modelar poblaciones utilizando juegos evolutivos.

<mark style="background: #BBFABBA6;">"Juego"</mark> se utiliza en una amplia variedad de contextos la mayoria de los cuales no tiene nada que ver con el contenido de este libro. Para los teoricos de juegos y especialmente para aquellos que trabajan en aplicaciones de la teoria de juegos en biologia, economia o ciencias sociales, la palabra <mark style="background: #ABF7F7A6;">"Juego" significa un modelo matematico de una situacion en la que varias entidades interactuan (directa o indirectamente) entre si y donde cada entidad actua en su propio interes (que puede estar potencialmente en conflicto con los intereses de otras entidades, aunque tambien puede haber intereses comunes)</mark> [[definicion-juego]]
La mayoria de los juegos como el <mark style="background: #ABF7F7A6;">Dilema del Prisionero</mark> discutido en los capitulos 4 y 14, de hecho se han desarrollado para modelar y analizar este tipo de situaciones de conflicto. Tambien hay juegos que existen desde hace mucho tiempo y que juegan ninos y adultos de todas las edades, y que solo despues del desarrollo de la teoria de juegos se han adaptado para modelar situaciones de la vida real. Antes de introducir el concepto matematico de un juego, veamos uno de ellos, el juego de <mark style="background: #ABF7F7A6;">piedra, papel o tijera</mark> 


#### Ejemplo 2.1 (El juego de piedra papel y tijera) 
Dos jugadores ponen las manos detras de la espalda y, a una senal dada, producen una de las tres formas simultaneamente, <mark style="background: #FFB8EBA6;">sin saber como juega el otro</mark> : un puno cerrado (una piedra), dos dedos separados (un par de tijeras) o una palma plana (una hoja de papel). La convencion es que la piedra vence (al romper) a las tijeras, las tijeras vencen (cortan) al papel y el papel vence (envuelve) a la piedra. Si ganas, obtienes un punto, y si pierdes, pierdes un punto, y no hay puntos si ambos producen el mismo simbolo. <mark style="background: #ABF7F7A6;">El juego Piedra Papel o Tijera (RSP - Rock, Scissors, Paper) se ha utilizado para modelar algunos fenomenos biologicos, por ejemplo, las bacterias coliformes (ver ejercicio 2.2) o las estrategias de apareamiento del lagarto comun de manchas laterales</mark> (Uta stansburiana) como se describe a continuacion.


#### Ejemplo 2.2 (El juego PPT en lagartijas, ) 
La lagartija comun de manchas laterales Uta Stansburiana exhibe un polimorfismo en el color de la garganta. Los machos con gargantas anaranjadas son muy agresivos y defienden territorios grandes. Los machos con gargantas azul oscuro son menos agresivos y defienden territorios mas pequenos. Los machos con rayas amarillas no defienden ningun territorio, pero se parecen a las hembras y utilizan una estrategia de sigilo cuando se aparean. Se observo en <mark style="background: #CACFD9A6;">"Sinervo y Lively (1996)"</mark>
 que 
 - a) si prevalece el azul, el naranja puede invadir
 - b) si prevalece el amarillo, el azul puede invadir
 - c) si prevalece el naranja, el amarillo puede invadir
Como es el caso en el juego de PPT, y lo cual es tipico en la mayoria de los juegos interesantes, el resultado del juego depende no solo de la accion de un jugador en particular, sino tambien de las acciones de otros jugadores.<mark style="background: #ABF7F7A6;"> Gran parte de la teoria de juegos se dedica a responder una pregunta que todo jugador de cualquier juego debe responder: cual es la mejor accion que puede realizar? La dificultad radica en el hecho de que la mejor jugada generalmente depende de la eleccion del otro jugador o de los otros jugadores. Este es el concepto fundamental de la teoria de juegos</mark>. Veremos en las sesiones siguientes como la teoria de juegos aborda la definicion de la mejor accion y como buscamos dicha accion.



## 2.1 Elementos clave de un juego

Considerando el ejemplo del juego de PPT, podemos ver algunos de los conceptos clave que necesitamos en la teoria de juegos. Debemos especificar las reglas del juego. <mark style="background: #ABF7F7A6;">Alguno de los factores mas importantes son:</mark>
- <mark style="background: #ABF7F7A6;">quien juega el juego: dos jugadores)</mark>
- <mark style="background: #ABF7F7A6;"> que acciones pueden realizar estos jugadores: en este caso piedra, papel o tijera</mark>
- <mark style="background: #ABF7F7A6;">y cual es el resultado que sigue a un conjunto especifico de acciones.</mark>

<mark style="background: #ABF7F7A6;">Tambien hay otros factores</mark>, necesarios para una descripcion matematica completa de un juego, que a menudo se dan por sentados implicitamente, sin indicarlos explicitamente. Algunos ejemplos de tales factores incluyen el requisito de que los<mark style="background: #ABF7F7A6;"> jugadores tomen sus decisiones simultaneamente </mark>(es decir, sin conocimiento de la eleccion que hara el otro jugador) <mark style="background: #ABF7F7A6;">o en un orden determinado; que el juego se juegue una o varias veces, etc.</mark>

A continuacion, presentamos el concepto de un juego en forma normal. En el capitulo 10 se presentara un concepto de juego alternativo.


### 2.1.1 Jugadores

Un escenario de juego puede tener cualquier numero de jugadores, que toman decisiones estrategicas y obtienen recompensas en consecuencia. <mark style="background: #ABF7F7A6;">Un juego</mark> en particular <mark style="background: #ABF7F7A6;">puede tener cualquier numero finito, o incluso un numero infinito de jugadores</mark>. <mark style="background: #ABF7F7A6;">El numero mas comun de jugadores es de dos</mark>, como en el juego de PPT, y este escenario esta cubierto por gran parte de la literatura sobre el tema.

Como se describe en el capitulo 1, <mark style="background: #ABF7F7A6;">es muy comun en biologia que el juego se defina para tener solo dos jugadores, pero aun asi, puede ser "jugado" dentro de una poblacion de mas de dos individuos</mark> (<mark style="background: #FFB8EBA6;">ver descripcion en capitulo 1 del libro</mark>) De hecho, muy a menudo se considera que la poblacion es efectivamente infinita. Podemos pensar en la poblacion como un grupo de jugadores potenciales que participan en concursos por parejas jugando un juego particular (relativamente simple) entre dos jugadores en lugar de que cada individuo sea un jugador de un juego (relativamente complicado). Podemos discutir sobre el realismo de estas suposiciones (ver capitulos 4 y 9), pero esta es una de las simplificaciones que utilizan los modeladores para hacer que su modelo sea matematicamente manejable. Como veremos en este libro, hay suficientes dificultades matematicas incluso con esta simplificacion.
<mark style="background: #ABF7F7A6;">La popularidad de los juegos por parejas no se debe simplemente a su relativa simplicidad, sino tambien a la amplia aplicabilidad de esta idea</mark>. Sin embargo, las poblaciones reales contienen muchos individuos, y sus interacciones no siempre se pueden reducir a una secuencia de concursos por parejas independientes. A veces, grupos mas grandes de individuos pueden encontrarse y luchar simultaneamente por un recurso; Esto se analiza en el capitulo 9. De manera similar, los juegos pueden ser por parejas, pero el resultado de uno puede influir en que individuo sera el siguiente oponente, o en la probabilidad de exito en un juego posterior, generando asi una estructura de juegos por parejas no independientes. Un ejemplo de esto se encuentra en el modelo de formacion de jerarquias de dominancia que se analiza en el capitulo 15 y tambien en el capitulo 9. Una situacion diferente es cuando un idividuo debe emplear una estrategia en su comportamiento general que no se utiliza contra ningun individuo o grupo de individuos, pero cuya recompensa se ve afectada por el juego de todos los miembros de la poblacion. Este tipo de juego se denomina "jugar en el campo", y un ejemplo clasico de esto es el juego de la proporcion de sexos que analizaremos en detalle en el capitulo 4.


### 2.1.2 Estrategias

Una vez que hemos decidido quienes seran los jugadores, tenemos que especificar que opciones estos pueden elegir.<mark style="background: #ABF7F7A6;"> Puede haber varios puntos en los que un jugador tenga que elegir, y las opciones posibles en cada punto suelen denominarse acciones</mark>. <mark style="background: #ABF7F7A6;">Matematicamente, una estrategia puede definirse como una especificacion completa de la accion elegida en cada posicion posible que pueda encontrarse en un juego</mark>. <mark style="background: #ABF7F7A6;">Desde el punto de vista biologico, una estrategia puede considerarse como un fenotipo</mark> (!!!no se que es un fenotipo???), <mark style="background: #ABF7F7A6;">como el color de la piel en los lagartos o la produccion de toxinas en las bacterias, o un comportamiento como el parasitismo de cria de los cucos, que esta determinado geneticamente</mark>. En general, existe una distincion entre una estrategia pura y una estrategia mixta. Esta distincion, matematicamente, muy a menudo es solo una cuestion de definicion. Sin embargo, biologicamente, la distincion suele ser importante.


#### 2.1.2.1 Estrategias Puras


-------------------=






























