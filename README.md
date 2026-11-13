# Capacitaciones 2024–2026

App web con las personas capacitadas por provincia y año (2024, 2025 y 2026).
Se puede instalar en el celular como un ícono en la pantalla de inicio.

## Archivos

- `index.html`: la app (resumen, totales por año, gráfico por provincia con filtro de año y tabla).
- `data.json`: los totales por provincia y año. Solo cantidades, sin datos personales.
- `manifest.webmanifest`, `sw.js`, `icons/`: lo necesario para instalarla en el celular y que abra sin conexión.

No necesita compilación: Vercel la publica como sitio estático.

## Actualizar los datos

Los scripts de consolidación están en la carpeta del proyecto en la PC, fuera de este repositorio.

1. Consolidar las planillas nuevas en `datos/capacitados_por_provincia_y_anio.csv`.
2. Correr `scripts/actualizar_web.ps1`, que regenera `data.json` con la fecha del día.
3. Subir el cambio a GitHub. Vercel publica la versión nueva en uno o dos minutos.

## Instalar en el celular

- **Android (Chrome):** abrir el link → menú ⋮ → **Agregar a la pantalla principal** (o **Instalar app**).
- **iPhone (Safari):** abrir el link → botón **Compartir** → **Agregar a inicio**.

## Cómo se cuenta

- Cada asistencia cuenta una vez: si una persona hizo tres cursos, suma tres.
- Se cuenta "SI" en Asistencia; donde no hay esa columna, "APROBADO" en Calificación, "SI" en Certificado o en Aprobó actividad final.
- En 2024, las asistencias sin provincia se asignan a Buenos Aires.
- Las entidades no cumplidoras de la RES 756-B (2026) cuentan cada una como una persona de su provincia.
