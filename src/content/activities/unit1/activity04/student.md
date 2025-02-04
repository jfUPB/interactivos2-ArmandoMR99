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
































