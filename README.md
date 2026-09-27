# Cuento.exe ✵

*Máquina de ideación narrativa para salir del bloqueo creativo.*

> “And here are you a writer, infinitely original and endowed with a sensibility that is charming though beyond the understanding of the vulgar.” — Tristan Tzara, 1920, *How to Make a Dadaist Poem*

Inspirada en los métodos dadaístas de creación por azar, pero con instrucciones técnicas en lugar de argumentos, para no alterar el estilo de quien escribe. Aleatoriza combinaciones de técnica narrativa (persona, narrador, tiempo verbal, técnica de discurso, forma textual, estructura temporal), género, tono, extensión, un personaje (naturaleza, género, edad, papel en la historia, tiempo de aparición y efecto en el lector) y una de las 36 situaciones dramáticas (interruptor activado por defecto) de Georges Polti (1895). Además muestra detonadores creativos: un artículo aleatorio de Wikipedia en español y una imagen aleatoria de Wikimedia Commons.

**Página:** https://viridianalizardo.github.io/ideas_escritura/

## Archivos

- `index.html`: la página (diseño y lógica).
- `ideas.json`: opciones, descripciones y reglas. **Para cambiar las opciones, edita solo este archivo.**
- `og.png`: imagen de vista previa al compartir el enlace.
- `LICENSE`: licencia MIT.
- `.nojekyll`: evita que GitHub Pages procese el sitio con Jekyll.

## Uso

- **Aleatorizar**: genera una idea nueva. Los campos con candado se conservan.
- **Fijar**: toca una etiqueta debajo de la idea para fijarla o soltarla. En *Campos* también se puede elegir un valor concreto o usar el candado.
- **Modo caos** (interruptor): ignora reglas y pesos; las combinaciones imposibles se marcan como reto. Apagado, se aplican las reglas de compatibilidad (p. ej., narrador omnisciente → tercera persona). **Incluir personaje** (interruptor) añade el párrafo del personaje.
- **Guardar**: conserva la idea y sus detonadores en *Ideas guardadas*, en este navegador (localStorage). **Descargar .txt** exporta la lista.
- **Compartir**: *Copiar enlace* genera una dirección que abre la misma idea con sus detonadores; en celulares se usa el menú nativo para compartir y en escritorio aparecen WhatsApp y correo; además, *Imprimir / PDF*. El enlace guarda cada campo como su posición en `ideas.json`: si reordenas o insertas opciones, los enlaces ya compartidos pueden abrir valores distintos (agregar opciones al final de una lista es seguro).

## Editar `ideas.json`

- `campos`: cada valor tiene `id` (único, sin espacios), `t` (etiqueta en la lista), `f` (frase que entra en la idea), `d` (descripción, opcional), `ej` (ejemplo, opcional) y `w` (peso, opcional; 1 por defecto). Las descripciones y ejemplos de narrador, tiempo verbal, técnica, forma y estructura aparecen en *Instrucciones detalladas*.
- `reglas`: `si` → `req` (valores permitidos) y/o `no` (valores excluidos), con un mensaje `msg`. Las reglas se refieren a los `id`. Con `"siempre": true` la regla se aplica también en modo caos (se usa para impedir que el tono erótico se combine con personajes menores de edad).
- `wikipedia_respaldo`: títulos que se usan si la API de Wikipedia no responde.

Es JSON estricto: comillas dobles, sin coma después del último elemento y sin comentarios. Si el archivo tiene un error, la página muestra un aviso. Puedes validarlo en https://jsonlint.com antes de subirlo.

## Contador de visitas (opcional)

La página admite [GoatCounter](https://www.goatcounter.com), un contador gratuito y sin cookies. Crea una cuenta, elige un código (p. ej. `maquina-ideacion`) y escríbelo en `index.html`, en la línea `const GOATCOUNTER = "";`. Las estadísticas se ven en `https://TU-CODIGO.goatcounter.com`. Para que el total de visitas aparezca en la página, activa en GoatCounter *Settings → Allow adding visitor counts on your website*.

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
