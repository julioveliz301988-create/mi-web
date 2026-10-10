# Selfie · Anuarios escolares (web)

Landing de ventas de Selfie Anuarios (Corporación Selfie Studio S.A.C.) para Lima y todo el Perú.

## Archivos
- `index.html`: la web completa (HTML + CSS + JS, sin dependencias).
- `libro-de-reclamaciones.html`: Libro de Reclamaciones virtual (envía por correo).
- `img/`: fotos reales de Selfie optimizadas en WebP y el logo.

## Secciones
Hero · Qué trae el anuario · Paquetes y precios (preventa) · Cómo reservar (5 pasos, formulario a WhatsApp, calculadora de fecha de clausura, cuentas de la empresa) · Galería · Cobertura Lima y provincias · Confianza · Preguntas frecuentes · Agente de WhatsApp flotante.

## Agente de WhatsApp
Botón flotante abajo a la derecha que abre un chat guiado (reservar, precios, provincia, asesor) y termina en la API click-to-chat de WhatsApp con el mensaje ya escrito.
El número se cambia en un solo lugar, al inicio del `<script>` de `index.html`:

```js
const SELFIE = { whatsapp: '51908865284', api: 'https://api.whatsapp.com/send', origen: 'web' };
```

## Antes de publicar
- Confirmar los precios para la Promo 2027 (hoy son los de la campaña 2026).
- Cambiar `https://www.selfieanuarios.pe/` (canonical, Open Graph y schema) por el dominio real.
- Confirmar el correo del Libro de Reclamaciones (`CORREO_RECLAMOS`).
- Confirmar que se tiene la autorización de los padres para publicar las fotos de los niños.

## Ver en local
```bash
python3 -m http.server 8000   # y abrir http://localhost:8000
```
