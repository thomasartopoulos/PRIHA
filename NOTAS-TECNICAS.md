# Notas técnicas

Sitio estático publicado con GitHub Pages desde `main`, carpeta raíz.

## Estructura

| Ruta | Qué es |
|---|---|
| `index.html` | Todo el sitio: una sola página con secciones ancladas |
| `404.html` | Página de error que sirve GitHub Pages |
| `img/` | Logotipos, vista previa y fotos: `equipo/`, `actividades/`, `novedades/` (ver `img/LEEME.md`) |
| `departamentos.geojson` | Capa de departamentos del Observatorio |

| `.nojekyll` | Publica los archivos tal cual, sin pasar por Jekyll |
| `.gitattributes` | Fuerza finales de línea LF: evita diffs de 2000 líneas desde Windows |
| `CNAME` | Dominio propio. Lo genera GitHub al configurarlo en Settings → Pages |

## Publicar cambios

```bash
git add -A
git commit -m "descripción del cambio"
git push
```

GitHub Pages republica en 1–2 minutos.

## Agregar una novedad

Se toca **un solo lugar**: el JSON `#nov-datos` dentro de `index.html`. Las tarjetas
del carrusel y las del explorador se dibujan solas a partir de ahí, en el orden en
que estén los objetos.

```json
{
  "cat": "Informe",
  "fecha": "05/08/2026",
  "titulo": "Séptimo informe · El NOA al rojo vivo",
  "resumen": "Una o dos líneas para la tarjeta.",
  "cuerpo": "<p>Párrafos del texto completo.</p><p>Otro párrafo.</p>",
  "img": "img/novedades/archivo.jpg",
  "icono": "fa-file-lines",
  "enlace": "https://...",
  "enlaceTexto": "Leer el informe completo"
}
```

| Campo | Obligatorio | Para qué |
|---|---|---|
| `cat` | sí | Categoría. Genera sola su chip en el explorador |
| `fecha` | sí | Texto libre: `05/08/2026` o `2026` |
| `titulo` | sí | |
| `resumen` | no | Texto de la tarjeta. Si falta, se recorta del `cuerpo` |
| `cuerpo` | sí | HTML del popup |
| `img` | no | Miniatura. Proporción 124:100, por ejemplo 744×600 px |
| `icono` | no | Ícono de Font Awesome cuando no hay imagen (por defecto `fa-image`) |
| `enlace` | no | Agrega el botón de descarga en el popup |
| `enlaceTexto` | no | Texto del botón (por defecto «Abrir el documento») |

## Agregar una actividad

Mismo criterio: un objeto en el JSON `#act-datos` de `index.html`.

```json
{
  "cat": "Charla",
  "fecha": "12 de septiembre de 2026",
  "titulo": "Título de la actividad",
  "detalle": "Quién la dio, dónde y con qué tema.",
  "foto": "img/actividades/archivo.jpg",
  "icono": "fa-chalkboard-user"
}
```

`fecha`, `foto` e `icono` son opcionales. Sin foto queda el ícono dentro del aro naranja.

## Fotos del equipo

Van en `img/equipo/` con el nombre exacto que figura en `img/equipo/LEEME.md`.
Si falta alguna, esa tarjeta muestra las iniciales.

## Pendiente

- Reemplazar el CDN de Tailwind por CSS compilado:
  `npm install -D tailwindcss && npx tailwindcss -i src/input.css -o dist/styles.css --minify`
- Faltan las fotos de `img/novedades/`, `img/equipo/` y `img/actividades/`.
- La cronología quedó como desplegable dentro del Observatorio (`<details id="cronologia">`).
