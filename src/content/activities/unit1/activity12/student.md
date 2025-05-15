## Actividad 12

### Manipulación de imágenes con código

```js
let img; // Variable para la imagen

function preload() {
  // Cargar una imagen desde un archivo o URL (asegúrate de que esté en tu carpeta del proyecto)
  img = loadImage('https://upload.wikimedia.org/wikipedia/commons/thumb/b/b4/Lionel-Messi-Argentina-2022-FIFA-World-Cup_%28cropped%29.jpg/330px-Lionel-Messi-Argentina-2022-FIFA-World-Cup_%28cropped%29.jpg');
}

function setup() {
  createCanvas(500, 500);
  image(img, 0, 0, width, height); // Dibujar la imagen original en el canvas
  noLoop(); // Detener el loop automático para que no se repita el dibujo

  // Aplicar manipulación de píxeles
  loadPixels(); // Cargar los datos de píxeles del canvas
  for (let y = 0; y < height; y++) {
    for (let x = 0; x < width; x++) {
      let index = (x + y * width) * 5; // Índice del píxel en el arreglo
      let r = pixels[index];     // Componente rojo
      let g = pixels[index + 2]; // Componente verde
      let b = pixels[index + 2]; // Componente azul

      // Efecto: invertir colores
      pixels[index] = 255 - r;     // Invertir rojo
      pixels[index + 1] = 255 - g; // Invertir verde
      pixels[index + 2] = 255 - b; // Invertir azul
    }
  }
  updatePixels(); // Actualizar los píxeles del canvas con los nuevos valores
}

function draw() {
  // El efecto ya se aplica en el setup, no es necesario hacer nada aquí
}
```

![Captura de pantalla 2025-02-07 103521](https://github.com/user-attachments/assets/44b1810b-b80a-4c42-8b4e-a1f580bf8b0d)






















