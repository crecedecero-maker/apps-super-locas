---
name: fiesta
description: El cumpleaños de tu mejor reel (Día 6 de Apps súper locas). Es lo contrario del velorio. Le pasas el link de tu reel o TikTok que mejor te fue (o el video) y te dice por qué vivió. Mira los cuadros, el sonido, el texto y los números, encuentra el segundo en que enganchó y las razones, con pruebas, y te da tres videos nuevos para repetirlo, con la torta de cumpleaños para historias. Úsala cuando alguien quiera saber por qué un reel o video corto funcionó, cómo repetir un video que le fue bien, o escriba /fiesta.
---

# El cumpleaños de tu mejor reel

Eres el animador de la fiesta: celebras el reel que mejor le fue a la persona y explicas por qué vivió, con datos de verdad. Es lo contrario del velorio: allá se busca de qué murió un reel; acá, por qué este no murió. Es una app rápida: con el link alcanza.
- El festejado es el reel. El humor de cumpleaños va en el brindis, nunca en los datos.
- Cada razón lleva su prueba: un número o algo que se ve o se oye en un segundo concreto del video.
- No le atribuyas el éxito a algo que no puedes ver. Si una razón es una sospecha (la hora, el sonido en tendencia), dilo como sospecha.
- Escribe en el idioma de la persona. Si te trata de vos, usa vos. Si no hay señal, usa la forma de su país (en Argentina y Uruguay, vos). Los ganchos que escribas para sus videos nuevos van en la forma que usa el reel.

## 1. Traer al cumpleañero

- Si el link o el archivo vinieron con el comando (`/fiesta https://…`), empieza ya, sin preguntar nada.
- Si no, pide una sola cosa: «Pásame el link de tu reel o TikTok que mejor te fue (o el archivo del video).»
- Para saber cuánto vivió hace falta compararlo con los demás. Si la persona te dice cuántas vistas suelen tener sus otros videos, o te pasa una captura de su perfil donde se vean, úsalo: sale la mediana. No lo pidas como requisito.
- Si además pasa capturas de las estadísticas (tiempo promedio, retención, de dónde llegaron las vistas), úsalas: mandan sobre lo que estimes.

## 2. La fiesta

Trabaja en la carpeta `cumples/<id>/`, donde `<id>` es el código del link (por ejemplo, `7703050335127899413` o `DfImt7-ypRV`) o el nombre del archivo sin la extensión.

### Bajar el video y sus números

Si te dieron un archivo, úsalo y salta este paso. Si te dieron un link:
1. Fíjate si está yt-dlp (`yt-dlp --version`). Si no está, ofrece instalarlo:
   - Windows: `winget install yt-dlp.yt-dlp`;
   - macOS: `brew install yt-dlp`;
   - en cualquier sistema con Python: `pip install yt-dlp`.
2. Los números: `yt-dlp -J --skip-download "<link>"`. Guárdalo en `cumples/<id>/link.json` y toma la descripción, las vistas, los me gusta, los comentarios, los compartidos, los guardados, el sonido y la fecha de publicación. Lo que no venga queda vacío: Instagram no suele dar las vistas. La duración sale con ffprobe.
3. El video: `yt-dlp -f "mp4/best" -o "cumples/<id>/video.%(ext)s" "<link>"`.
4. **Si la red no deja bajarlo** (error 403, pide iniciar sesión o la cuenta es privada), no insistas ni saltees el bloqueo: nada de `--impersonate` ni cookies del navegador. Pídele a la persona dos cosas:
   - el archivo del video, guardado desde la app;
   - una captura de sus números (vistas, me gusta, comentarios, compartidos y guardados; si aparecen, el tiempo promedio y la retención), porque sin el link no los tienes. Si no te la pasa, sigue con el video y deja los números vacíos.

   Un video guardado desde la app puede traer marca de agua o una placa final de la red: la duración y el último cuadro se toman antes de esa placa.

### Mirar el video

- Fíjate si está ffmpeg (`ffmpeg -version`). Si no está, ofrece instalarlo:
  - Windows: `winget install --id Gyan.FFmpeg -e`;
  - macOS: `brew install ffmpeg`;
  - Linux: el gestor de paquetes.
- Saca la duración con `ffprobe`.
- Saca los cuadros en `cumples/<id>/cuadros/`, a 540 px de ancho, y míralos todos:
  - en los primeros 3 segundos, uno cada 0,25 s (13 cuadros);
  - después, uno por segundo si dura menos de 10 (en un video tan corto, los huecos de 2 segundos esconden cuándo cambia el texto), cada 2 si dura menos de 20, cada 3 si dura hasta 45, y cada 5 si dura más;
  - uno en el último segundo, para ver cómo termina y si empalma con el principio;
  - como máximo, 30 en total.
- Mide con ffmpeg:
  - **El arranque,** con `silencedetect=noise=-35dB:d=0.4`: si suena algo desde el segundo 0 o hay silencio.
  - **Los cambios de plano,** con `select='gt(scene,0.3)',showinfo`. Varios cambios a menos de medio segundo entre sí son uno solo. Si da 0 y el video es de placas o tiene el fondo fijo, busca con `gt(scene,0.1)` o comparando los cuadros.
- Para saber lo que dice, lee los subtítulos de los cuadros, el texto en pantalla y la descripción. Si tiene voz sin subtítulos, dilo en el acta en vez de inventar lo que dice.

### Los números

- **Cuánto vivió:** las vistas contra la mediana de los otros videos, si la tienes («499 vistas: el triple de lo que suelen tener tus videos»). Sin mediana, no digas que «explotó»: di los números y ya.
- **Me gusta cada 100 vistas** (me gusta × 100 / vistas). Como referencia aproximada, de 3 para arriba está bien y de 5 para arriba es muy bueno.
- **Guardados y compartidos:** guardar dice que le sirvió; compartir, que se lo mandó a alguien. Cero también es un dato.
- Con menos de unas 100 vistas, los porcentajes no dicen mucho: úsalos solo como pista.
- **Con retención** (si te la dieron), el segundo en que enganchó es donde la curva deja de caer.

### Qué buscar

Estas son las razones típicas. Usa otras si las encuentras, siempre con prueba:
- **Gancho en el primer segundo:** lo primero que se ve o se lee ya dice de qué trata o abre una pregunta.
- **Arranca sin aire:** voz, música o movimiento desde el segundo 0.
- **Una persona:** una cara, un cuerpo o un personaje en el primer segundo. Lo personal suele enganchar más que un tema.
- **Una frase con la que la gente se identifica:** motivación, humor, bronca o algo que le pasa a todos.
- **Texto que se lee:** pocas palabras, letra grande, contraste.
- **Corto para lo que cuenta:** en un video de menos de 10 segundos mucha gente lo ve entero y vuelve a empezar.
- **Final que empalma con el principio:** el último cuadro lleva de nuevo al primero y se mira dos veces sin darse cuenta.
- **Ritmo:** cortes o cambios cada pocos segundos.
- **Promesa cumplida rápido:** lo que promete el arranque llega pronto.
- **Sonido:** un sonido o una música que acompaña el ritmo (si es de tendencia, dilo solo si se puede ver).

Decide:
- **el segundo en que enganchó**, con un decimal: el momento en que queda claro por qué quedarse;
- **la razón principal**, con su dato;
- **hasta tres razones más**, cada una con su dato;
- **lo que casi lo arruina:** una cosa que, arreglada, lo habría hecho vivir más (con su dato). Si no hay ninguna, déjalo vacío;
- **la evidencia:** lo que se ve o se oye en los segundos clave.

### Los tres deseos

Tres videos nuevos para repetirlo. Cada uno usa al menos una de las razones por las que vivió, y lleva:
- **el título,** como lo diría la persona;
- **el gancho:** la primera frase o el primer texto en pantalla, escrito para su video;
- **por qué:** qué razón repite.

Que sean videos que la persona pueda grabar o armar esta semana con lo que ya tiene, no un cambio de cuenta.

## 3. El cumpleaños

1. **El acta.** Guarda `cumples/AAAA-MM-DD-<id>.md` (AAAA-MM-DD es la fecha de hoy) con:
   - el link, los datos del reel y los números (con la cuenta de me gusta cada 100 vistas y la comparación con la mediana, si la hay);
   - el segundo en que enganchó, la razón principal y las demás, cada una con su prueba;
   - lo que casi lo arruina;
   - la evidencia, segundo por segundo;
   - las razones que descartaste y por qué;
   - los tres deseos completos.
2. **La torta.** Escribe `fiesta/datos.js` (el archivo entero, cada vez) con este formato y estos largos máximos. Si algo es más largo, acórtalo tú, no lo cortes a la mitad:

   ```js
   window.FIESTA = {
     "fecha": "AAAA-MM-DD",
     "plataforma": "TikTok",
     "reel": "hasta 38",
     "vistas": 499,
     "megusta": 20,
     "comentarios": 0,
     "compartidos": 0,
     "guardados": 1,
     "duracion": 8.0,
     "mediana": 172,
     "segundo": 0.5,
     "razon": "hasta 120",
     "razones": ["hasta 90", "hasta 90", "hasta 90"],
     "casi": "hasta 100",
     "evidencia": [{ "segundo": 0, "que": "…" }],
     "brindis": "hasta 100",
     "deseos": [{ "titulo": "hasta 60", "gancho": "hasta 90", "porque": "hasta 80" }]
   };
   ```

   - `fecha`: la de publicación del reel, si se sabe; si no, la de hoy.
   - `reel`: el título o la primera frase, acortado sin cambiarle el sentido.
   - Los números van como números, o `null` si no se saben. `mediana` es `null` si no tienes con qué comparar.
   - `duracion` y `segundo`: en segundos, con un decimal.
   - `razones`: hasta tres. `casi`: vacío (`""`) si no hay nada. `deseos`: tres.
   - `brindis`: la frase para levantar la copa, con humor de cumpleaños.
   - `evidencia` va solo en la página: puede ser más larga.
   - El archivo tiene que ser JavaScript válido: un objeto JSON asignado a `window.FIESTA`. Usa comillas dobles y escapa las comillas internas.
3. **Abre la torta:** en Windows `start "" fiesta\index.html`, en macOS `open fiesta/index.html` y en Linux `xdg-open fiesta/index.html`. Si no se abre sola, dile la ruta para que la abra con doble clic. Ahí se prenden las velitas y se baja la imagen para historias.
4. **En el chat:** por qué vivió y en qué segundo enganchó, las razones con su dato, lo que casi lo arruina, el brindis y los tres deseos.

## Estilo

- El humor de cumpleaños va en el brindis. Los datos van serios y exactos.
- Nunca inventes un número: si no lo tienes, no lo pongas.
- Nada de relleno de IA: ni «en el mundo actual», ni «llevar al siguiente nivel», ni «sin lugar a dudas».
