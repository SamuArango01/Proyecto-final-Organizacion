

````markdown
# Space Invaders con Bosses – Proyecto Organización de Computadores (Nand2Tetris)

## Integrantes

- Samuel Arango  
- Samuel Moncada  
- Sara Hurtado  

---

## Descripción general

Este proyecto es una versión extendida de **Space Invaders**, desarrollada completamente en **Jack** para el curso **Organización de Computadores**.  
El jugador controla una nave que se desplaza horizontalmente, destruye enemigos, esquiva disparos, obtiene power-ups y se enfrenta a múltiples jefes finales.

El juego está compuesto por **5 niveles** y, para avanzar al siguiente nivel, es necesario:

- Destruir todos los enemigos/obstáculos del nivel.  
- Derrotar al jefe final de ese nivel.  

Además, **entre más enemigos eliminemos, mayor probabilidad hay de recibir power-ups**, los cuales mejoran temporalmente las habilidades del jugador.

Todo esto se ejecuta dentro del entorno **Nand2Tetris**, interactuando directamente con las APIs de hardware simulado (`Screen`, `Keyboard`, `Sys`, `Memory`).

---

## Relación con Organización de Computadores

Este proyecto demuestra conceptos clave del curso:

### Interacción con el hardware simulado

- Uso de `Screen.drawPixel`, `Screen.drawRectangle`, `Screen.drawLine`.  
- Lectura de teclado con `Keyboard.keyPressed`.  
- Control del tiempo con `Sys.wait`.  
- Gestión de memoria con `Memory.peek` y `Memory.poke`.

### Arquitectura en capas

- **Lógica del juego**: `Game`, `Player`, `Enemy`, `Boss`, `PowerUp`.  
- **Motor de render seguro**: `SafeScreen`.  
- **Animación del fondo**: `Starfield`.  
- **Sistema de objetos y colisiones**: `Rect`.  
- **Manejo de entrada**: `InputHandler`.  

### Ciclo de ejecución

```text
Input → Update → Collisions → Render → Wait → Repeat
````

---

## Arquitectura del proyecto

El código está organizado modularmente en múltiples clases:

| Archivo             | Función                                                 |
| ------------------- | ------------------------------------------------------- |
| `Main.jack`         | Punto de entrada del programa                           |
| `Game.jack`         | Game loop, manejo de niveles, actualización y render    |
| `Player.jack`       | Movimiento y disparos del jugador                       |
| `Bullet.jack`       | Balas del jugador                                       |
| `Enemy.jack`        | Lógica de enemigos individuales                         |
| `EnemyGrid.jack`    | Organización y movimiento grupal de enemigos            |
| `EnemyShot.jack`    | Disparos enemigos                                       |
| `Boss.jack`         | Jefe final de cada nivel, con vida y patrones de ataque |
| `PowerUp.jack`      | Sistema de power-ups según enemigos destruidos          |
| `InputHandler.jack` | Lectura estructurada del teclado                        |
| `Starfield.jack`    | Animación del fondo                                     |
| `SafeScreen.jack`   | Renderizado sin parpadeos (anti-flicker)                |
| `Rect.jack`         | Geometría y detección de colisiones                     |

---

## Jugabilidad

* **← / →** : Mover la nave.
* **Espacio** : Disparar.

### Objetivo por nivel

* Destruir todos los enemigos/obstáculos del nivel.
* Derrotar al **Boss** de ese nivel.

### Power-ups

* Se obtienen al eliminar enemigos.
* Pueden mejorar:

  * velocidad del jugador,
  * frecuencia de disparo,
  * tipo o cantidad de balas,
  * otras habilidades temporales.

### Progresión de niveles

El juego tiene **5 niveles progresivos**.
En cada nivel aumenta:

* la cantidad y velocidad de los enemigos,
* la frecuencia de disparos enemigos,
* la complejidad del patrón del jefe.

---

## Mecánicas avanzadas

### Sistema de 5 niveles

Cada nivel introduce cambios en la dificultad, tipo de enemigos y comportamiento del jefe final, haciendo el reto progresivo y coherente.

### Enemigos en grilla

* Movimiento sincronizado horizontal.
* Descenso al tocar los bordes de la pantalla.
* Velocidad que puede incrementarse a medida que se eliminan enemigos.

### Boss por nivel

* Vida propia.
* Disparos más complejos.
* Patrones de movimiento distintos al resto de enemigos.

### Power-ups dinámicos

* Relacionados con la cantidad de enemigos destruidos.
* Diseñados para recompensar el juego ofensivo y la supervivencia.

### Starfield animado

* Fondo dinámico que simula profundidad espacial.

### SafeScreen (anti-flicker)

* Evita parpadeos en pantalla controlando la forma en que se limpian y redibujan los elementos.
* Mejora la experiencia visual dentro de las limitaciones del hardware simulado.

---

## Estructura del proyecto

```text
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
```

---

## Cómo ejecutarlo

1. Abrir **JackCompiler** y compilar la carpeta del proyecto.
2. Abrir **VMEmulator**.
3. Cargar la carpeta compilada.
4. Configurar:

   * *Screen* en modo **FAST**.
   * Velocidad del simulador al máximo.
5. Presionar **Run** para iniciar el juego.

---

## Créditos

Proyecto desarrollado para el curso **Organización de Computadores – Nand2Tetris** por:

* **Samuel Arango**
* **Samuel Moncada**
* **Sara Hurtado**

```
```
