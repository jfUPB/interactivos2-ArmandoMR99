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

- **Fuente:** Tablet o PC
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
- Los artistas se tienen que ir acomodando al ritmo de la musica y su velocidad, sin embargo la musica se puede pausar para que los artistas no se pongan nerviosos y aumente su BPM.

***3. Movimiento del Publico***
- Con lo que comente en el input se calcula la aceleración y posición del celular para poder saber si el celular si se esta desplazando con intensidad o si casi no esta en movimiento.

***4. Visual Generativo***
- Estos visuales tambien se encargan de recibir rangos los cuales dependiendo de estos rangos se comvierten en el arte generativo
- - 1 - 5, Se transmiten colores mas frios y lineas mas suaves y rectas sin tanto movimiento.
- - 6 - 10, Son colores mas calidos y se pueden observar explosiones por diferentes partes de la pantalla.
  
***Datos Importantes***

Buscando encontre los BPM aproximados por temas musicales
- Cumbia: 90-110 lpm
- Reggaetón: 100-120 lpm
- Pop/rock/dance: 120-140 lpm
- Rock metálico/punk: 140-190 lpm
- Dub: 60-90 lpm
- Hip-hop: 60-100 lpm
- House: 115-130 lpm


















































































