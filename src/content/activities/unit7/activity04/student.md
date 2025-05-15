### Actividad 4

## Integrando Inputs y Outputs al flujo

**Cliente Mobile**

- ***Conectar Inputs al Proceso:*** *El input principal es un slider creado en setup() con createSlider(60, 180, 90), que permite al usuario ajustar el BPM manualmente.
Cada 100 milisegundos, el valor del slider se lee mediante bpm = bpmSlider.value(); y se actualiza la variable interna bpm. Este valor luego se emite al servidor con socket.emit
('bpm', bpm);. Esto establece un vínculo directo entre el input del usuario y el proceso lógico del programa, asegurando que cada cambio en la entrada se refleje inmediatamente
en la lógica de envío de datos.*
