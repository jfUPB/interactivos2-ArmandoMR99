### Actividad 2

## Implementando el núcleo del proceso y la simulación

- Voy a adjuntar los codigos respectivos de cada cliente, se pudo llevar a cabo el cliente de mobile y desktop, adjuntare los html, los sketch y el server.js

________________________________________________________________________________________________

**Mobile**
- HTML
```js
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <script src="https://cdn.jsdelivr.net/npm/p5@1.11.0/lib/p5.min.js"></script>
    <script src="https://cdn.socket.io/4.7.5/socket.io.min.js"></script>
    <script src="sketch.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/1.6.0/addons/p5.sound.min.js"></script>

    <title>Mobile p5.js Application</title>
</head>
<body></body>
</html>
```
- Sketch
```js
let socket;
let song;
let bpm = 60; // valor por defecto

function preload() {
  song = loadSound('/assets/cancion.mp3');
}

function setup() {
  createCanvas(windowWidth, windowHeight);
  textAlign(CENTER, CENTER);
  textSize(24);
  fill(255);

  socket = io(); // conexión automática a la misma URL/puerto del servidor

  socket.on('connect', () => {
    console.log('Conectado al servidor');
  });

  socket.on('bpm', (data) => {
    bpm = data;
    console.log('BPM recibidos:', bpm);
    updatePlaybackRate();
  });

  // Espera a que el usuario toque para iniciar la música (política del navegador)
  userStartAudio().then(() => {
    if (!song.isPlaying()) {
      song.loop();
    }
  });
}

function draw() {
  background(30);
  text(`BPM actuales: ${bpm}`, width / 2, height / 2);
}

function updatePlaybackRate() {
  // Ajuste proporcional (puedes afinar esto)
  let rate = map(bpm, 40, 180, 0.5, 2.0, true);
  console.log(`rate: ${rate}`);
  
  song.rate(rate);
}
```

______________________________________________________________________________________________________

**Desktop**
- HTML
```js
<!DOCTYPE html>
<html lang="es">
  <head>
    <meta charset="UTF-8" />
    <title>Mobile Reproductor</title>
    <script src="/socket.io/socket.io.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/1.4.0/p5.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/1.4.0/addons/p5.sound.min.js"></script>
  </head>
  <body>
    <script src="sketch.js"></script>
  </body>
</html>
```
- Sketch
```js
let bpmSlider;
let bpm = 90;
let socket;

function setup() {
  createCanvas(400, 200);
  textAlign(CENTER, CENTER);

  // Crear el slider de BPM (60-180)
  bpmSlider = createSlider(60, 180, 90);
  bpmSlider.position(20, 60);
  bpmSlider.style('width', '360px');

  socket = io(); // conexión automática

  // Enviar BPM cada 100ms
  setInterval(() => {
    bpm = bpmSlider.value();
    socket.emit('bpm', bpm);
  }, 100);
}

function draw() {
  background(30);
  fill(255);
  textSize(20);
  text("Simulación de BPM", width / 2, 20);
  textSize(32);
  text(bpmSlider.value() + " LPM", width / 2, 120);
}
```

____________________________________________________________________________________________________

**Server.js**
```js
const express = require('express');
const app = express();
const http = require('http').createServer(app);
const io = require('socket.io')(http);

app.use(express.static('public'));

io.on('connection', (socket) => {
  console.log('Un cliente conectado');

  socket.on('bpm', (data) => {
    socket.broadcast.emit('bpm', data);
  });

  socket.on('mouseMovement', (data) => {
    socket.broadcast.emit('mouseMovement', data); // Para que "generativo" reciba
  });

  socket.on('disconnect', () => {
    console.log('Cliente desconectado');
  });
});

const PORT = process.env.PORT || 3000;
http.listen(PORT, () => {
  console.log('Servidor escuchando en puerto', PORT);
});
```





