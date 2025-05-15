### Actividad 4

## Plan de simulación de datos

**1. Identifica inputs a simular**
- ***Frecuencia cardíaca del artista (BPM)*** 
- ***Movimiento de los celulares del público (Acelerómetro/Giroscopio – vector x, y, z)*** 
- ***Intensidad emocional del público (nivel 1 a 10)***

________________________________________________________

**2. Define método de simulación**

- ***BPM del Artista:*** Usaremos noise() para fluctuaciones suaves y random() para picos ocasionales. El rango será de 60 a 180 BPM. El comportamiento simulado debe tener cambios lentos con picos, como si el artista estuviera experimentando fluctuaciones emocionales.

- ***Movimiento del Publico:*** Se simula usando noise() para los ejes x, y, z con un rango de -10 a +10 m/s². El movimiento debe ser orgánico, suave, como si el público estuviera moviendo sus celulares con ritmo, sin brusquedad.

- ***Intensidad Emocional Publico:*** Se controlará con un slider manual o noise() para simulaciones automáticas. El rango será de 1 a 10, representando la energía del público, con cambios suaves y graduales.

________________________________________________________

**3. Activación/Desactivación de Simulación:**
- Usaremos una variable booleana usarSimulacion = true para activar o desactivar la simulación. Si está activada, el sistema utilizará datos simulados; si está desactivada, se conectarán los datos reales de los sensores.


  































































































