## Actividad 5

### Generación de patrones visuales

- ***Ejemplo #1***: P 2 1 1 04

- ***Descripción***: Este código crea un patrón de mosaico con formas que rotan según la posición del ratón. El usuario puede cambiar la forma mostrada, ajustar la rotación y la cantidad de mosaicos, y guardar la imagen. Todo esto se hace en tiempo real, creando una experiencia interactiva.

- ***Variaciones***: Se realizaron una variación simple se aumento la cantidad de mosaicos para que se viera mucho mas vistoso el arte generativo.

- ***Modificación***
```js
var tileCount = 20;
```

- ***Link***: https://x.com/ArmandoRua999/status/1886844493183254712

- ***Aplicación Potencial***: Una aplicación que se le podria realizar a este ejemplo podria ser museos virtuales donde las obras de arte puedan observar y mover los ojos dependiendo de donde se mueve el cursos y en niveles mas grandes lo que se puede realizar es que los ojos de las obras de arte detecten a el usuario con una camara y sigan su movimiento y asi dar el realismo de que los estan observando.


______________________________________________________________________________________________________________________________________________________________________________________

- ***Ejemplo #2***: P 2 0 01

- ***Descripción***: En este ejemplo podemos observar como al mover el mouse de derecha a izquierda el arte generativo aumenta su tamaño o disminuye, y si el mouse se mueve de arriba a abajo se iran agregando lineas verticales desde el origen donde si se aumenta mucho las lineas formalan un circulo que cubrira toda la pantalla.

- ***Variaciones***: Se realizarón dos variaciones una de ellas fue que se aumentaron el grosor de las lineas y la segunda variación fue que se cambio el centro de donde crecen las lineas, estas dos variaciones son simples pues no cambian mucho el diseño original.

- ***Modificación Posición***
```js
translate(width / 5, height /2 );
```
- ***Modificación Grosor***
```js
  strokeWeight(mouseY / 5);
```

![Captura de pantalla 2025-02-04 143048](https://github.com/user-attachments/assets/23e95233-5664-4f67-ae59-f7f294cac8dc)

- ***Aplicación Potencial***: Este ejemplo se podria aplicar a creacion de figuras virtuales, por ejemplo una imagen que sea geometrica con el cursor se puede modificar el tamaño y el grosor de esta misma y asi las personas pueden tener mas interación con las imagenes.


___________________________________________________________________________________________________________________________________________________________________________

- ***Ejemplo #3***: P 2 2 3 01

- ***Descripción***: En este ejemplo podemos observar una forma inicial de una esfera que a medida que movemos el cursor se va deformando y mientras se deforma va siguiendo el cursor con una claridad muy leve, pero si mpasamos el cursor por el mismo lado varias veces se ira resaltando mas y poniendo de un color mas oscuro, otro detalle que tiene el ejemplo es que al darle click al espacio se genera el circulo automaticamente.

- ***Variaciones***: Solo se realizo una variación simple la cual fue que el circulo al momento de perseguir al cursor lo hiciera de manera instantanea y no lo hiciera mucho mas lento como lo estaba haciendo sin la modificación.

- ***Modificación***
```js
function draw() {
  centerX += (mouseX - centerX) * 0.2;
  centerY += (mouseY - centerY) * 0.2;
```

![Captura de pantalla 2025-02-04 144912](https://github.com/user-attachments/assets/aca7d256-1024-499c-afe8-c29b0eff1fc2)

- ***Aplicación Potencial***: Una aplicación potencial podria ser que este modo se puede utilizar para dibujar porque al momoento de que sigue el cursor los diseñadores graficos le podrian sacar provecho a esto puesto que aumenta su intensidad si se pasa por el mismo lugra esto, ellos podrian sacar un potencial muy bueno a este ejemplo.








































