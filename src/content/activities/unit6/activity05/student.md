### Actividad 5

## Blueprint 

**1. Resumen del Proyecto**
- Una pieza generativa que conecta al artista con su audiencia en tiempo real a través de datos biométricos y movimiento colectivo. El corazón del artista marca el ritmo musical,
mientras que la energía del público moldea visuales vivos. Todo converge en una experiencia efímera, emocional e irrepetible.

________________________________________________________

**2. Inputs detallados**
| Input | Fuente | Tipo de Dato | Rango | Simulación |
| ----- | ------ | ------------ | ----- | ---------- |
| BPM Artista | Smartwatch  | Numérico | 60-180 BPM | noise() + random(), picos suaves |
| Movimiento Publico | Acelerómetro/Giroscopio de celulares | Vector (float x/y/z) | -10 a +10 m/s² | noise() por eje |
| Intensidad emocional | Tablet o PC (aceleración promedio) | Numérico (entero) | 1 – 10 | Slider o noise() |

________________________________________________________

### 3.Proceso (Algoritmo)

***1. Procesamiento BPM***
- 60–80 → lento y grave
- 100–120 → ritmo medio
- 120–180 → rápido y agudo

***2. Movimiento del público***
- Se calcula el promedio de aceleración de los celulares. Si es bajo, se genera visual suave. Si es alto, visual explosivo.

***3. Intensidad Emocional***
- A partir del movimiento promedio, se asigna un nivel 1–10. Esto modula colores y energía visual.

***Pseudocodigo***





















































































