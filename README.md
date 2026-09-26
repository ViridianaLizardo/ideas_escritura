# Máquina de ideación

**Generador de ideas de escritura creativa.** 

Aleatoriza combinaciones de técnica narrativa, género, tono y extensión, y sugiere un personaje. Aparte, muestra detonadores de ideas: un artículo aleatorio de Wikipedia , una imagen aleatoria y un libro en español de disponible para descargar en Project Gutenberg (vía [Gutendex](https://gutendex.com)).

## Archivos

- `index.html`: la página (diseño y lógica).
- `consignas.json`: opciones, descripciones y reglas. **Para cambiar las consignas, edita solo este archivo.**
- `.nojekyll`: evita que GitHub Pages procese el sitio con Jekyll.

## Uso

- **Sortear**: genera una consigna nueva. Los campos con candado se conservan.
- **Candado**: fija un campo. Elegir un valor en la lista también lo fija.
- **Modo coherente**: aplica las reglas de compatibilidad (p. ej., narrador omnisciente → tercera persona).
- **Guardar**: conserva la consigna y sus detonadores en una lista en este navegador (localStorage). **Descargar .txt** exporta la lista.
- **Modo caos**: ignora reglas y pesos; las combinaciones imposibles se marcan como reto.

## Editar `consignas.json`

- `campos`: cada valor tiene `id` (único, sin espacios), `t` (etiqueta en la lista), `f` (frase que entra en la consigna), `d` (descripción, opcional) y `w` (peso en el sorteo, opcional; 1 por defecto).
- `reglas`: `si` → `req` (valores permitidos) y/o `no` (valores excluidos), con un mensaje `msg`. Las reglas se refieren a los `id`.
- `wikipedia_respaldo`: títulos que se usan si la API de Wikipedia no responde.
- `gutenberg_respaldo`: libros que se usan si Gutendex no responde (enlazan a una búsqueda en gutenberg.org).

Es JSON estricto: comillas dobles, sin coma después del último elemento y sin comentarios. Si el archivo tiene un error, la página muestra un aviso en lugar de la consigna. Puedes validarlo en https://jsonlint.com antes de subirlo.

## Probar en local

Abrir `index.html` con doble clic no funciona: el navegador bloquea la lectura de `consignas.json` desde el disco. Usa un servidor local en la carpeta del proyecto:

```
python -m http.server
```

y abre http://localhost:8000.

## Publicación

Sitio estático sin dependencias ni compilación. En GitHub: *Settings → Pages → Deploy from a branch → `main` / `(root)`*.
