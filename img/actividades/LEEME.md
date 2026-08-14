# Fotos de las actividades

Se muestran en un círculo de 72 px con aro naranja, igual que en el sitio del
Programa. Poné cada foto con **exactamente** este nombre. Sirve `.jpg` o `.png`.

| Archivo | Actividad |
|---|---|
| `territorio-en-dialogo.jpg` | I Encuentro «Territorio en Diálogo» (UNQ) |
| `dia-del-investigador.jpg` | Clase pública en Plaza de Mayo |
| `senado-propiedad-privada.jpg` | Senado · proyecto de inviolabilidad de la propiedad privada |
| `senado-ciencia-y-tecnica.jpg` | Senado · comisión de Ciencia y Técnica |
| `juncal-uruguay.jpg` | Charla del Dr. Agustín Juncal |
| `cladhe-montevideo.jpg` | VIII Congreso Latinoamericano de Historia Económica |
| `mellano-soberania.jpg` | Charla de la Dra. Julieta Mellano · soberanía alimentaria |
| `seminario-interno.jpg` | Seminario interno del Programa |
| `secreto-mundo-rural.jpg` | Conversatorio con la Dra. María Verónica Secreto |
| `mellano-reforma-agraria.jpg` | Conversatorio con la Dra. Julieta Mellano |
| `alhr-mesa-tierra.jpg` | Mesa «Tierra y territorios en crisis» (Costa Rica) |
| `volkind-derechos-propiedad.jpg` | Ponencia de Pablo Volkind (Costa Rica) |

## Cómo tienen que ser

- **Cuadradas**: se recortan a un círculo, así que lo que quede fuera del cuadrado
  se pierde. Con 300×300 px alcanza.
- Menos de 150 KB cada una.

Si falta alguna, esa tarjeta muestra un ícono según el tipo de actividad
(charla, congreso, conversatorio…). No se rompe nada.

## Sumar una actividad

Agregá un objeto al JSON `#act-datos` de `index.html`:

```json
{
  "cat": "Charla",
  "fecha": "12 de septiembre de 2026",
  "titulo": "Título de la actividad",
  "detalle": "Una o dos oraciones con el detalle, quién la dio y dónde.",
  "foto": "img/actividades/archivo.jpg",
  "icono": "fa-chalkboard-user"
}
```

`fecha`, `foto` e `icono` son opcionales.
