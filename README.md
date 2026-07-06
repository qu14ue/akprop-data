# AKPROP — data (fuente única de propiedades)

Sirve `propiedades.js`, la lista compartida de propiedades destacadas que consumen
todas las landings en la sección "Otras propiedades que merecen ser vistas".

## Deploy (una sola vez)
1. Repo GitHub nuevo (ej. `qu14ue/akprop-data`) con el contenido de esta carpeta.
2. Cloudflare Pages → Connect to Git → framework **None**, build command vacío, output dir `/`.
3. Custom domain → `data.akprop.com.ar`.

## Cómo se usa desde cada landing
```html
<script src="https://data.akprop.com.ar/propiedades.js"></script>
```
Cada landing define su propio `SELF` (slug) y renderiza las otras 3.

## Mantenimiento
- Editar **solo** `propiedades.js`. El cambio impacta en las 4 landings al siguiente reload.
- `_headers` cachea 5 min (`max-age=300`), así que los cambios propagan rápido.
- `slug` es la clave de exclusión: cada landing esconde su propia ficha por `slug`.
