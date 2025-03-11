### Actividad 2

## Caso de estudio: la biblioteca p5LiveMedia

***¿Qué es p5LiveMedia?***
- p5LiveMedia es una biblioteca para p5.js que permite la comunicación en tiempo real entre múltiples clientes a través de WebRTC y WebSockets. Facilita el intercambio de video, audio, datos y el canvas, lo que la hace útil para aplicaciones interactivas y colaborativas.

***¿Qué posibilidades ofrece p5LiveMedia?***
- Compartir video y audio en tiempo real desde la cámara/micrófono de los usuarios.
- Enviar datos personalizados (como posiciones del mouse, coordenadas, mensajes de chat, etc.).
- Transmitir el canvas de p5.js para colaboraciones en arte generativo.
- Crear experiencias interactivas multiusuario en navegadores sin necesidad de configurar servidores complejos.

***Replica varios ejemplos de p5LiveMedia que permitan entender sus posibilidades. Trata de seleccionar ejemplos para entender cómo se comparte audio, video, datos y el canvas.***
- Compartir Video y Audio en Tiempo Real
```js
let myVideo = null;
let otherVideo = null;

function setup() {
  createCanvas(400, 400);

  let constraints = { audio: true, video: true };
  myVideo = createCapture(constraints, function(stream) {
    let p5lm = new p5LiveMedia(this, "CAPTURE", stream, "nombre_unico_de_sala");
    p5lm.on('stream', gotStream);
  });

  myVideo.elt.muted = true; // Evitar retroalimentación de audio
}

function draw() {
  background(220);
  if (myVideo) {
    image(myVideo, 0, 0, width / 2, height);
    text("Mi Video", 10, 20);
  }
  if (otherVideo) {
    image(otherVideo, width / 2, 0, width / 2, height);
    text("Video Remoto", width / 2 + 10, 20);
  }
}

function gotStream(stream, id) {
  otherVideo = stream;
}
```

- Compartir el Canvas de p5.js
```js
let otherCanvas;

function setup() {
  let myCanvas = createCanvas(400, 400);
  let p5lm = new p5LiveMedia(this, "CANVAS", myCanvas, "nombre_unico_de_sala");
  p5lm.on('stream', gotStream);
}

function draw() {
  background(220);
  fill(255, 0, 0);
  ellipse(mouseX, mouseY, 100, 100);
}

function gotStream(stream, id) {
  otherCanvas = stream;
}
```

- Compartir Datos Personalizados
```js
let otherX = 0;
let otherY = 0;
let p5lm;

function setup() {
  createCanvas(400, 400);
  p5lm = new p5LiveMedia(this, "DATA", null, "nombre_unico_de_sala");
  p5lm.on('data', gotData);
}

function draw() {
  background(220);
  fill(255, 0, 0);
  ellipse(mouseX, mouseY, 50, 50);
  fill(0, 255, 0);
  ellipse(otherX, otherY, 50, 50);
}

function mouseMoved() {
  let dataToSend = { x: mouseX, y: mouseY };
  p5lm.send(JSON.stringify(dataToSend));
}

function gotData(data, id) {
  let receivedData = JSON.parse(data);
  otherX = receivedData.x;
  otherY = receivedData.y;
}
```

***Documenta en la bitácora tus hallazgos y las consideraciones que debes tener en cuenta para implementar p5LiveMedia en tu aplicación.***
- Al implementar p5LiveMedia en tu aplicación, considera que necesitas un servidor de señalización para establecer conexiones entre usuarios. Asegura la privacidad y el consentimiento al compartir video, audio o datos, ya que WebRTC transmite información en tiempo real. Maneja correctamente la conexión y desconexión de usuarios para evitar errores o pérdida de datos. Además, optimiza el rendimiento, especialmente en la transmisión de video o canvas, para que la experiencia sea fluida en distintos dispositivos y navegadores.


