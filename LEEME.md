# Blog de Sameer Salama · «de otro universo» · en tres idiomas

El mismo blog en **inglés** (la versión principal), **español** y **árabe**, con el mismo diseño.

```
index.html      Inglés: la página principal
es/index.html   Español
ar/index.html   Árabe, de derecha a izquierda
sitemap.xml     Mapa del sitio con las tres versiones, para Google Search Console
fotos/          Tu foto, las capturas de tus plantillas y las imágenes de la bitácora (fm66, paleta12, fm11 y luces)
iconos/         Iconos en SVG: marcas (simple-icons, CC0) y trazos (Lucide, licencia ISC)
fuentes/        Inter Tight, Space Grotesk, Instrument Serif, JetBrains Mono e IBM Plex Sans Arabic (licencia OFL)
```

Las tres páginas usan las mismas carpetas `fotos/`, `iconos/` y `fuentes/`: no las dupliques.

## Cómo abrirla

Haz doble clic en `index.html`. Funciona sin servidor. El selector **EN · ES · ع** de la cabecera lleva de un idioma a otro.

## Publicarla en GitHub Pages

1. En GitHub, crea un repositorio que se llame **`blog`** y sube **el contenido de esta carpeta** (no la carpeta entera):
   `index.html`, `es/`, `ar/`, `fotos/`, `iconos/`, `fuentes/` y `sitemap.xml`.
2. En el repositorio: **Settings → Pages → Build and deployment**: elige **Deploy from a branch**, la rama `main` y la carpeta `/ (root)`. Guarda.
3. En un par de minutos estará en `https://sika04126301188.github.io/blog/` (y `…/blog/es/`, `…/blog/ar/`).
4. Para que Google la encuentre antes: en [Google Search Console](https://search.google.com/search-console) añade la dirección, verifícala y envía `sitemap.xml`.

**Si usas otro nombre de repositorio o tu propio dominio**, cambia la dirección `https://sika04126301188.github.io/blog/`
por la nueva en los tres `index.html` (buscar y reemplazar) y en `sitemap.xml`. Aparece en las etiquetas `canonical`,
`hreflang`, `og:` y en los datos para Google del `<head>`.

## Cómo sabe Google qué idioma es cada página

- Cada página dice su idioma en `<html lang="…">` (y la árabe, `dir="rtl"`), y está escrita entera en ese idioma.
- Las tres se enlazan entre sí con `<link rel="alternate" hreflang="…">`: así Google enseña la versión en inglés,
  español o árabe según el idioma de quien busca. La inglesa es la de por defecto (`x-default`).
- Cada una tiene su propio título, descripción y datos de persona (schema.org) en su idioma.
- El `sitemap.xml` repite esos enlaces entre idiomas.

## Qué hay en la página

1. **Inicio**: tu foto en el centro de una galaxia de partículas. HTML5, CSS, JavaScript, Figma, Git y GitHub giran en órbita.
2. **Caja de herramientas**: una cinta de logos que no se acaba (en árabe corre hacia el otro lado).
3. **01 · Habilidades**: front-end con una ventana de código de tu CSS sin clases, tu asistente de IA, UX/UI con la paleta,
   Git con commits por semana, y datos, vídeo y automatización.
4. **02 · Trabajos**: carrusel 3D con 6 plantillas de All Pixels, filtro (todos, oscuros o claros), visor en grande y «Ver en vivo».
5. **03 · Laboratorio**: tu asistente digital (un chat de ejemplo que responde sobre tu trabajo) y la bitácora
   «Notas desde el taller»: cuatro notas en fila, la primera marcada como nueva. Cada nota se abre en un lector.
6. **04 · Cómo trabajo**: el cristal 3D y tus cuatro pasos (analizo, diseño, programo y publico).
7. **05 · Contacto**: tus datos, los días libres de la semana y el formulario que te llega al correo.
8. **Pie**: «Hablemos ya», el reloj con la hora de España, el índice y tus enlaces (All Pixels, GitHub y LinkedIn).

## La versión en árabe

- Toda la página va de derecha a izquierda: menú, columnas, flechas, carrusel y la línea de «Cómo trabajo».
- Usa IBM Plex Sans Arabic para las letras árabes; las palabras en latino (HTML, CSS, Figma…) siguen con tus fuentes.
- En árabe no hay espacio entre letras ni cursiva (rompería la unión de las letras), y las líneas tienen más aire.
- El código, las direcciones web, los colores y el correo se escriben de izquierda a derecha.
- Los textos están en árabe estándar (فصحى). Repásalos por si quieres cambiar el tono.

## Qué cambiar en cada idioma

Cada `index.html` lleva sus textos. Si cambias algo en uno, cámbialo también en los otros dos.

- **Textos de la página**: en el HTML de cada versión.
- **Lo que escribe el JS**: al principio del `<script>` de cada página, en el objeto `T`:
  - `notas`: el texto completo de las 4 notas de la bitácora, en el mismo orden que sus botones;
  - `respuestas`: lo que contesta tu asistente, con sus palabras clave. Gana la primera que aparece en la pregunta.
    Una clave con espacios («how much») se busca como frase entera;
  - `formulario`, `semana` y `reloj`: avisos del formulario, días libres y estado del reloj.
- **Formulario**: usa tu clave de Web3Forms (campo `access_key`). El asunto lleva `[EN]`, `[ES]` o `[AR]`
  para que sepas en qué idioma responder. Las opciones («Web completa», «Tienda online»…) te llegan siempre en español.
- **Días libres**: lunes, miércoles y viernes a partir de hoy. El fin de semana se muestra la semana siguiente.

## Si editas el HTML a mano

El JS monta cada parte por separado (menú, galaxia, carrusel, lector, chat, formulario, reloj…).
Si borras un elemento que una parte necesita, solo deja de funcionar esa parte y en la consola del navegador
sale un aviso con su nombre («No se ha podido montar…»). El resto de la página sigue funcionando.

Ojo con los párrafos del inicio: el CSS los llama por su posición (`p:first-of-type` es la etiqueta «Disponible»,
`p:nth-of-type(2)` los dos botones y `p:nth-of-type(3)` la línea de idiomas). Si añades o quitas uno, cambia esas reglas.
En la cabecera, la primera lista (`ul:first-of-type`) es el menú y la segunda (`ul:last-of-type`), el selector de idioma.

## Rendimiento

- La galaxia del inicio y el cristal de «Cómo trabajo» solo se dibujan mientras se ven en pantalla.
  La galaxia pinta sus puntos por tandas, y en el móvil va a 30 cuadros por segundo.
- Las animaciones que no paran se detienen cuando su bloque sale de la pantalla.
- Las fotos que no se ven al abrir la página se cargan cuando hacen falta (`loading="lazy"`).
- La fuente árabe solo se descarga en la versión árabe, y solo para las letras árabes.
- Con la opción «reducir movimiento» del sistema, la página se queda quieta.
