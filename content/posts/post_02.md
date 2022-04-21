---
title: "Cómo programar un péndulo doble con javascript"
date: 2022-04-21
description: 'Todo el mundo conoce las leyes de Newton para las fuerzas, 
pero pocas personas conocen su contraparte: las leyes de Lagrange para la energía. 
En este post, muestro cómo usar estas leyes y algo llamado  método de
Runge-Kutta para hacer una animación de un péndulo doble en Processing.js'
---

Hoy les quiero presentar el que fue mi proyecto final de la materia de métodos numéricos
en la universidad. Disfruté mucho haciéndolo. Creo que es un bonito ejemplo del proceso
que hay que seguir a la hora de pasar de la teoría en papel al código.

Sería muy largo explicar el por qué de cada cachito de conocimiento utilizado en este
proyecto. Lo que quiero con este post es que por lo menos se den una idea de cuáles
serían los pasos a seguir si quisieran hacer algo similar. Para programar sistemas más
sencillos, como una bola de billar moviéndose en línea recta o una pelota de béisbol
luego de batearla, el proceso es también mucho más sencillo y no requiere tantas
matemáticas. Pueden ver un ejemplo con Python [aquí](https://www.petercollingridge.co.uk/tutorials/pygame-physics-simulation/).
Para el péndulo doble tal vez también hay métodos más sencillos, pero este es el que me sé jaja.

¡Comencemos!

# Paso 1. Definir el sistema
## ¿Qué es un péndulo doble?
Un peńdulo simple es cualquier objeto colgando de una cuerda, moviéndose en un
sólo plano (es decir, de izquierda a derecha y de abajo hacia arriba, pero no de
atrás hacia adelante) por efecto de la gravedad. Aquí hay un gif que lo muestra:
![Gif de un péndulo simple](http://www.netanimations.net/Moving-animated-clip-art-picture-of-pendulum-x-bpm-1.gif)

Un péndulo doble son dos péndulos simples pegados uno al final del otro, como en
el siguiente gif:
![Gif de un péndulo doble](https://revolution-computing.typepad.com/.a/6a010534b1db25970b0192aa7aa4a6970d-pi)

En el gif anterior, podemos ver que el primer péndulo simple, el de arriba, traza
simples arcos de circunferencia al moverse. El segundo péndulo, el de abajo, traza
lo que en México conocemos como un desmadre. Por eso (spoiler alert) sus ecuaciones
de movimiento son tan complicadas.

En la vida real, las cuerdas pesan, se curvan, se estiran y se desgastan. Pero para
hacernos la vida más fácil, vamos a suponer que no.

# Paso 2. Encontrar las ecuaciones de movimiento
## ¿En dónde va a estar la bolita en cada instante de tiempo?

# Paso 3. Resolver las ecuaciones de movimiento
## Dos señores alemanes llamados Runge y Kutta

# Paso 4. Hacer la animación
## Cómo utilizar Processing.js

# Bonus. Sistemas dinámicos
