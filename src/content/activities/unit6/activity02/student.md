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

***Pseudocodigo***
```
si bpm_artista > 120:
    base_musical.tempo = "rápido"
  
si promedio_movimiento_publico < 5.0:
    visual.color = "azul"
    visual.forma = "líneas suaves"
else:
    visual.color = "rojo"
    visual.forma = "explosiones"
```

______________________________________________________________________________________________________

## Outputs

***1. Sonidos (Musica)***
- Cambio de velocidades de la musica
- Tono de la melodia (Grave/Aguda)

***2. Visual***
- Colores (Azul, Morado, Verde - Frio / Naranja, Rojo, Amarillo - Calidos)
- Formas (Lineas suaves / Explosión)

____________________________________________________________________________

***Conexión  Input -> Process -> Output***
- Los latidos del artista marcan el ritmo y el tono de la música en tiempo real, como si su corazón fuera el metrónomo del show. Mientras tanto, el movimiento de los celulares del público revela cuánta energía hay en el ambiente. Con esa info, los visuales se transforman: cambian los colores, las formas y cómo se mueven, todo al ritmo de la emoción colectiva. Es una conexión viva entre cuerpo y emoción, donde artista y público crean juntos una experiencia única que no se puede repetir.

***Outputs manifiestan el Storytelling.***
- La música nace del cuerpo, la imagen nace de la emoción colectiva. Todo converge en una obra efímera y emocional, donde artista y audiencia laten en sincronía.












































































