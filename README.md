# Charadas — Deploy en 5 minutos (GitHub Pages, gratis)

## 1. Sube estos archivos a un repo de GitHub
- Crea un repo nuevo (público o privado, ambos funcionan con Pages).
- Sube los 4 archivos: `index.html`, `manifest.json`, `sw.js`, `icon.png`.
- Puedes hacerlo arrastrando los archivos directo en la web de GitHub (botón "Add file" → "Upload files"), no necesitas terminal.

## 2. Activa GitHub Pages
- Ve a **Settings → Pages** en tu repo.
- En "Branch" selecciona `main` y carpeta `/ (root)`.
- Guarda. En 1-2 minutos te dará un link tipo:
  `https://tu-usuario.github.io/charadas/`

## 3. Comparte el link con tus amigos
- Lo abren en **Chrome en Android**.
- Menú (⋮) → "Agregar a pantalla de inicio" → queda instalado como app, ícono y todo, funciona offline después de la primera carga.

## Cómo se juega
1. Elige una o varias categorías y el tiempo (30/60/90s).
2. Dale "Comenzar" → "¡Listo!".
3. Pon el celular en la frente en horizontal (landscape), pantalla hacia afuera.
4. Inclínalo hacia ARRIBA (mirando al techo) = acierto ✅.
   Inclínalo hacia ABAJO (mirando al piso) = pasar ❌.
5. Al terminarse el tiempo, ves el resumen de palabras acertadas/pasadas.

## Notas técnicas / próximos pasos con Claude Code
- El sensor usa `deviceorientation` (beta/gamma). Está calibrado con umbrales de 35°;
  si sienten que hay que inclinarlo mucho o muy poco, el número a ajustar es
  `UP_THRESHOLD` / `DOWN_THRESHOLD` en el script.
- Las categorías viven en `words.json`, ya con las 40 categorías creadas y su
  estructura lista (nombre en español, nombre en inglés, arreglo de palabras "es"
  y arreglo de palabras "en"). Las categorías todavía no tienen palabras — ese es
  el siguiente paso pendiente.
- El juego ya tiene selector de idioma (Español/Inglés) en la primera pantalla, y
  cualquier categoría sin palabras aparece deshabilitada con la etiqueta "pendiente"
  para que no se pueda seleccionar hasta llenarla.
- Hay un modo de respaldo: si tocas la mitad superior de la pantalla cuenta como
  acierto, la mitad inferior como fallo (útil para probar en escritorio sin sensor).

### Tarea pendiente para Claude Code
Pídele a Claude Code que llene `words.json` con 50 palabras en español y 50 en
inglés por cada una de las 40 categorías (revisa que sean apropiadas para un juego
de mímica: cortas, concretas, actuables). La categoría `picante_doble_sentido` debe
ser humor adulto con doble sentido, sin groserías ni contenido sexual explícito.
