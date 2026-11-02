# Apps súper locas

Las apps de la serie **«Día N creando apps súper locas sin saber programar»**, de [@crece_de_cero](https://www.instagram.com/crece_de_cero/). Las armé con Claude Code sin saber programar, y funcionan **dentro de tu Claude Code, con tu cuenta de Claude**.

| Día | Comando | Qué hace |
|---|---|---|
| 1 | `/velorio` | Le pasas el link de tu reel que no vio nadie y le hace la autopsia: mira el video y los números, y te dice en qué segundo murió, de qué y cómo hacer que el próximo no muera. |
| 2 | `/tarot` | Le pasas una captura de tu perfil y te tira tres cartas: lo que hiciste, lo que te frena y lo que tienes que hacer esta semana, cada una sacada de algo real de tu perfil. |
| 3 | `/juez` | Juzga tu idea de negocio: te hace cinco preguntas, sale a investigar a tu competencia y lo que cobra, y dicta sentencia con pruebas. |

Cada una te deja un informe completo y una imagen para tus historias.

## Qué necesitas

- **Claude Code**, con una cuenta de Claude (Pro o Max) o una clave de API. Si no lo tienes, está en [claude.com/claude-code](https://claude.com/claude-code).
- Para el velorio, **yt-dlp** (baja el video del link) y **ffmpeg** (lo mira por dentro). Si no los tienes, la app te ofrece instalarlos.

## Cómo instalarlas

1. Descarga este repositorio: botón verde **Code** → **Download ZIP**, y descomprímelo. Si usas git, `git clone` con el link de esta página.
2. Abre la carpeta en Claude Code:
   - en la app de escritorio, elige la carpeta `apps-super-locas`;
   - en la terminal, entra a la carpeta y escribe `claude`.
3. Escribe el comando de la app: `/velorio`, `/tarot` o `/juez`. También puedes pedirlo con tus palabras, por ejemplo «quiero saber por qué murió mi reel».

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

## Cuánto gasta

Usan tu cuenta de Claude. El juez hace entre 6 y 15 búsquedas en internet por juicio, el velorio mira hasta 30 cuadros del video y el tarot lee una o dos capturas.

## Privacidad

Todo lo que generan queda en tu compu, en las carpetas de cada app. Las búsquedas las hace Claude desde tu cuenta.

---

Hechas con Claude Code por alguien que no sabe programar · [@crece_de_cero](https://www.instagram.com/crece_de_cero/)
