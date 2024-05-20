# Break Out Game en C# y Windows Form

---

## Función General

El juego Breakout se desarrolla mediante el movimiento de una pelota que rebota dentro de los límites del formulario y destruye bloques. El jugador controla una plataforma que se mueve a la izquierda y a la derecha para evitar que la pelota caiga fuera del formulario. El objetivo es destruir todos los bloques sin dejar que la pelota caiga, incrementando la puntuación a medida que se destruyen los bloques. Cuando todos los bloques son destruidos, el jugador gana, y si la pelota cae fuera del formulario, el jugador pierde.

---

## Interacciones Principales

- **Movimiento del jugador**: Controlado mediante las teclas izquierda y derecha del teclado, detectadas en los métodos keyisdown y keyisup.
- **Movimiento de la pelota**: Actualizado en cada tick del temporizador en mainGameTimerEvent, manejando colisiones con los límites del formulario, el jugador y los bloques.
- **Bloques**: Colocados al inicio del juego con PlaceBlocks y removidos con removeBlocks.

---

## Funcionamiento Interno

### Clases

- La clase Form1 hereda de Form y contiene toda la lógica del juego Breakout.

### Métodos

- **public Form1()**: Constructor de la clase. Inicializa los componentes y coloca los bloques en el formulario.
- **private void setupGame()**: Configura el estado inicial del juego, resetea variables como isGameOver, score, ballx, bally, y playerSpeed, y posiciona la pelota y el jugador. También inicia el temporizador del juego (gameTimer).
- **private void gameOver(string message)**: Detiene el juego, muestra un mensaje de fin de juego y actualiza la variable isGameOver a true.
- **private void PlaceBlocks()**: Coloca los bloques en el formulario, organiza su posición y los agrega al arreglo blockArray. Luego, llama al método setupGame para iniciar el juego.
- **private void removeBlocks()**: Elimina todos los bloques del formulario.
- **private void mainGameTimerEvent(object sender, EventArgs e)**: Controla la lógica principal del juego y se ejecuta en cada tick del temporizador (gameTimer). Maneja el movimiento de la pelota y el jugador, la detección de colisiones entre la pelota y los bloques/jugador, y verifica las condiciones de victoria o derrota.
- **private void keyisdown(object sender, KeyEventArgs e)**: Detecta cuando una tecla se presiona. Si es la tecla izquierda o derecha, establece goLeft o goRight a true.
- **private void keyisup(object sender, KeyEventArgs e)**: Detecta cuando una tecla se suelta. Si es la tecla izquierda o derecha, establece goLeft o goRight a false. Si es la tecla Enter y el juego ha terminado, elimina los bloques y coloca nuevos para reiniciar el juego.

### Variables

- **bool goLeft**: Indica si el jugador está presionando la tecla para mover el jugador hacia la izquierda.
- **bool goRight**: Indica si el jugador está presionando la tecla para mover el jugador hacia la derecha.
- **bool isGameOver**: Indica si el juego ha terminado.
- **int score**: Almacena la puntuación del jugador.
- **int ballx**: Velocidad horizontal de la pelota.
- **int bally**: Velocidad vertical de la pelota.
- **int playerSpeed**: Velocidad de movimiento del jugador.
- **Random rnd**: Generador de números aleatorios para varias operaciones, como cambiar la velocidad y color de los bloques.
- **PictureBox[] blockArray**: Arreglo que contiene los bloques del juego.

---

## Imágenes

![image](https://github.com/jdanielcalle/BreakOutGame/assets/90487680/64837c00-7818-4266-9e71-36871590a4cb)

![image](https://github.com/jdanielcalle/BreakOutGame/assets/90487680/64b5cb2d-7b38-4fa6-af46-9d156f103669)

---

## Más Información

### Miembros

- [Jair Daniel Calle Sinitave](https://www.linkedin.com/in/jair-daniel-calle-sinitave/)
- [Daniel Estiven Villegas Bedoya](https://www.linkedin.com/in/daesvi/)
