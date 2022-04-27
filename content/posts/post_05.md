---
title: "Física en Animaciones Parte 3: Movimiento en dos dimensiones"
date: 2022-04-27
description: 'En esta tercera parte, explico cómo hacer que la bolita que
dibujamos en la parte 2 se mueva en diagonal y formando parábolas'
---

[El post anterior](https://pagutri.github.io/my_launchx_blog/posts/post_04/)
termina con una pregunta: ¿cómo hacer que la bolita se mueva en diagonal?
La respuesta es: aumentando ambas coordenadas en lugar de una sola. El
siguiente código lo hace:

```
int radius = 8;
int diameter = 2 * radius;
int x = radius;
int y = 0;

void setup() {
  size(500, 500);
  fill(0);
  //y = height - radius; //Start on the left-bottom corner
  y = radius; //Start on the left-top corner
  circle(x, y, diameter);
}

void draw() {
  background(255); //Comment this line if you want to see the trayectory
  x += 1;
  //y -= 1; //Move upwards
  y += 1; //Move downwards
  circle(x, y, diameter);
}
```

Hay que tener cuidado al inicializar las variables **x**, **y**. Al inicio del programa,
declaré la variable **y** pero, sabiendo que iba a utilizar `height` para definir
su valor inicial, la inicialicé **después** de llamar a la función `size()`.

La trayectoria que describe la bolita sigue siendo una línea recta.
Recomiendo probar con distintos valores del incremento de las coordenadas y observar
qué sucede antes de pasar al siguiente párrafo. La única condición es probar con valores
enteros (¡No podemos sumar ni restar fracciones de pixel!).

Mis observaciones al experimentar con distintos incrementos se resumen en que la **velocidad**
y la **pendiente** de la recta cambian. Pero para poder hablar de cómo cambian de manera
precisa, hay que explicar cómo se miden los **ángulos** y el **tiempo** en Processing.

### Los ángulos en Processing

