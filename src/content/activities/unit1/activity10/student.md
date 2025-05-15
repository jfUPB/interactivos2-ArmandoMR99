## Actividad 10

### Creación de un patrón generativo simple

- El código crea una cuadrícula de rectángulos que cambian de tamaño y color en tonos de gris según el movimiento del mouse, haciendo que la animación sea interactiva y responda en tiempo real.

```js
function setup() {
  createCanvas(800, 400);
  noStroke();
}

function draw() {
  var stepX = mouseX + 2; // tamaño dinámico en el eje X
  var stepY = mouseY + 2; // tamaño dinámico en el eje Y

  for (var gridY = 0; gridY < height; gridY += stepY) {
    for (var gridX = 0; gridX < width; gridX += stepX) {
      var grayValue = map(gridX + gridY, 0, width + height, 0, 255); // generamos tonos de gris
      fill(grayValue); // se llena con gris
      rect(gridX, gridY, stepX, stepY);
    }
  }
}
```

- ***Link***: http://www.generative-gestaltung.de/2/sketches/?01_P/P_1_1_1_01










