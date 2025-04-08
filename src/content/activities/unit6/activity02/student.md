## Actividad 2

### Diseñando el flujo IPO de tu pieza generativa

## Inputs Detallados

***1. Laditos del Corazón***

- **Fuente:** Sensor biométrico (Smartwatch).
- **Tipo de Dato:** Numérico (frecuencia cardíaca).
- **Rango:** 60 – 180 BPM.
- **Simulable:** Si, se puede simular con p5.js, conectando el relog por bluetooth a p5.js
- **Storytelling:** Si está más calmado (la música es más lenta y grave). Si está más acelerado - (la música se vuelve más rápida y aguda).
Esto vuelve la experiencia más íntima, la audiencia escucha el cuerpo del artista.

______________________________________________________

***2. Movimiento de los celulares del público***

- **Fuente:** Acelerométro y Giroscopio (Web que contenga estas funciones)
- **Tipo de Dato:** Vector (x, y, z) de aceleración.
- **Rango:** Float -10 a +10 m/s² en x/y/z.
- **Simulable:** Si, se puede realizar si se hace un codigo que detecten estos valores. (Algo similar a el micro:bit del semestre pasado)
- **Storytelling:** La energía del público se convierte en una “pincelada colectiva” sobre el escenario. Los celulares funcionan como pinceles vivos que pintan con movimiento.

_______________________________________________________________________________

***3. Intensidad emocional del público***

- **Fuente:** Resultados del Input anterior
- **Tipo de Dato:*** Numerico (Posición y aceleración que detecta el celular)
- **Rango:** Rango de 1 - 10, para determinar que tanto se estan moviendo
- **Simulable:** Si, muestra los colores y las lineas dependiendo los valores de la posición y aceleración
- **Storytelling:** Esta intensidad se traduce en el “estado de ánimo” visual de la obra. Es una representación simbólica de la emoción colectiva.

____________________________________________________________________________________________________________________

## Procesamiento

***1. Input Latido Artista***
- Los BPM van por rangos, donde la musica cambia dependiendo estos rangos:
- - 60 - 80 BPM, Velocidad lenta y musica grave
- - 100 - 120 BPM, Musica normal
- - 120 - 180 BPM, Velocidad rapida y musica aguda

***2. Artista Improvisa***
- Los artistas se tienen que ir acomodando al ritmo de la musica y su velocidad, haciendo que esta experiencia sea unica para 


















































































