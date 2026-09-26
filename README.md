# Máquina de Ideación ✵

Generador de ideas de escritura creativa. Aleatoriza combinaciones de técnica narrativa (persona, narrador, tiempo verbal, técnica de discurso, forma textual, estructura temporal), género, tono, extensión y un personaje (género, edad, papel en la historia, tiempo de aparición y efecto en el lector). Además muestra detonadores creativos: un artículo aleatorio de Wikipedia en español y una imagen aleatoria de Wikimedia Commons.

**Página:** https://viridianalizardo.github.io/ideas_escritura/

## Archivos

- `index.html`: la página (diseño y lógica).
- `ideas.json`: opciones, descripciones y reglas. **Para cambiar las opciones, edita solo este archivo.**
- `og.png`: imagen de vista previa al compartir el enlace.
- `LICENSE`: licencia MIT.
- `.nojekyll`: evita que GitHub Pages procese el sitio con Jekyll.

## Uso

- **Aleatorizar**: genera una idea nueva. Los campos con candado se conservan.
- **Candado**: fija un campo. Elegir un valor en la lista también lo fija.
- **Modo coherente**: aplica las reglas de compatibilidad (p. ej., narrador omnisciente → tercera persona). **Modo caos**: ignora reglas y pesos; las combinaciones imposibles se marcan como reto.
- **Guardar**: conserva la idea y sus detonadores en *Ideas guardadas*, en este navegador (localStorage). **Descargar .txt** exporta la lista.
- **Compartir**: *Copiar enlace* genera una dirección que abre la misma idea con sus detonadores; también hay menú nativo del dispositivo (si existe), WhatsApp, Telegram, correo, X, Bluesky e *Imprimir / PDF*.

## Editar `ideas.json`

- `campos`: cada valor tiene `id` (único, sin espacios), `t` (etiqueta en la lista), `f` (frase que entra en la idea), `d` (descripción, opcional) y `w` (peso, opcional; 1 por defecto).
- `reglas`: `si` → `req` (valores permitidos) y/o `no` (valores excluidos), con un mensaje `msg`. Las reglas se refieren a los `id`.
- `wikipedia_respaldo`: títulos que se usan si la API de Wikipedia no responde.

Es JSON estricto: comillas dobles, sin coma después del último elemento y sin comentarios. Si el archivo tiene un error, la página muestra un aviso. Puedes validarlo en https://jsonlint.com antes de subirlo.

## Contador de visitas (opcional)

La página admite [GoatCounter](https://www.goatcounter.com), un contador gratuito y sin cookies. Crea una cuenta, elige un código (p. ej. `maquina-ideacion`) y escríbelo en `index.html`, en la línea `const GOATCOUNTER = "";`. Las estadísticas se ven en `https://TU-CODIGO.goatcounter.com`.

## Probar en local

Abrir `index.html` con doble clic no funciona: el navegador bloquea la lectura de `ideas.json` desde el disco. Usa un servidor local en la carpeta del proyecto:

```
python -m http.server
```

y abre http://localhost:8000.

## Publicación

Sitio estático sin dependencias ni compilación. En GitHub: *Settings → Pages → Deploy from a branch → `main` / `(root)`*.

## Créditos

Creada por [Viridiana Lizardo](https://github.com/ViridianaLizardo). Desarrollada con la asistencia de Claude (Anthropic).

Sugerencias y errores: [Issues](https://github.com/ViridianaLizardo/ideas_escritura/issues). Licencia [MIT](LICENSE).
