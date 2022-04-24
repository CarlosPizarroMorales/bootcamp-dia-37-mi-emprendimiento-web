## PEQUEÑO ESTUDIO SOBRE LAYOUT

La maqueta presenta un flujo bastante fácil de observar e implementar en HTML, en la siguiente imagen se observa: 

![0]

* Básicamente, son 5 grandes grupos que mantienen ese orden cuando se implementa la vista de 1 sola columna en vista móvil. Por ese motivo, la vista móvil será la elegida para comenzar el desarrollo.
* Los contenidos de cada grupo 2-4, son bastante grandes como para permitir la vista en 1 columna hasta un viewport de aproximadamente 992px width, momento en el que debería saltarse a la vista de escritorio que muestra la imagen de arriba, y entonces aplicar un esquema GRID para arreglar los elementos. 
* Una opción para realizar el layout es utilizar CSS Grid para organizar los grupos 2-4, pero eso implicaría el uso de un contenedor dedicado, y por otro lado, se puede hacer una sola grilla para todo el esquema. 



















[0]:./layoutNotes1.png