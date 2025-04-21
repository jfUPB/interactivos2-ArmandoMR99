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

```
if (bpm > 120) {
  musica.tempo = "rápido";
  musica.tono = "agudo";
} else if (bpm < 80) {
  musica.tempo = "lento";
  musica.tono = "grave";
}

if (movimientoProm < 5) {
  visual.color = "frío";
  visual.forma = "líneas suaves";
} else {
  visual.color = "cálido";
  visual.forma = "explosiones";
}
```

________________________________________________________________________________

### 4. Outputs Detallados

**Música (output sonoro)**
- Tempo variable según BPM del artista
- Tono melódico (grave/agudo)
- Cambios en tiempo real

**Visuales (output visual)**
- Colores dinámicos (fríos ↔ cálidos)
- Formas: líneas suaves o explosiones
- Movimiento visual en pantalla basado en aceleración colectiva

**Conexión IPO y storytelling:**
- El artista guía con su ritmo cardíaco, la audiencia responde con energía física. Juntos moldean una obra visual-sonora en vivo. El cuerpo crea la música; la emoción del público pinta la imagen. Todo responde en tiempo real, generando una narrativa sensorial compartida.

_________________________________________________________________________________________________

### Notas Clave

- Si un input falla (por ejemplo, no hay señal del reloj), se activa un estado por defecto con valores promedio.
- La simulación es activable con usarSimulacion = true, útil para pruebas sin hardware.
- Las fluctuaciones suaves son clave para evitar resultados visuales o sonoros bruscos o incoherentes.















































































