---
author: Pazthor
categories:
- lessons
date: "2020-10-05T00:00:00Z"
draft: true
homepage: https://github.com/
license: MIT License
license_link: https://github.com/
tagline: Supporting tagline
tags:
- intro
- beginner
- jekyll
- tutorial
thumbnail: scribble.png
title: notas emacs
---


### Funciona para la versión de emacs 24.5.1 y con la interfaz gráfica.


## Mover por páginas##
Ctrl v – (siguiente)
Alt v – (anterior)
Ctrl l – Limpiar la pantalla y volver a mostrar todo el texto, moviendo el texto alrededor del cursor al centro de la pantalla.

##Moverse entre el texto##
Ctrl f – Moverse un caracter hacia adelante
Ctrl b – Moverse un caracter hacia atrás
Alt f – Moverse una palabra hacia adelante
Alt b – Moverse una palabra hacia atrás

Ctrl n – Moverse a la siguiente línea
Ctrl p – Moverse a la línea anterior
Ctrl a – Moverse al comienzo de una línea
Ctrl e – Moverse al final de una línea
Alt a – Moverse al inicio de una oración
Alt e – Moverse al final de una oración

##Alterando el texto##
Ctrl k – kill, “mata” el texto. Esto implica que lo borra, pero lo mantiene guardado y puede ser recuperado con Ctrl Y.
Ctrl d – Borra un caracter (borra, no mata, no puede ser recuperado).
Alt d – Borra palabras

Ctrl @ / Ctrl Espacio – marca el texto (primera marca)
Ctrl w – corto texto desde la marca de texto.
Alt w – copia texto desde la marca de texto.
Ctrl h – Marcar todo el buffer, como “Seleccionar todo”.

Ctrl y – “Yanks text”, pega el texto matado o cortado/copiado con w.
Alt y – Recorre yanks previos, podemos recuperar algo que matamos varios Ctrl k antes.

Ctrl g – Cancelar comandos
Ctrl x u – Deshacer
Ctrl / – Deshace

##Ctrl x - Comandos##
Ctrl x Ctrl f – “Visitar” nuevo archivo (si existe lo abre, sino lo crea).
Ctrl g – Cancelar comandos

###Buffers###

Ctrl x Ctrl b – Listar buffers. En Emacs no hay “pestañas” o “ventanas”. Cada archivo se abre en un buffer. Con este comando vemos todos los buffers que hayan abiertos en esta sesión de Emacs.



Ctrl x 2 – Divide la ventana en 2 de forma horizontal.
Ctrl x 3 – Divide la ventana en 2 de manera vertical.
Ctrl x 1 – Deja solo una ventana abierta.
Ctrl Alt v – scrollea la ventana donde no tengo el foco.
Ctrl x o – cambia el cursor de una ventana a otra
