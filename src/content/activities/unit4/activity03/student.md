### Actividad 3

## Tu propuesta con la biblioteca p5LiveMedia

***Describe la aplicación que propones.***
- Esta propuesta consiste en un juego de carreras de bolitas entre jugadores, donde todas comienzan en la parte inferior de la pantalla y deben avanzar hasta la meta, representada por una franja negra en la parte superior. Los jugadores controlan sus bolitas con las flechas del teclado, y la posición de los demás competidores se actualiza en vivo, permitiendo que todos vean el progreso en tiempo real.

***Describe cómo la aplicación propuesta hace uso de la biblioteca p5LiveMedia.***
- Para esta propuesta, decidí utilizar uno de los ejemplos que propone Vanevery sobre el compartir datos en tiempo real y lo combiné con una mecánica de carrera, permitiendo que los jugadores vean su avance en vivo. Las posiciones de las bolitas se actualizan constantemente, de modo que cuando un jugador se mueve en su pantalla, su posición también cambia para los demás, y viceversa.

***Describe cómo la aplicación propuesta se relaciona con el proyecto de curso.***
- La aplicación propuesta está relacionada con los eventos en vivo, que es el enfoque principal del proyecto del curso. De esta manera, sirve como una guía para nuestra bitácora, permitiéndonos mejorar nuestros conocimientos sobre eventos en tiempo real y desarrollar la mejor aplicación posible para la parte final del curso.

***Escribe un tutorial que permita replicar la aplicación propuesta.***
- Paso 1: Abrir el repositorio de Vanevery y luego abrir p5.js
- Paso 2: En el repositorio de Vanevery leer con atención y si es posible ver el video que esta en su cuenta, todo esto es para poder agregar simplepeer y socket.io en el HTML de p5.js
- Paso 3: Cuando ya los allas agregado mas abajo te dejare el codigo de la propuesta y se implementa dicho codigo en el sketch,js
- Paso 4: Antes de eso te registras en p5.js, Luego te vas a "File" como ya te registraste te aparecera una opción que se llama "Share" con la cual puedes copiar el segundo link y abrirlo en una nueva pestaña
- Paso 5: Ya luego de que tengas todo abierto corre la aplicación y veras que cuando vayas cambiando de pestaña se actualizara la posición de cada bolita.
- Paso 6: (Esta en testeo) se comparte el link con un compañero y se realiza la carrera.

***Adiciona el código y enlaces necesarios para replicar la aplicación propuesta.***
- Este es el codigo de mi aplicación propuesta
```js
let myBot;
let otherBots = {};
let p5lm;

function setup() {
  createCanvas(600, 400);
  
 
  myBot = new Bot(random(width), height - 20, color(random(255), random(255), random(255)));

 
  p5lm = new p5LiveMedia(this, "DATA", null, "race-room");
  p5lm.on("data", gotData);
}

function draw() {
  background(220);

 
  fill(0);
  rect(0, 0, width, 20);

  // Dibujar mi bot
  myBot.show();

 
  for (let id in otherBots) {
    otherBots[id].show();
  }
}

function keyPressed() {
  if (keyCode === LEFT_ARROW) myBot.move(-5, 0);
  if (keyCode === RIGHT_ARROW) myBot.move(5, 0);
  if (keyCode === UP_ARROW) myBot.move(0, -5);
  if (keyCode === DOWN_ARROW) myBot.move(0, 5);

  // Enviar la posición actualizada
  let dataToSend = { x: myBot.x, y: myBot.y };
  p5lm.send(JSON.stringify(dataToSend));
}

function gotData(data, id) {
  let d = JSON.parse(data);
  
  if (!otherBots[id]) {
    otherBots[id] = new Bot(d.x, d.y, color(0, 0, 255)); // Color azul para otros jugadores
  } else {
    otherBots[id].x = d.x;
    otherBots[id].y = d.y;
  }
}

// Clase Bot
class Bot {
  constructor(x, y, c) {
    this.x = x;
    this.y = y;
    this.color = c;
  }
  
  move(dx, dy) {
    this.x += dx;
    this.y += dy;
  }
  
  show() {
    fill(this.color);
    ellipse(this.x, this.y, 20, 20);
  }
}
```
- Aqui mostrare como se ve la aplicación planteada

https://github.com/user-attachments/assets/ed89ec38-9261-47c3-9db6-2ff1a365e48a

- https://github.com/vanevery/p5LiveMedia?tab=readme-ov-file  - Esta es la pagina de Vanevery donde si sigue paso a paso mi tutorial se puede replicar la aplicación







