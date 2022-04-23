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
