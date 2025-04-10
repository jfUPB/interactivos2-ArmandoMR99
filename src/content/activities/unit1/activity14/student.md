## Actividad 14

### Análisis crítico de los prototipos

- ***Prototipo***: Actividad 9

- ***Descripción***: Este código dibuja 100 formas (círculos, cuadrados y triángulos) de colores y tamaños aleatorios en el lienzo. Solo se dibujan una vez al inicio. Cuando haces clic, las formas se redibujan con nuevas posiciones y colores.

- ***Análisis***: Una buena implementacion de random(), ya que este se utiliza en la gran mayoria del programa como para colores, posiciones, tamaños y figuras que apareceran en el lienzo, el programa se podria mejorar haciendo que las figuras se dezplacen por el lienzo y si pensamos mas grande se podria disminuir las figuras geometricas y que estas colisionen entre si y se repelan.

- ***Aprendizaje***: Uso de estructuras condicionales para elegir figuras aleatorias. Creación de funciones auxiliares (drawTriangle()) para modularidad. La distribución podría optimizarse para evitar solapamientos excesivos.

___________________________________________________________________________________________________________________________________________________________________
  
- ***Prototipo***: Actividad 10

- ***Descripción***: El código crea una cuadrícula de rectángulos que cambian de tamaño y color en tonos de gris según el movimiento del mouse, haciendo que la animación sea interactiva y responda en tiempo real.

- ***Análisis***: El código crea una cuadrícula de rectángulos cuyo tamaño se adapta a la posición del mouse, modificando la densidad en tiempo real. Además, cada rectángulo cambia de tono de gris según su posición en la pantalla, generando un degradado visual dinámico. Esto produce un efecto interactivo donde la estructura y el color de la cuadrícula responden al movimiento del usuario.

- ***Aprendizaje***: Con este código aprendí a generar cuadrículas dinámicas en p5.js, donde el tamaño de las celdas cambia según la posición del mouse. También entendí cómo mapear valores para crear un degradado en escala de grises y cómo usar bucles anidados para recorrer el lienzo de manera eficiente. Me permitió experimentar con la interactividad y la relación entre posición, color y estructura visual.

______________________________________________________________________________________________________________________________________________________________________

- ***Prototipo***: Actividad 11

- ***Descripción***: Crea texto con palabras ya definidas y las pone en un lienzo color gris y letras negras, si se desea poner mas palabras eso no es un impedimento ya que desde el codigo se puede mofificar.

- ***Análisis***: Agregar interacción para generar nuevos poemas con un clic. Usar diferentes tamaños o estilos de fuente para mayor dinamismo. Implementar animaciones sutiles en la aparición del texto, Generación aleatoria de versos con variedad visual. Distribución ordenada del texto en el lienzo. Uso de noLoop() para evitar redibujados innecesarios.

- ***Aprendizaje***: Aprendí a usar random(words) para crear combinaciones creativas, aunque mejorar la distribución del texto con espaciado dinámico sigue siendo un desafío. Además, la estructura del poema es fija, por lo que podría hacerse más flexible para generar variaciones más dinámicas.

______________________________________________________________________________________________________________________________________________________________________

- ***Prototipo***: Actividad 12

- ***Descripción***: Carga una imagen en un lienzo de p5.js y manipula sus píxeles para aplicar un efecto de inversión de colores. Para ello, recorre cada píxel de la imagen y modifica sus valores de rojo, verde y azul, invirtiéndolos para crear un efecto visual llamativo y transformado.

- ***Análisis***: Aprendí a cargar y mostrar imágenes en p5.js, manipulando sus píxeles para generar efectos visuales. Para optimizar el rendimiento, usé noLoop() y evité actualizaciones innecesarias. Aún se puede mejorar el cálculo del índice de píxeles con la fórmula correcta (x + y * width) * 4, además de añadir más filtros y opciones interactivas para cambiar los efectos en tiempo real.

- ***Aprendizaje***: Aprendí a utilizar loadPixels() y updatePixels() para manipular los píxeles de una imagen en p5.js, aunque tuve dificultades con el cálculo del índice de píxeles, lo que afectó la manipulación visual. También observé que la imagen no carga correctamente si la URL no es accesible, y eso puede generar errores. Además, al trabajar con imágenes grandes, noté que puede haber problemas de rendimiento que también necesitan ser optimizados.

_________________________________________________________________________________________________________________________________________________________________________

- ***Prototipado***: Actividad 13

- ***Descripción***: Este código en p5.js genera sonidos con diferentes tipos de ondas (senoidal, triangular, cuadrada) y permite al usuario ajustar la frecuencia y amplitud usando sliders. También tiene botones para cambiar el tipo de onda. El lienzo tiene un tamaño de 500x500 píxeles y la interacción afecta el sonido en tiempo real.

- ***Análisis***: El código funciona bien, pero la interfaz podría ser más ordenada. Sería útil agregar una visualización de la onda y mejorar la disposición de los controles. También podría incluirse un botón para apagar el sonido o ajustar la velocidad de cambio de parámetros.

- ***Aprendizaje***: Aprendí a trabajar con osciladores en p5.js y a usar sliders para controlar frecuencia y amplitud. Experimenté con diferentes tipos de ondas y cómo se pueden manipular, además de crear interfaces simples para interactuar con el sonido en tiempo real.

























