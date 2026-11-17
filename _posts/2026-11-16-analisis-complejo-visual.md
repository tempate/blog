---
title: Análisis Complejo Visual
date: 2026-11-16
---

Mi hermana está cursando su primera asignatura de análisis complejo. Ella odia el análisis, y la verdad es que no es difícil odiarlo. Es un coñazo. Todo está lleno de números irracionales, derivadas, integrales, fórmulas absurdas que memorizar y que cuesta entender. Todo es mucho más fácil en álgebra, donde los objetos son tangibles. Pero el análisis complejo es diferente. 

No me acuerdo de cómo ni de por qué, pero mientras yo cursaba la asignatura de análisis complejo, me leí el mejor libro de matemáticas que he leído nunca, _Visual Complex Analysis_, de Tristan Needham. Me gustó tanto que hizo que la asignatura que más odiaba se convirtiera en mi asignatura favorita, y desde entonces, siempre pienso que odio el análisis real, pero adoro el análisis complejo. Hoy me gustaría intentar transmitirle ese amor a mi hermana.

## Multiplicar números complejos es girar y estirar

Quiero empezar analizando la relación entre los números complejos y el plano. Un número complejo es un número $z = x + iy$ donde $x \in \mathbb{R}$ es la parte real de $z$ y $y \in \mathbb{R}$, la parte imaginaria. Podemos pensar en un número complejo $z$ como en una tupla $\langle x,y \rangle \in \mathbb{R}^2$ y dibujarlo en un plano cartesiano con la parte real en el eje X y la parte imaginaria en el eje Y. 

<figure>
  <img src="../assets/images/multiplicar-numeros-complejos/plano-complejo.svg" alt="Plano complejo con la parte real en el eje horizontal y la parte imaginaria en el vertical. Aparecen los puntos 2 + i, −1 + 2i, −3 − i y 1 − 2i, con líneas discontinuas hasta los ejes.">
  <figcaption>Algunos números complejos en el plano.</figcaption>
</figure>

La esencia del análisis complejo, y lo que lo diferencia del análisis vectorial, aparece en la multiplicación. Multiplicar un número complejo $z = x + iy$ por $i$ da $iz = -y + ix$, y convierte el punto $\langle x, y \rangle$ en $\langle -y, x \rangle$. Es decir, multiplicar por $i$ rota el plano. Por otro lado, multiplicar $z$ por un número real positivo, como $2$, da $2z$, y convierte el punto $\langle x, y \rangle$ en $\langle 2x, 2y \rangle$. Es decir, multiplicar por $2$ estira el plano.

Para entender esta idea mejor, podemos dibujar qué le pasa al plano. Basta con fijarnos en el cuadrado de vértices $0$, $1$, $1 + i$ e $i$, en gris, y ver a dónde lo lleva la multiplicación, en rosa.

<div class="figure-row">
<figure>
  <img src="../assets/images/multiplicar-numeros-complejos/multiplicar-por-i.svg" alt="El cuadrado de vértices 0, 1, 1 + i e i, en gris, y su imagen al multiplicar por i, en rosa, con vértices 0, i, −1 + i y −1. El cuadrado rosa es el gris girado 90° en sentido antihorario.">
  <figcaption>Multiplicar por c = i gira el plano 90°.</figcaption>
</figure>
<figure>
  <img src="../assets/images/multiplicar-numeros-complejos/multiplicar-por-2.svg" alt="El cuadrado de vértices 0, 1, 1 + i e i, en gris, y su imagen al multiplicar por 2, en rosa, con vértices 0, 2, 2 + 2i y 2i. El cuadrado rosa es el gris con el doble de lado.">
  <figcaption>Multiplicar por c = 2 estira el plano.</figcaption>
</figure>
</div>

Ahora podemos probar a multiplicar por otros números y ver qué pasa. Si multiplicamos $z$ por $-i$, el plano rota hacia el otro lado, en sentido horario. Y si multiplicamos $z$ por $1/2$, el plano se aplasta hacia el centro.

<div class="figure-row">
<figure>
  <img src="../assets/images/multiplicar-numeros-complejos/multiplicar-por-menos-i.svg" alt="El cuadrado de vértices 0, 1, 1 + i e i, en gris, y su imagen al multiplicar por −i, en rosa, con vértices 0, −i, 1 − i y 1. El cuadrado rosa es el gris girado 90° en sentido horario.">
  <figcaption>Multiplicar por c = −i gira el plano −90°.</figcaption>
</figure>
<figure>
  <img src="../assets/images/multiplicar-numeros-complejos/multiplicar-por-un-medio.svg" alt="El cuadrado de vértices 0, 1, 1 + i e i, en gris, y su imagen al multiplicar por 1/2, en rosa, con vértices 0, 1/2, 1/2 + i/2 e i/2. El cuadrado rosa es el gris con la mitad de lado.">
  <figcaption>Multiplicar por c = 1/2 aplasta el plano.</figcaption>
</figure>
</div>

¿Pero qué pasa si multiplicamos $z$ por un número complejo $c$ cualquiera? Para verlo, podemos empezar probando con los números complejos más sencillos, $1$ e $i$. El $1$ va a $c$, e $i$ va a $ic$, que es $c$ girado un cuarto de vuelta. Así que el cuadrado que forman $1$ e $i$ se convierte en otro cuadrado, girado y estirado. Y como 

$$
c\,z = c\,(x + iy) = x \cdot c + y \cdot ic, 
$$

el resto del plano les sigue. Así, multiplicar por $c$ gira el plano el ángulo que forma con el eje real, y lo estira $\lvert c \rvert$ veces, donde $\lvert c \rvert$ es la distancia de $c$ a $0$.

Por ejemplo, $1 + i$ forma un ángulo de 45° y tiene módulo $\sqrt{2}$, así que multiplicar por $1 + i$ gira el plano 45° y lo estira $\sqrt{2}$ veces.

<figure>
  <img src="../assets/images/multiplicar-numeros-complejos/multiplicar-por-1-mas-i.svg" alt="El cuadrado de vértices 0, 1, 1 + i e i, en gris, y su imagen al multiplicar por c = 1 + i, en rosa, con vértices 0, 1 + i, 2i y −1 + i. El cuadrado rosa es el gris girado 45° y estirado.">
  <figcaption>Multiplicar por c = 1 + i lleva el cuadrado gris al rosa.</figcaption>
</figure>

Y por eso, multiplicar números complejos es girar y estirar (o aplastar).

## Las ecuaciones de Cauchy-Riemann

El análisis estudia sobre todo funciones, y una de las preguntas más importantes que podemos hacer sobre una función es cuándo se puede derivar, porque que una función se pueda derivar es equivalente a que sea "buena". En análisis real, cuando una función es buena decimos que es derivable, pero en análisis complejo, decimos que es holomórfica. 

Una función compleja $f: \mathbb{C} \to \mathbb{C}$ es _holomórfica_ en $z_0 \in \mathbb{C}$ cuando

$$
\lim_{h \to 0} \frac{f(z_0 + h) - f(z_0)}{h} = c
$$

para algún $c \in \mathbb{C}$. Si despejamos la definición, obtenemos que $f$ es holomórfica en $z_0$ cuando 

$$
\lim_{h \to 0} f(z_0 + h) = f(z_0) + \lim_{h \to 0} c \, h,
$$

es decir, cuando al hacer zoom en $z_0$, $f$ equivale a multiplicar por $c$. En la sección anterior vimos que multiplicar por un número complejo es equivalente a girar y a estirar, así que $f$ es holomórfica cuando transforma un cuadrado pequeño alrededor de $z_0$ en otro cuadrado girado y estirado por $c$.

De la misma forma podemos descomponer $z$ en $x$ e $y$, podemos descomponer $f$ en dos funciones vectoriales reales. La función $f$ es equivalente a 

$$
f(x,y) = u(x,y) + i v(x,y)
$$ 

donde $u : \mathbb{R}^2 \to \mathbb{R}$ es la parte real de $f$ y $v : \mathbb{R}^2 \to \mathbb{R}$, la parte imaginaria. 


Ahora, podemos hacer un cuadrado pequeño centrado en $z_0$ y analizar cómo lo transforma $f$. Supongamos que el cuadrado tiene vértices en $z_0$, $z_0 + \varepsilon$, $z_0 + i \varepsilon$ y $z_0 + \varepsilon + i \varepsilon$, como en el dibujo. El punto $z_0 + \varepsilon$ desplaza $z_0$ por la tupla $\langle \varepsilon, 0 \rangle$, así que para ver cómo lo transforma $f$, solo tenemos que centrarnos en el eje $X$. Cada vez que movemos $\varepsilon$, la imagen de $f$ se mueve

$$
(\partial_x u + i\, \partial_x v)\, \varepsilon.
$$

El punto $i \varepsilon$, sin embargo, desplaza $z_0$ por la tupla $\langle 0, \varepsilon \rangle$, así que para ver cómo lo transforma $f$, solo tenemos que centrarnos en el eje $Y$. Cada vez que movemos $i \varepsilon$, la imagen de $f$ se mueve

$$
(\partial_y u + i\, \partial_y v)\, \varepsilon.
$$

<figure>
  <img src="../assets/images/cauchy-riemann/cuadrado-holomorfo.svg" alt="A la izquierda, en gris, un cuadrado pequeño con vértices en 0, ε e iε. A la derecha, en rosa, su imagen por f: otro cuadrado con un vértice en f(0), girado y estirado, cuyos lados son (∂ₓu + i∂ₓv)ε y (∂ᵧu + i∂ᵧv)ε y forman un ángulo recto.">
</figure>

Antes hemos dicho que $f$ es holomórfica cuando, al hacer zoom, gira y estira los puntos. Pero girar y estirar solo puede rotar el cuadrado y cambiar su tamaño. No lo puede deformar. Así que $f$ es holomórfica si y solo si transforma el cuadrado en otro cuadrado. El lado vertical del nuevo cuadrado entonces tiene que ser el lado horizontal girado 90°, y como multiplicar por $i$ es como girar 90°, tenemos que

$$
\partial_y u + i\, \partial_y v = i\,(\partial_x u + i\, \partial_x v) = -\partial_x v + i\, \partial_x u.
$$

Igualando la parte real con la real y la imaginaria con la imaginaria, llegamos a las ecuaciones de Cauchy-Riemann,

$$
\partial_x u = \partial_y v \quad \text{y} \quad \partial_y u = -\partial_x v,
$$

que, aunque parezcan misteriosas, solo dicen que para que una función sea holomórfica, tiene que transformar los cuadrados pequeños en cuadrados.

