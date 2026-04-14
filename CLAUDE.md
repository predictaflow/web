# Predictaflow — Web

## Proposito
Landing page publica de Predictaflow en predictaflow.me.

## Modo por defecto: modo-productivo

## Contexto tecnico
- Stack: HTML/CSS puro, sin framework JS
- Hosting: Netlify — deploy desde este repo (site: predictaflow, URL: predictaflow.netlify.app)
- Dominio: predictaflow.me (Namecheap, GitHub Student Pack)
- DNS: A record → 75.2.60.5 (Netlify), CNAME www → predictaflow.netlify.app
- Fonts: Manrope (body) + DM Sans (headings) via Google Fonts
- Colores: primary `#4343FF`, accent `#FFD802`, highlight `#DAFFAA`
- Tema claro, estilo Platanomelon

## Archivos clave
| Archivo | Descripcion |
|---|---|
| `index.html` | Landing page completa |
| `css/style.css` | Estilos principales |
| `images/` | Logos, iconos, backgrounds, portfolio |

## Reglas
- Este repo es PUBLICO. No incluir datos internos, credenciales, ni documentacion de negocio.
- Branding y estrategia estan en el repo privado `predictaflow/cerebro`.
- Cambios de contenido: editar index.html directamente. Netlify deploya automaticamente al hacer push a main.
