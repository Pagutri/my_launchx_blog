---
title: "Física en Animaciones Parte 1: Básicos de Processing"
date: 2022-04-23
description: 'En esta primera parte, explico qué es Processing y cómo usarlo
para dibujar figuras geométricas.'
---

Hace unos años, como proyecto final de una materia de la universidad, hice la animación
de un péndulo doble. Aprendí y disfruté tanto haciéndolo que quería escribir un post al
respecto. El detalle es precisamente ese: aprendí MUCHO. Cosas que no caben en un solo
post. Incluyendo cosas que *no* tienen nada que ver con programación.

No tiene sentido escribir un post que no pueda leerse y entenderse en diez minutos, así
que decidí hacer lo que mejor estoy aprendiendo gracias a NODE: modularizar el tema.
La idea es explicar, post a post, cómo pasar de un fenómeno físico a las fórmulas que lo
describen, de las fórmulas al código y del código a la animación. En este primer post,
explico cómo hacer dibujos en Processing. En el siguiente post, quiero explicar cómo
hacer que esos dibujos se muevan.

### ¿Qué es Processing?

Processing es una aplicación que te permite hacer sketches de animaciones 2D con
código. Es gratuita y open source. Para aprender a instalarlo y correrlo, puedes ir a su
[página oficial](https://processing.org/).

### Básicos de Processing

Un programa de Processing tiene dos funciones principales: `setup()` y `draw()`. Tú las
defines. La función `setup()` corre una sola vez, al iniciar el programa. Allí puedes
definir el tamaño y las características de la ventana donde quieres visualizar tu animación.
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
que voy a usar aquí la tomé de [esta página](https://coolors.co/ff9fb2-80ced7-63c7b2-f5e960-654f6f).
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

<a href="https://imgbb.com/"><img src="https://i.ibb.co/s9yk2jz/pantalla-verde.png" alt="pantalla-verde" border="0"></a><br /><a target='_blank' href='https://es.imgbb.com/'>imagenes e</a><br />

### Dibujar formas básicas

Para dibujar una línea recta, usamos la función `line()`. Ésta recibe cuatro parámetros.
Los dos primeros son las coordenadas del punto donde empieza la línea. Los dos últimos
son las coordenadas del punto donde termina la línea. Fácil. Sólo hay que
señalar un pequeño detalle: en Processing, el origen del sistema de coordenadas es la
esquina superior izquierda de la ventana de la animación. Las coordenadas en **x**
aumentan de izquierda a derecha, y las coordenadas en **y** aumentan de arriba hacia
abajo, como se muestra en la imagen de la derecha:

<a href="https://processing.org/tutorials/coordinatesystemandshapes"><img src="https://processing.org/3e3972693a7deb9dbe15199c186d2917/drawing-03.svg"></a>

El siguiente código dibuja una sencilla línea horizontal (observa que la coordenada **y**
es igual para el punto final y para el inicial):

```
void draw() {
  line(120, 80, 340, 80);
}
```

Para dibujar una circunferencia, usamos la función `circle()`. Ésta recibe tres parámetros:
las dos coordenadas del centro del círculo y su diámetro. Si queremos cambiar el color de relleno, usamos la
función `fill()`, y si queremos engrosar el borde, usamos `strokeWeight()`. El siguiente código:

```
void setup() {
  size(500, 300);
  background(99, 199, 178);
}

void draw() {
  fill(142, 108, 136);
  strokeWeight(10);
  line(120, 80, 340, 80);
  circle(224, 184, 120);
  circle(150, 100, 80);
}
```

Dibuja algo como esto:

<a href="https://imgbb.com/"><img src="https://i.ibb.co/bJfSN3s/two-circles.png" alt="two-circles" border="0"></a>

Las características que definí con `fill()` y `strokeWeight()` se aplican a todas las figuras que dibujé.
Esto es porque, para cada nueva figura, Processing toma las últimas características definidas, leyendo de
arriba hacia abajo. Por ejemplo, si queremos cambiar el borde y el relleno del circulo más pequeño, 
podemos hacer algo como esto:

```
void setup() {
  size(500, 300);
  background(99, 199, 178);
}

void draw() {
  fill(142, 108, 136);
  strokeWeight(10);
  line(120, 80, 340, 80);
  circle(224, 184, 120);
  fill(255, 159, 178);
  strokeWeight(4);
  circle(150, 100, 80);
}
```

<a href="https://imgbb.com/"><img src="https://i.ibb.co/HpVQ6M2/two-new-circles.png" alt="two-new-circles" border="0"></a>

Listo. Esto es todo lo que necesitamos saber por ahora. Si quieres aprender más, da clic
[aquí](https://processing.org/tutorials/) y explora los cursos y tutoriales que ofrece el equipo de
Processing. ¡Nos vemos en el siguiente post!
