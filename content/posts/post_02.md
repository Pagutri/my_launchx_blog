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


