# DemocraticAI

Plataforma cívica de monitorización gubernamental para España.

Monitorizamos promesas electorales, leyes aprobadas e indicadores 
económicos. Datos del BOE e INE. Análisis de IA auditable. 
Sin agenda política.

## Estado actual
Prototipo de producto — frontend completo, backend en desarrollo.

## Tecnología
HTML · CSS · JavaScript · (próximamente: Python · FastAPI · PostgreSQL)

## Licencia
AGPL-3.0 — open source
```

Clic en "Commit changes". Tu repositorio ya tiene descripción y aparecerá bien en búsquedas.

---

## Bloque B — Netlify: conectar al repositorio y publicar

**Paso B1 — Crear cuenta en Netlify**
Ve a `netlify.com` → "Sign up" → elige "Sign up with GitHub" (esto es clave — los conecta directamente).

Autoriza a Netlify a acceder a tu cuenta de GitHub cuando te lo pida.

**Paso B2 — Crear el sitio desde GitHub**
En el panel de Netlify:
- Clic en "Add new site" → "Import an existing project"
- Elige "Deploy with GitHub"
- Busca y selecciona el repositorio `democraticai`
- En la pantalla de configuración deja todo como está — Netlify detecta automáticamente que son archivos HTML estáticos
- Clic en "Deploy site"

En 30 segundos Netlify te da una URL aleatoria tipo `amazing-paella-123456.netlify.app`. Ya está publicado en internet.

**Paso B3 — Cambiar el nombre del subdominio**
Esa URL aleatoria es fea. Para cambiarla:
- En el panel de tu sitio → "Site settings" → "Domain management"
- "Options" junto al nombre aleatorio → "Edit site name"
- Escribe `democraticai` → Guarda

Ahora la URL es `democraticai.netlify.app`. Funciona en cualquier navegador del mundo.

**Verificación:** Abre `democraticai.netlify.app` en modo incógnito. Deberías ver la landing page exactamente igual que en local.

---

## Bloque C — Dominio propio: democraticai.es

**Paso C1 — Comprar el dominio**
Ve a `dondominio.com` (el más barato y fiable en España):
- Busca `democraticai.es` — debería estar disponible
- Si no, prueba `democratic-ai.es` o `democraticai.es`
- Precio: ~8-12€/año
- Crea cuenta y completa la compra

**Paso C2 — Conectar el dominio a Netlify**
En el panel de Netlify → "Domain management" → "Add custom domain":
- Escribe `democraticai.es` → Verify
- Netlify te mostrará dos registros DNS que tienes que añadir en Dondominio

En Dondominio → "Mis dominios" → `democraticai.es` → "Gestión DNS" → "Añadir registro":

| Tipo | Nombre | Valor |
|---|---|---|
| `A` | `@` | `75.2.60.5` |
| `CNAME` | `www` | `democraticai.netlify.app` |

- Guarda los cambios
- Vuelve a Netlify → "Verify DNS configuration"

**Los cambios DNS tardan entre 10 minutos y 2 horas en propagarse** — es normal. Cuando Netlify muestre "✓ DNS verified" y "✓ HTTPS enabled", el dominio funciona.

**Desde ese momento, `democraticai.es` está en internet, con HTTPS, sin coste mensual.**

---

## Bloque D — El flujo de trabajo que usarás de ahora en adelante

Este es el ciclo que repetirás cada vez que hagas un cambio en el producto:
```
1. Editas un archivo HTML en tu ordenador
2. Vas a github.com/TU_USUARIO/democraticai
3. Haces clic en el archivo → lápiz de edición → editas → "Commit changes"
4. Netlify detecta el commit automáticamente
5. En 30 segundos, democraticai.es está actualizado
