# Selfie · Anuarios escolares (web)

Landing de ventas de Selfie Anuarios (Corporación Selfie Studio S.A.C.) para Lima y todo el Perú.

## Archivos
- `index.html`: la web completa (HTML + CSS + JS, sin dependencias).
- `CNAME`, `robots.txt`, `sitemap.xml`: listos para publicar en selfieanuarios.com.
- `img/`: fotos reales de Selfie optimizadas en WebP y el logo.

## Secciones
Hero · Qué trae el anuario · Paquetes y precios (preventa) · Cómo reservar (5 pasos, formulario a WhatsApp, calculadora de fecha de clausura, cuentas de la empresa) · Galería · Cobertura Lima y provincias · Confianza · Preguntas frecuentes · Agente de WhatsApp flotante.

## Agente de WhatsApp
Botón flotante abajo a la derecha que abre un chat guiado (reservar, precios, provincia, asesor) y termina en la API click-to-chat de WhatsApp con el mensaje ya escrito.
El número se cambia en un solo lugar, al inicio del `<script>` de `index.html`:

```js
const SELFIE = { whatsapp: '51908865284', api: 'https://api.whatsapp.com/send', origen: 'web' };
```

## Datos confirmados
- Dominio: selfieanuarios.com.
- Precios de la campaña 2026, vigentes también para la Promo 2027.
- Libro de Reclamaciones oficial: https://www.respondo.pe/libro/corporacion-selfie-studio-s-a-c
- Redes: Instagram, TikTok y Facebook `@selfieanuarios`.

## Publicar en selfieanuarios.com (GitHub Pages)
1. Settings → Pages → Deploy from branch → elegir la rama y `/ (root)`.
2. El archivo `CNAME` ya apunta a `selfieanuarios.com`.
3. En el proveedor del dominio: registros A a 185.199.108.153, 185.199.109.153, 185.199.110.153 y 185.199.111.153, y CNAME `www` → `julioveliz301988-create.github.io`.

## Ver en local
```bash
python3 -m http.server 8000   # y abrir http://localhost:8000
```

## App interna del equipo: Ruta del Anuario (`/equipo/`)
App para iPhone (15, 16, 17) en 3D con los personajes de Selfie Studio sobre fondo blanco. Explica área por área cómo se hace un anuario:
Ventas → Administración → Fotografía (exterior, toga y birrete) → Edición → Postventa → Impresión → Taller (3 personas) → Entrega (oficina o delivery por distancia).

- Cada personaje hace su acción en 5 segundos, con 1 o 2 herramientas. Se gira con el dedo (deslizar a los lados).
- "Comenzar" reproduce todas las áreas seguidas; "Ver detalles" abre las tareas, los tipos de fotos y la calculadora de delivery.
- Instalar en el iPhone: abrir `https://selfieanuarios.com/equipo/` en Safari → Compartir → "Agregar a pantalla de inicio". Se abre a pantalla completa como una app.
- En computadora se muestra dentro de un marco de iPhone.
- 3D hecho con Three.js (copiado en `equipo/vendor/`, licencia MIT), no necesita internet para el 3D.
- Clave por defecto: `selfie2026`. Para cambiarla, genera el hash y pégalo en `CONFIG.claveHash` de `equipo/index.html`:
  ```bash
  printf 'NUEVA_CLAVE' | sha256sum
  ```
- Duración de la acción y tarifas de delivery: `CONFIG.accion` y `CONFIG.delivery` (las tarifas actuales son de ejemplo).
- Importante: la clave es un filtro simple en el navegador. Como el sitio y el repositorio son públicos, quien conozca el código puede leerlo. Para privacidad real, publica `/equipo/` detrás de un login (por ejemplo Cloudflare Access) o mantén el repositorio privado.
