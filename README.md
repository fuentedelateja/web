# Web

Repositorio de la web de la asociación (https://fuentedelateja.org). Es un único
`index.html` sin dependencias, servido con GitHub Pages.

## Añadir una actividad nueva

1. Copia el cartel a `carteles/` con un nombre tipo `nombre-actividad-AAAA.jpg` y
   crea su miniatura (es la que se muestra en la web; el original se abre al pulsar):

   ```sh
   sips -s format jpeg -s formatOptions low --resampleWidth 600 carteles/NOMBRE.jpg --out carteles/mini/NOMBRE.jpg
   ```
2. En `index.html`, sección **Próxima actividad** (`id="proxima"`): cambia el cartel,
   el título, la fecha y los datos (lugar, plan, precio, inscripción).
   Actualiza también los textos de «Compártelo» (WhatsApp y correo), el enlace de Google Calendar
   y el fichero `.ics` de `eventos/` (fechas en hora UTC: en invierno, hora de
   España menos 1; en verano, menos 2).
3. Pasa la actividad anterior al principio de **Lo que hemos hecho**
   (`id="realizadas"`), copiando uno de los `<li class="actividad">` que ya hay.

## Actividades sin fecha cerrada

Van en el bloque **Más adelante** (`class="mas-adelante"`), dentro de la sección
de próxima actividad. Cuando se confirme la fecha, se convierten en la
**Próxima actividad**. Si no hay ninguna pendiente, se borra el bloque entero.
