👾 Space Invaders con Bosses – Proyecto Organización de Computadores (Nand2Tetris)
Integrantes

Samuel Arango

Samuel Moncada

Sara Hurtado

⭐ Descripción General

Este proyecto es una versión extendida de Space Invaders, desarrollada completamente en Jack para el curso Organización de Computadores.
El jugador controla una nave que se desplaza horizontalmente, destruye enemigos, esquiva disparos, obtiene power-ups y se enfrenta a múltiples jefes finales.

El juego está compuesto por 5 niveles, y para avanzar al siguiente nivel es necesario:

Destruir todos los enemigos/obstáculos del nivel, y

Derrotar al jefe final de ese nivel

Además, entre más enemigos eliminemos, mayor probabilidad hay de recibir power-ups, los cuales mejoran temporalmente las habilidades del jugador.

Todo esto se ejecuta dentro del entorno Nand2Tetris, interactuando directamente con las APIs de hardware simulado (Screen, Keyboard, Sys, Memory).

🧠 Relación con Organización de Computadores

Este proyecto demuestra conceptos clave del curso:

✔ Interacción directa con el hardware simulado

Uso de Screen.drawPixel, Screen.drawRectangle, Screen.drawLine

Lectura de teclado por Keyboard.keyPressed

Control de tiempo con Sys.wait

Gestión de memoria con Memory.peek y Memory.poke

✔ Arquitectura en capas

Lógica del juego (Game, Player, Enemy, Boss)

Motor de render seguro (SafeScreen)

Animación del fondo (Starfield)

Sistema de objetos y colisiones (Rect)

Manejo de entrada (InputHandler)

✔ Ciclo de ejecución estilo CPU
Input → Update → Collisions → Render → Wait → Repeat

🧩 Arquitectura del Proyecto

El código está organizado modularmente en múltiples clases:

Archivo	Función
Main.jack	Punto de entrada del programa
Game.jack	Game loop, niveles, actualización y render
Player.jack	Movimiento y disparos del jugador
Bullet.jack	Balas del jugador
Enemy.jack	Lógica de enemigos individuales
EnemyGrid.jack	Organización y movimiento grupal de enemigos
EnemyShot.jack	Disparos enemigos
Boss.jack	Jefe final de cada nivel, con vida y patrones
PowerUp.jack	Sistema de power-ups según enemigos destruidos
InputHandler.jack	Lectura estructurada del teclado
Starfield.jack	Animación del fondo
SafeScreen.jack	Render sin parpadeos (anti-flicker)
Rect.jack	Geometría y colisiones
🎮 Jugabilidad

← → : Mover la nave

Espacio : Disparar

Objetivo por nivel:

Destruir todos los enemigos

Derrotar al Boss

Power-Ups:

Se obtienen al eliminar enemigos

Mejoran velocidad, disparos y habilidades

Avance de niveles:

El juego tiene 5 niveles progresivos

Cada nivel incrementa:

dificultad de enemigos

velocidad

frecuencia de disparos

comportamiento del jefe

🚀 Mecánicas Avanzadas
✔ Sistema de 5 niveles

Cada nivel tiene su propio conjunto de enemigos, velocidades y boss.

El jugador solo avanza si supera completamente el nivel anterior.

✔ Enemigos en Grilla

Movimiento sincronizado, inspirado en Space Invaders clásico

Descenso al llegar a bordes

Comportamiento más rápido en niveles altos

✔ Boss Final por Nivel

Vida propia

Disparos especiales

Patrones únicos de movimiento

✔ Power-Ups Dinámicos

Se otorgan según la cantidad de enemigos destruidos:

Velocidad aumentada

Disparo doble

Menor cooldown

Disparo más rápido o más ancho

✔ Starfield Animado

Un fondo de estrellas en movimiento que da profundidad visual.

✔ SafeScreen Anti-Flicker

Evita parpadeos típicos de la API de Screen en Jack, mejorando la experiencia visual:

Dibujo ordenado

Limpieza controlada

Actualización eficiente

📂 Estructura del Proyecto
├── Main.jack
├── Game.jack
├── Player.jack
├── Bullet.jack
├── Enemy.jack
├── EnemyGrid.jack
├── EnemyShot.jack
├── Boss.jack
├── PowerUp.jack
├── InputHandler.jack
├── Starfield.jack
├── SafeScreen.jack
└── Rect.jack

▶️ Cómo Ejecutarlo

Abrir JackCompiler y compilar la carpeta del proyecto.

Abrir VMEmulator.

Cargar la carpeta compilada.

Configurar:

Screen: FAST

Animator: Max speed

Ejecutar con Run.

🏆 Créditos

Desarrollado por:

Samuel Arango

Samuel Moncada

Sara Hurtado

Para el curso Organización de Computadores – Nand2Tetris.
