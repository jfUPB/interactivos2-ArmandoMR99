## Actividad 11

### Generación de texto aleatorio

```js
let words = ["Papayo", "Robar", "Messi", "Tiempo", "Alma", "Casa", "Izi", "Silencio", "Mundial", "Negra"]; // Conjunto de palabras

function setup() {
  createCanvas(500, 500);
  background(200); // Fondo Gris
  textAlign(CENTER, CENTER); // Centrar texto
  noLoop(); // Detener el loop automático

  generatePoem(); // Generar poema
}

function generatePoem() {
  fill(0); // Color del texto
  textSize(28); // Tamaño de texto

  for (let i = 0; i < 8; i++) { // Generar 8 líneas
    let line = "";
    for (let j = 0; j < 5; j++) { // Cada línea tiene 5 palabras
      line += random(words) + " "; // Elegir palabras aleatorias
    }
    text(line.trim(), width / 2, 100 + i * 50); // Dibujar línea
  }
}
```

![Captura de pantalla 2025-02-07 102041](https://github.com/user-attachments/assets/075f13fc-7463-4d59-ab7f-15f649d8b10b)























