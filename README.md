## Desafio "Mi emprendimiento web"

![captura presentación][3]

|Bootcamp 2022 Modulo 3|Desarrollo de la interfaz de usuario|
|----|-----|
|**Unidad 5**|Trabajo práctico|
|**Día Bootcamp**|37|
|**Día Modulo**|15/15|



El desafío 'Mi emprendimiento web' es la prueba del módulo 3 y consiste en un frontend para un sitio web que utiliza CSS Grid y Flex en la implementación del layout además de transiciones, animaciones y elementos svg. Uno de los desafíos es implementar suficientes breakpoints para que sea *responsive*.

<hr>

## Referencias: *'cause we nerds... love them!! :)*

* [MDN sobre clamp()][0]
* [CSS Tricks sobre el uso de clamp() en font-size's dinámicos][1]
* [MDN sobre el objeto del DOM ClassList (relacionado con `toggle()`)][4]

### Requerimientos

|N°|Estado|Requisito|Puntaje|
|:-------:|:------:|:------:|:------:|
|1|OK|Usar Sass con patrón 7-1|3|
|2|--|Crear grilla usando CSS Grid para crear diseño *responsive* según las maquetas|2|
|3|--|Usar CSS Flexbox para posicionar y alinear elementos dentro de la maqueta|2|
|4|OK|Implementar transiciones y animaciones al elemento SVG indicado|2|
|5|--|Crear mediaqueries para visualizar correctamente la página en cualquier tamaño de dispositivo|1|

* **Tipografía** 
  * Ubuntu 400 700
  * Poppins 400 700
* **Colores:**
  * Esquema 1:
    * $white: #fff;
  * Esquema 2: 
    * $black: #000;
    * $sable: #060606;
    * $charcoal: #2e1503
  * Esquema 3:
    * $tangerine: #ffaf6d;
    * $orange: #ffa500;
* **Iconos:**
  * `<i class="fa-regular fa-thumbs-up"></i>`
  * `<i class="fa-regular fa-comments"></i>`
  * `<i class="fa-regular fa-eye"></i>`
  * `<i class="fa-solid fa-share-nodes"></i>`
  * `<i class="fa-brands fa-facebook-f"></i>`
  * `<i class="fa-brands fa-twitter"></i>`
  * `<i class="fa-brands fa-github"></i>`

<hr>

### IMPLEMENTACIÓN

* Se ha considerado que la vista se compone de 5 grandes bloques que se mueven naturalmente -*normal flow*- en una sola columna y luego es necesario organizar con CSS Grid para cumplir el requisito 2. Los grupos 1 y 3-5 se organizarán internamente con CSS Flex para dar cumplimiento al requerimiento 3. 
* ![Nota sobre el layout][2]
* Se ha comenzado por la vista *mobile* para dispositivos de 320px de ancho. 
* Se ha definido `width: 70%` y `max-width: 375px` al svg-animado para evitar que este 'inunde' la vista al cambiar a pantallas anchas, que tienen una disposición horizontal y no vertical como los dispositivos móviles.
* En el footer, cuando se está en *viewport* de 320px de ancho (probado en las *Dev Tools* con el modelo iPhone 5/SE), no se ha respetado la maqueta porque el espaciado vertical entre sus elementos hacía que la imagen svg animada quedara ligeramente oculta de la vista, lo que en mi opinión resta en la experiencia de usuario. Por eso se ha creado una regla dinámica con `clamp()` para que este espaciado crezca en relación al ancho de la vista hasta obtener con cierta fidelidad la proporción de la maqueta cuando se encuentra en vistas de tipo tablet, cerca de los 800px de `width` 

```css
 footer p span {
      padding-top: clamp(4px, 1.5vw, 16px)
    }
```

* Para el nombre del instructor de cada curso, el `font-size: $large` se escapaba del ancho. Se probaron 2 soluciones:
  1. Hacer una variable con un valor custom: `$more-than-medium: 18px;`
  2. Usar un truco "feo" con `letter-spacing: -0.5px` Solo por entretenido lo he dejado así. 

<hr>

## NOTAS

1. En el desafío anterior comencé a aprender y a acostumbrarme al *mindset* del uso de `calc()` para establecer valores de tamaño dinámico en algunos elementos. En este desafío estoy haciendo lo mismo con `clamp()`. Es mucho más entretenido por ejemplo, escribir: `width: clamp(10px, 1vw, 20px)` que escribir lo mismo como 3 reglas `min-width: 10px; width: 1vw; max-width: 20px;` y más legible que escribir `width: max()(10px, min()(1vw, 20px))` [Leer en MDN][0]. Ejemplo muy entrete aplicado al font-size en [CSS Tricks][1]

<hr>

[]:

[4]:https://developer.mozilla.org/en-US/docs/Web/API/Element/classList
[3]:./assets/utils/presentacion.png
[2]:./assets/utils/layoutNotes1.png
[1]:https://css-tricks.com/linearly-scale-font-size-with-css-clamp-based-on-the-viewport/
[0]:https://developer.mozilla.org/en-US/docs/Web/CSS/clamp


<!--TODO Implementar button:active & button:focus en XDA -->
<!--TODO -LISTO- Incluir textos de menús dentros de enlaces -->
<!--TODO  -->
<!--TODO  -->
<!--TODO  -->