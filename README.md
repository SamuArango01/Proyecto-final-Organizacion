👾 Space Invaders con Bosses
Proyecto – Organización de Computadores (Nand2Tetris)
Integrantes:

Samuel Arango

Samuel Moncada

Sara Hurtado

Este proyecto corresponde al curso Organización de Computadores y fue desarrollado completamente en Jack, el lenguaje de alto nivel del ecosistema Nand2Tetris, ejecutándose sobre la máquina virtual diseñada en el curso.

Creamos una versión extendida del clásico Space Invaders, incorporando enemigos, disparos, power-ups y un Boss final, demostrando dominio de:

programación orientada a objetos en Jack

manejo del hardware simulado (Screen, Keyboard, Memory)

uso correcto de la VM y del compilador Jack

diseño modular y eficiente

control de pantallas, animaciones y colisiones usando APIs del sistema

⭐ Descripción General

Space Invaders con Bosses es un videojuego en donde:

El jugador controla una nave que se mueve horizontalmente.

Dispara para eliminar enemigos ubicados en una grilla.

Los enemigos avanzan y disparan aleatoriamente.

Existen power-ups que mejoran temporalmente las habilidades del jugador.

Tras eliminar a todos los enemigos aparece un Boss final, con vida propia y ataques más complejos.

Todo esto corre sobre el ambiente del VMEmulator de Nand2Tetris.

🧠 Relación con Organización de Computadores

Este proyecto demuestra conceptos clave del curso:

✔ Interacción con el Hardware Simulado

Uso directo de las APIs del hardware del curso:

Screen.drawPixel, drawLine, drawRectangle

Keyboard.keyPressed

Memory.peek y Memory.poke

Implementación manual de:

renderizado eficiente

detección de colisiones basada en memoria

animaciones usando ciclos de CPU (Sys.wait)

✔ Arquitectura en Capas

Se aplican los principios del curso:

Capa de aplicación: lógica del juego

Capa de abstracción gráfica: SafeScreen para evitar flickering

Capa de VM/Hack: ejecución en la máquina virtual

Hardware simulado: interacción con pantalla y teclado

✔ Control del Ciclo de Ejecución

El loop principal replica un ciclo de máquina simple:

Input → Update → Collisions → Render → Wait → Repeat


similar a un fetch–decode–execute pero aplicado a videojuegos.

🧩 Arquitectura del Proyecto

El código está organizado en módulos independientes que representan subsistemas del juego:

Archivo	Función
Main.jack	Punto de entrada del programa
Game.jack	Loop principal, actualización y render
Player.jack	Lógica del jugador
Bullet.jack	Disparos del jugador
Enemy.jack	Lógica de enemigos individuales
EnemyGrid.jack	Organización y movimiento grupal
EnemyShot.jack	Disparos enemigos
Boss.jack	Jefe final con vida y patrón de ataque
PowerUp.jack	Sistema de power-ups
InputHandler.jack	Lectura estructurada del teclado
Starfield.jack	Fondo animado
SafeScreen.jack	Dibujo libre de flickering
Rect.jack	Representación geométrica y colisiones
🔧 Mecánicas del Juego
✔ Movimiento del jugador

Basado en lectura directa del teclado a través de la API del hardware.

✔ Disparos

Objetos Bullet y EnemyShot que se actualizan en arreglos dinámicos.

✔ Enemigos en Grilla

Movimiento sincronizado inspirado en el original Space Invaders:

se mueven horizontalmente

bajan cuando tocan un borde

velocidad aumenta cuando hay menos enemigos

✔ Boss Final

Con:

vida

disparos más complejos

patrón de movimiento independiente del grid

✔ Power-Ups

Implementados como objetos que se actualizan y detectan contacto con el jugador.

✔ Starfield

Fondo dinámico para simular profundidad usando varios niveles de movimiento.

✔ SafeScreen

Evita el parpadeo típico de Screen.draw en Jack optimizando:

borrados parciales

orden de render

doble-buffer visual simple

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

Abre JackCompiler y compila la carpeta del proyecto.

Abre VMEmulator.

Carga la carpeta compilada.

Configura:

Screen: FAST

Animation speed: Max

Ejecuta con Run.
