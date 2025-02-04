## Actividad 4
### Exploración de código generativo

- ***Ejemplo #1***: Fortnite Cliker

- ***Descripción del Codigo***: El código implementa un clicker game donde el jugador gana "Vbucks" al presionar click izquierdo. Puede gastar esta moneda virtual en mejoras que aumentan la cantidad obtenida por clic y el multiplicador. Se generan elementos visuales como botones y textos usando Sprites, con colores llamativos como naranja, amarillo y verde. El fondo cambia dinámicamente y los objetos tienen formas rectangulares y circulares. No hay animaciones complejas, pero el juego responde a la interacción del usuario mediante clics y teclas.

- ***Modificación del Codigo***: En este código se hicieron dos modificaciones. La primera fue cambiar el clic izquierdo del mouse por la barra espaciadora, lo que permite presionar más rápido y acumular puntos con mayor facilidad. La segunda modificación fue ajustar el crecimiento del multiplicador: en lugar de aumentar gradualmente (1, 3, 5, 10, etc.), ahora se incrementa multiplicando por 10 en cada mejora. Por ejemplo, si el multiplicador es 10 y lo aumentamos a 100, cada vez que presionemos la barra espaciadora ganaremos 100 puntos en lugar de 10.

- ***Modificación de Barra Espaciadora***
```js
if(kb.presses('space')) {
        moneyCount += click * multi;
	    	score.text = ("Vbucks: " + moneyCount);
    }
```
- ***Modificación Multiplicador***
```js
 click = click + 1;
            multi = multi * 10;
            mul.text = ("Multiplier: " + multi);
```

- ***Reflexión***: En este ejemplo nos podemos dar cuenta que es muy interesante como interactua el programa con el jugador en tiempo real, Con las modificaciones realizadas hace que el juego sea mucho mas sencillo pero sin perder su interacción con el jugador. En el codigo vemos que lograron algo muy bonito utilizando diseños basicos como circulos, cuadrados y otras figuras y colores como el naranjado y el amarillo, este codigo no es tan dificil de entender pero si es muy bueno como funcional.


- ***Link***: https://openprocessing.org/sketch/2372232


________________________________________________________________________________________________________________________________________________________________________________

- ***Ejemplo #2***: AIM

- ***Descripción del Codigo***: Con este recurso descubrí cómo crear una simulación de dos ojos que siguen el cursor usando la biblioteca p5.js. Observé cómo utilizar las funciones atan2(), translate(), y rotate() para calcular y aplicar el ángulo entre los ojos y el cursor. También pude explorar el uso de push() y pop() para controlar el sistema de coordenadas y dibujar cada ojo de manera independiente.

- ***Modificaciones del Codigo***: En este ejemplo se realizaron otras dos modificaciones, una de ellas es que el fondo cambie de color dependiendo de donde se encuentre el mouse, para que la experiencia sea mas dinamica y en tiempo real, la segunda modificación que se realizo es que cuando el cursor este lejos de los ojos estos incremente su tamaño y si el cursor se acerca a estos mismos disminuira su tamaño.

- ***Modificación Fondo***
```js
background(map(mouseX, 0, width, 0, 255), 100, 100);
```
- ***Modificación Ojos***
```js
let d = dist(mouseX, mouseY, width / 2, height / 2);
let eyeSize = map(d, 0, width, 50, 60); 
let pupilSize = eyeSize / 2;
```

- ***Reflexión***: Las modificaciones hacen que la animación sea más interactiva. El fondo que cambia de color y el tamaño variable de los ojos y las pupilas según la cercanía del mouse hacen que la experiencia se sienta más viva, como si los ojos realmente reaccionaran al movimiento. Esto agrega un toque más dinámico y personal al código.

- ***Link***: https://p5js.org/examples/angles-and-motion-aim/





























