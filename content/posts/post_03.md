---
title: "Aprendiendo Processing"
date: 2022-04-22
description: 'Cómo dibujar rayas y bolitas en Processing y hacer que se muevan.'
---

Hace unos años, como proyecto final de una materia de la universidad, hice la animación
de un péndulo doble. Aprendí y disfruté tanto haciéndolo que quería escribir un post al
respecto. El detalle es precisamente ese: aprendí MUCHO. Cosas que no caben en un solo
post. Incluyendo cosas que *no* tienen nada que ver con programación.

No tiene sentido escribir un post que no pueda leerse y entenderse en diez minutos, así
que decidí hacer lo que mejor estoy aprendiendo gracias a NODE: modularizar el tema.
La idea es explicar, en este primer post, cómo usar Processing. Después escribir uno
donde explique cómo usarlo para simular sistemas físicos simples y, finalmente, uno
donde explique cómo simular un péndulo doble, que usa unas ecuaciones bien salvajes.

### ¿Qué es Processing?

Processing es una aplicación que te permite hacer sketches de animaciones 2D con
código. Es gratuita y open source. Para aprender a instalarlo y usarlo, puedes ir a su
[página oficial](https://processing.org/).

### Básicos de Processing

Un programa de Processing tiene dos funciones principales: `setup()` y `draw()`. Tú las
defines. La función `setup()` corre una sola vez, al iniciar el programa. Allí puedes
definir el tamaño de la ventana donde podrás visualizar tu animación, por ejemplo.
Por su parte, `draw()` corre continuamente. ¿Por qué?

Piensa en cómo funcionan las cámaras de video. En realidad son cámaras de fotos súper
rápidas. Toman unas 24 fotos por segundo y, al mostrarlas una detrás de la otra a la
misma velocidad, dan la ilusión de movimiento. La función `draw()` funciona algo así.
En ella programas cómo van a moverse tus dibujitos, y cada nueva corrida es como una
nueva foto.

[Aquí](https://processing.org/reference/) puedes ver todas las funciones disponibles
en Processing, separadas por categorías. En este post, vamos a utilizar las que
aparecen como **2D Primitives**.

### Armar el setup

El siguiente código abre una ventana de 500 pixeles de largo por 200 pixeles de alto
y le pone un fondo color *Middle Blue Green*, que me gusta mucho. La paleta de colores
que voy a usar aquí la tomé de [esta página](https://coolors.co/ccdbdc-80ced7-63c7b2-8e6c88-263d42).
Para pasar de código hex a RGB, utilizo [esta otra](https://www.color-hex.com/color/63c7b2).
Ambas son muy útiles para elegir colores, al menos cuando el diseño no es precisamente
tu especialidad.

```
void setup() {
  size(500, 200);
  background(99, 199, 178);
}
```
Al correr el código, abrirá una ventana que lucirá más o menos así:

<img src="pantalla_verde.png>
