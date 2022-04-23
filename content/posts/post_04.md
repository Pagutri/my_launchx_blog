---
title: "Física en Animaciones Parte 2: Movimiento"
date: 2022-04-23
description: 'En esta segunda parte, explico cómo hacer que las figuras que
dibujamos en la parte 1 se muevan.'
---

En física, nos gusta ir de lo más simple a lo más complicado. En movimiento, lo
más más simple es una sola partícula (o bolita) moviéndose en línea recta a
velocidad constante sin paredes ni fricción ni nada que le estorbe. En este post,
vamos a usar Processing para simular este tipo de movimiento.

En [el post anterior](https://pagutri.github.io/my_launchx_blog/posts/post_03/)
expliqué cómo dibujar bolitas en Processing. Hoy vamos a arrancar con una 
bolita negra colocada al tuntún:

```
void setup() {
  size(500, 300);
}

void draw() {
  fill(0);
  circle(150, 100, 15);
}
```

<a href="https://imgbb.com/"><img src="https://i.ibb.co/px9CC6f/tuntun.png" alt="tuntun" border="0"></a>

Pero no quiero colocarla al tuntún. Quiero que empiece pegada a la izquierda y a
media pantalla. Sabiendo que la pantalla mide 300 pixeles de alto y que 150 es la
mitad de 300, bastaría escribir `circle(0, 150, 15)`. Eso es un ejemplo de una mala
práctica llamada [hard coding](https://es.wikipedia.org/wiki/Hard_code).

Para evitarla, podemos usar una variable que guarde el valor de las medidas de la pantalla.
Processing lo hace automáticamente por nosotros. Una vez que llamamos a la función `size()`
en `setup()`, la altura de la ventana se guarda en la variable `height` y su largo se
guarda en `width`. Ya podemos usarlas.

```
void setup() {
  size(500, 300);
}

void draw() {
  fill(0);
  circle(0, height / 2, 15);
}
```
<a href="https://imgbb.com/"><img src="https://i.ibb.co/H47WLmj/traslape.png" alt="traslape" border="0"></a>

Bien. La bolita ya está al inicio y a media pantalla, pero sigue habiendo un problema:
Sólo vemos la mitad. Como vimos en el post anterior, la funcion `circle()` recibe las
coordenadas del **centro** del círculo. El centro es lo que ubicamos en la coordenada 0. 
Yo quiero que el **borde** sea lo que toque la orilla de la pantalla. Para eso,
creo una variable que guarde el radio de la bolita y la ubico a un radio de distancia
de la orilla.

Las variables en Processing pueden ser **locales** o **globales**. Si defino una variable
en el cuerpo una función, sólo puedo utilizarla dentro de esa función. Es una variable
local. Si la defino fuera de todas las funciones, entonces es global y puedo usarla en
cualquier logar del programa.



