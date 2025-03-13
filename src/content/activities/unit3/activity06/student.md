### Actividad 6

## Reto de transferencia del aprendizaje

- ***Server.js***

```js
const express = require('express');
const http = require('http');
const socketIO = require('socket.io');

const app = express();
const server = http.createServer(app);
const io = socketIO(server);
const port = 3000;

app.use(express.static('public'));

io.on('connection', (socket) => {
    console.log('New client connected');

    socket.on('image', (imgData) => {
        console.log('Imagen recibida, retransmitiendo...');
        io.emit('image', imgData); // Se usa io.emit para enviar la imagen a TODOS los clientes conectados
    });

    socket.on('disconnect', () => {
        console.log('Client disconnected');
    });
});

server.listen(port, () => {
    console.log(`Server is listening on http://localhost:${port}`);
});
```

- ***Sketch.js/mobile***

```js
let socket;
let receivedImage;

function setup() {
    createCanvas(400, 400);
    background(220);

    let socketUrl = 'https://laughing-goggles-5g494jpgj9rqf47g9-3000.app.github.dev/';
    socket = io(socketUrl);

    socket.on('connect', () => {
        console.log('Connected to server');
    });

    socket.on('image', (data) => {
        console.log('Imagen recibida');
        receivedImage = loadImage(data); // Cargar la imagen recibida
    });
}

function draw() {
    background(220);
    textSize(20);
    textAlign(CENTER);
    fill(0);
    text('Esperando imagen...', width / 2, 30);

    if (receivedImage) {
        image(receivedImage, 100, 50, 200, 200);
    }
}
```

- ***Sketch.js/desktop***

```js
let socket;
let capture;
let sendButton;

function setup() {
    createCanvas(400, 400);
    background(220);

    let socketUrl = 'https://laughing-goggles-5g494jpgj9rqf47g9-3000.app.github.dev/';
    socket = io(socketUrl);

    socket.on('connect', () => {
        console.log('Connected to server');
    });

    socket.on('disconnect', () => {
        console.log('Disconnected from server');
    });

    // Captura de video desde la cámara
    capture = createCapture(VIDEO);
    capture.size(200, 200);
    capture.hide();

    // Botón para enviar la imagen
    sendButton = createButton('Tomar Foto y Enviar');
    sendButton.position(10, height - 40);
    sendButton.mousePressed(sendImage);
}

function draw() {
    background(220);
    textSize(20);
    textAlign(CENTER);
    fill(0);
    text('Captura una imagen y envíala', width / 2, 30);
    image(capture, 100, 50, 200, 200);
}

function sendImage() {
    let imgCanvas = createGraphics(200, 200);
    imgCanvas.image(capture, 0, 0, 200, 200);
    let imgData = imgCanvas.canvas.toDataURL(); // Convierte la imagen a Base64

    socket.emit('image', imgData); // Enviar imagen al servidor
    console.log('Imagen enviada');
}
```

![Captura de pantalla 2025-03-10 211601](https://github.com/user-attachments/assets/48b83fe3-5cd9-4811-b61b-9bd580308943)

_____________________________________________________________________________________________________________________________________________________________________________

- ***¿Cómo se comunican los clientes con el servidor?***
```
socket.emit('image', imgData);
```
- ***¿Cómo se comunican los clientes entre sí?***

- La primera conexión se realiza con el cliente desktop que toma la foto y la transmite al servidor, el servidor la transmite en base64 al cliente mobile, el cliente mobile la transmite en su imagen.

- ***¿Qué tipo de mensajes se envían?***
  
- Cuando un cliente se conecta y se desconecta, tambien revisa que imagen se esta mandando para trasnmitirla.

- ***¿Qué tipo de datos se envían?***
```
data:image/png;base64,iVBORw0KGgoAAAANSUhEUg...
```
- ***¿Qué tipo de eventos se generan?***
- 'image' → Cuando el cliente desktop envía una imagen al servidor, y el servidor la reenvía al cliente mobile.

- ¿Cómo es el flujo de datos entre los clientes y el servidor?
- El cliente desktop se conecta al servidor, 
El cliente mobile se conecta al servidor, 
El usuario en el desktop captura una imagen, 
El cliente desktop convierte la imagen a Base64 y la envía al servidor, 
El servidor recibe la imagen y la retransmite a todos los clientes conectados (incluyendo mobile), 
El cliente mobile recibe la imagen y la muestra en pantalla.




































