### Actividad 4

## Integrando Inputs y Outputs al flujo

**Cliente Mobile**

- ***Conectar Inputs al Proceso:*** *El input principal es un slider creado en setup() con createSlider(60, 180, 90), que permite al usuario ajustar el BPM manualmente.
Cada 100 milisegundos, el valor del slider se lee mediante bpm = bpmSlider.value(); y se actualiza la variable interna bpm. Este valor luego se emite al servidor con socket.emit
('bpm', bpm);. Esto establece un vínculo directo entre el input del usuario y el proceso lógico del programa, asegurando que cada cambio en la entrada se refleje inmediatamente
en la lógica de envío de datos.*

```js
setInterval(() => {
  bpm = bpmSlider.value();
  socket.emit('bpm', bpm);
}, 100);
```

- ***Generar Outputs desde el Proceso:*** *El output se genera en la función draw(), donde se muestran en pantalla el título "Simulación de BPM" y el valor actual del BPM usando text(bpmSlider.value() + " LPM", width / 2, 120);. Este valor es calculado internamente por el proceso (lectura del slider) y refleja en tiempo real el estado interno del programa. La visual es clara y efectiva, pero se puede enriquecer haciendo que, por ejemplo, el tamaño del texto o el color cambien en función del BPM, como en textSize(map(bpm, 60, 180, 16, 48));.*

- ***Implementar interacción básica:*** *La interacción básica está completamente integrada con el uso del slider como input. El usuario puede moverlo para modificar el BPM, lo que actualiza automáticamente el proceso y los outputs. Esta interacción es intuitiva y directa, y podría complementarse fácilmente con manejadores adicionales como keyPressed() para resetear el BPM (bpmSlider.value(90)) o mousePressed() para activar algún efecto visual, extendiendo el rango de control del usuario.*

- ***Prueba del flujo completo:*** *El flujo completo puede verificarse ejecutando el cliente. Al mover el slider (input), el valor de BPM se actualiza (proceso) y se refleja tanto en la pantalla como en los datos emitidos al servidor (output). El uso de console.log(bpm); permite comprobar que los datos están siendo capturados y enviados correctamente, asegurando que el flujo Input → Proceso → Output esté funcionando como se espera.*

__________________________________________________________________________________________________________________________________________

**Cliente Desktop**

- ***Conectar Inputs al Proceso:*** *En este cliente, el input no proviene del usuario directamente, sino de los datos enviados por red desde el cliente mobile. El programa se conecta al servidor con socket = io(); y escucha los valores BPM entrantes con socket.on('bpm', (data) => { bpm = data; updatePlaybackRate(); });. Cuando se recibe un nuevo BPM, se actualiza la variable interna bpm, que a su vez ajusta la lógica de reproducción de audio en updatePlaybackRate().*

```js
socket.on('bpm', (data) => {
  bpm = data;
  updatePlaybackRate();
});
```

- ***Generar Outputs desde el Proceso:*** *El output principal es sonoro (la reproducción de la canción) y visual (mostrar el BPM en pantalla). En la función updatePlaybackRate(), el BPM recibido se convierte en una velocidad de reproducción usando map(bpm, 40, 180, 0.5, 2.0, true). Esto controla dinámicamente cómo suena la canción (aunque la línea que lo aplica está comentada: //song.rate(rate);). Además, en draw() se visualiza el valor de BPM actual con text(BPM actuales: ${bpm}, width / 2, height / 2);. Esto asegura que tanto el audio como el texto respondan al estado interno influenciado por el input remoto.*

- ***Implementar interacción básica:*** *Este cliente no incluye inputs directos del usuario, pero implementa una interacción requerida por políticas del navegador para iniciar el audio. Se utiliza userStartAudio().then(...) para permitir que la música comience a reproducirse luego de una acción del usuario, como un toque o clic inicial. Si se quisiera ampliar, se podrían implementar controles como mousePressed() para pausar o reanudar la canción, o teclas para cambiar efectos.*

```js
userStartAudio().then(() => {
  if (!song.isPlaying()) {
    song.loop();
  }
});
```

- ***Prueba del flujo completo:*** *El flujo Input → Proceso → Output se verifica al conectar ambos clientes. El usuario interactúa con el slider en el cliente mobile (input), que envía el BPM al servidor. El cliente desktop recibe ese BPM (proceso) y lo utiliza para ajustar dinámicamente la reproducción del audio y actualizar la visualización del valor (output). Si se activa el console.log('BPM recibidos:', bpm);, se puede confirmar que la conexión de datos y el flujo lógico funcionan correctamente.*












