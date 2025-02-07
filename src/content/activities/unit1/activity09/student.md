## Actividad 9

### Generación de formas geométricas aleatorias

- Este código dibuja 100 formas (círculos, cuadrados y triángulos) de colores y tamaños aleatorios en el lienzo. Solo se dibujan una vez al inicio. Cuando haces clic, las formas se redibujan con nuevas posiciones y colores.

```js
function setup() {
  createCanvas(600, 400);
  noLoop(); // Solo dibuja una vez al inicio
}

function draw() {
  background(0);
  
  for (let i = 0; i < 100; i++) { // Dibuja 100 formas aleatorias
    let x = random(width);
    let y = random(height);
    let size = random(20, 80);
    let shapeType = int(random(3)); // 0: círculo, 1: cuadrado, 2: triángulo
    
    fill(random(255), random(255), random(255));
    noStroke();
    
    if (shapeType === 0) {
      ellipse(x, y, size, size);
    } else if (shapeType === 1) {
      rect(x, y, size, size);
    } else {
      triangle(x, y, x + size, y, x + size / 2, y - size);
    }
  }
}

function mousePressed() {
  redraw(); // Redibuja nuevas figuras al hacer clic
}


```

![Captura de pantalla 2025-02-07 082855](https://github.com/user-attachments/assets/3eccd062-0e3e-4772-ba67-efe2681ce280)


















