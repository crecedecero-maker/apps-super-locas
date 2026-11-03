# Apps súper locas

Las apps de la serie **«Día N creando apps súper locas sin saber programar»**, de [@crece_de_cero](https://www.instagram.com/crece_de_cero/). Las armé con Claude Code sin saber programar, y funcionan **dentro de tu Claude Code, con tu cuenta de Claude**.

| Día | Comando | Qué hace |
|---|---|---|
| 1 | `/velorio` | Le pasas el link de tu reel que no vio nadie y le hace la autopsia: mira el video y los números, y te dice en qué segundo murió, de qué y cómo hacer que el próximo no muera. |
| 2 | `/tarot` | Le pasas una captura de tu perfil y te tira tres cartas: lo que hiciste, lo que te frena y lo que tienes que hacer esta semana, cada una sacada de algo real de tu perfil. |
| 3 | `/juez` | Juzga tu idea de negocio: te hace cinco preguntas, sale a investigar a tu competencia y lo que cobra, y dicta sentencia con pruebas. |
| 4 | `/chismoso` | Le pasas el link de un video que explotó, tuyo o de otro, y lee los comentarios por ti: qué piden, de qué se quejan y qué preguntan, con cinco videos para hacer mañana. |
| 5 | `/miss-portada` | Le pasas una captura de tu perfil y hace un concurso de belleza con tus portadas: elimina a las que no se leen en chiquito, le da la banda de Miss Simpatía a la de más vistas y corona a la mejor. |
| 6 | `/fiesta` | Lo contrario del velorio: le pasas el link de tu reel que mejor te fue y festeja su cumpleaños. Te dice en qué segundo enganchó y por qué vivió, y te da tres videos para repetirlo. |
| 7 | `/gemelo` | Le pasas una captura de tu perfil y crea a tu gemelo malvado: el creador de tu tema que te va a robar los seguidores porque hace todo lo que tú no haces. Te muestra su ficha de villano, su plan y cómo adelantarte. |

Cada una te deja un informe completo y una imagen para tus historias.

## Qué necesitas

- **Claude Code**, con una cuenta de Claude (Pro o Max) o una clave de API. Si no lo tienes, está en [claude.com/claude-code](https://claude.com/claude-code).
- Para el velorio y la fiesta, **yt-dlp** (baja el video del link) y **ffmpeg** (lo mira por dentro). Para el chismoso, solo **yt-dlp** (baja los comentarios). Para Miss Portada, **ffmpeg** (recorta tus portadas de la captura para subirlas al escenario; sin él, el concurso sale igual, sin las fotos). Si no los tienes, la app te ofrece instalarlos.

## Cómo instalarlas

1. Descarga este repositorio: botón verde **Code** → **Download ZIP**, y descomprímelo. Si usas git, `git clone` con el link de esta página.
2. Abre la carpeta en Claude Code:
   - en la app de escritorio, elige la carpeta `apps-super-locas`;
   - en la terminal, entra a la carpeta y escribe `claude`.
3. Escribe el comando de la app: `/velorio`, `/tarot`, `/juez`, `/chismoso`, `/miss-portada`, `/fiesta` o `/gemelo`. También puedes pedirlo con tus palabras, por ejemplo «quiero saber por qué murió mi reel».

La primera vez, Claude Code te pregunta si confías en la carpeta: dile que sí.

## Cómo funciona cada una

### Día 1 · Velorio de reels (`/velorio`)

1. Le pasas el link de tu reel o TikTok. Si la red no deja bajarlo, le pasas el video.
2. Baja el video y sus números, saca cuadros, y mide cuánto tarda en sonar algo y cuándo llega el primer corte.
3. Cruza lo que ve con los números (y con tus estadísticas, si se las pasas: cuánto lo miraron, cuántos lo saltearon, dónde cae la retención) y encuentra en qué segundo murió y de qué, con pruebas.
4. Te deja el acta en `velorios/`, la lápida para historias y tres cambios para que el próximo no muera.

### Día 2 · El tarot del algoritmo (`/tarot`)

1. Le pasas una captura de tu perfil de Instagram o TikTok: la parte de arriba, con la bio, los números y la grilla. Si quieres más precisión, suma una de la pestaña de reels, con las vistas.
2. Lee tu perfil: qué promete tu bio y a quién le habla, de qué temas es tu grilla, si se entiende cada portada, si apareces tú y qué post se destacó.
3. Te tira tres cartas de los 19 arcanos del algoritmo: lo que hiciste, lo que te frena y lo que tienes que hacer. Cada una trae la prueba que la llamó.
4. Te deja la profecía, tres pasos para esta semana, la lectura en `lecturas/` y la imagen de las cartas para historias.

### Día 3 · Juez de ideas tontas (`/juez`)

1. Le cuentas tu idea y te hace cinco preguntas de una vez: quién te pagaría, cuánto, quién lo hace ya, por qué te elegirían a ti y cuántos ya te dijeron que sí.
2. Sale a investigar en internet: tu competencia, lo que cobra, de qué se quejan sus clientes y si hay gente pidiendo lo que haces.
3. Dicta sentencia: cargos con pruebas, atenuantes y un fallo (absuelta, libertad condicional, culpable o cadena perpetua), más tres pasos para salir en libertad esta semana.
4. Te deja el expediente completo en `expedientes/` y la sentencia para historias.

### Día 4 · El chismoso de comentarios (`/chismoso`)

1. Le pasas el link de un reel, TikTok o video de YouTube que explotó, tuyo o de tu competencia. También le sirven capturas de los comentarios.
2. Baja los comentarios y los lee todos. YouTube los da completos; Instagram, sin iniciar sesión, solo los primeros 12 o 15 (si quieres que lea más, le pasas capturas).
3. Te cuenta el chisme con pruebas: lo que piden, de qué se quejan, lo que preguntan y lo que les encantó, cada cosa con un comentario real y cuántos dicen lo mismo. Nunca muestra quién comentó.
4. Te da cinco videos para hacer mañana, cada uno con el comentario que lo pidió, y te deja el acta en `chismes/` y la tapa de revista para historias.

### Día 5 · Miss Portada (`/miss-portada`)

1. Le pasas una captura de tu perfil donde se vean tus portadas: la mejor es la de la pestaña de reels, o la de tu perfil de TikTok, porque ahí se ven las vistas. Si arrastras el archivo a la ventana de Claude Code, tus portadas suben de verdad al escenario.
2. Las mira al tamaño de la grilla, que es como las ve la gente, y elimina a las que no se leen en chiquito: letra chica o fina, más de ocho palabras, poco contraste o texto tapado.
3. Le da la banda de Miss Simpatía a la de más vistas, aunque sea fea, y corona a la que mejor se entiende en un segundo y más frena el pulgar.
4. Te deja el acta en `concursos/`, la coronación animada con la imagen para historias, un arreglo para cada eliminada y la receta de tu próxima portada.

### Día 6 · El cumpleaños de tu mejor reel (`/fiesta`)

1. Le pasas el link del reel o TikTok que mejor te fue. Si le dices cuántas vistas suelen tener tus otros videos, te dice cuántas veces más vivió este.
2. Baja el video y sus números, saca cuadros, y mide cómo arranca, el sonido y los cortes, como el velorio.
3. Te dice en qué segundo enganchó y por qué vivió, con pruebas, y lo que casi lo arruina. Lo que es una sospecha (la hora, el sonido) lo dice como sospecha.
4. Te da tres deseos, tres videos para repetirlo con su primera frase escrita, y te deja el acta en `cumples/` y la torta para historias, con velitas que forman tus vistas.

### Día 7 · Tu gemelo malvado (`/gemelo`)

1. Le pasas una captura de tu perfil: la parte de arriba, con la bio, los números y la grilla. Una de la pestaña de reels, con las vistas, ayuda.
2. Busca lo que tu perfil no hace, cada cosa con su prueba en la captura: la bio, las portadas, si apareces, si hay una serie.
3. Crea a tu gemelo malvado, del mismo tema: su nombre, su lema, tres superpoderes (lo que él hace y tú no), su plan para robarte los seguidores y su única debilidad.
4. Te da tres pasos para adelantarte esta semana y te deja el expediente en `gemelos/` y la ficha de villano para historias.

## Cuánto gasta

Usan tu cuenta de Claude. El juez hace entre 6 y 15 búsquedas en internet por juicio, el velorio y la fiesta miran hasta 30 cuadros del video, el tarot lee una o dos capturas, el chismoso lee hasta 500 comentarios, Miss Portada mira una captura y sus recortes, y el gemelo lee una o dos capturas.

## Privacidad

Todo lo que generan queda en tu compu, en las carpetas de cada app. Las búsquedas las hace Claude desde tu cuenta.

---

Hechas con Claude Code por alguien que no sabe programar · [@crece_de_cero](https://www.instagram.com/crece_de_cero/)
