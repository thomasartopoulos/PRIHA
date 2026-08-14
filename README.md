# PRIHA · Programa de Investigaciones sobre Historia Agraria

Sitio institucional del PRIHA (FCE–UBA). Sitio estático publicado con **GitHub Pages**
desde la rama `main`, carpeta raíz.

## Estructura

| Archivo | Qué es |
|---|---|
| `index.html` | Todo el sitio (una sola página, secciones ancladas) |
| `404.html` | Página de error servida por GitHub Pages |
| `logo_priha.jpg` | Logotipo |
| `og-priha.jpg` | Imagen de vista previa para redes (Open Graph / Twitter) |
| `departamentos.geojson` | Capa de departamentos del Observatorio de Tierras |
| `equipo/` | Fotos e info del equipo |
| `CNAME` | Dominio propio (lo genera GitHub al configurarlo en Settings → Pages) |
| `.nojekyll` | Desactiva Jekyll: publica los archivos tal cual |
| `.gitattributes` | Fuerza finales de línea LF (evita diffs de 2000 líneas desde Windows) |

## Publicar cambios

```bash
git add -A
git commit -m "descripcion del cambio"
git push
```

GitHub Pages republica en 1–2 minutos.

## Pendiente para producción

- Reemplazar el CDN de Tailwind (`cdn.tailwindcss.com`) por CSS compilado:
  `npm install -D tailwindcss && npx tailwindcss -i src/input.css -o dist/styles.css --minify`
