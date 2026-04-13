# Predictaflow

## Proposito
Agencia creativa de contenido data-driven: detectar tendencias antes de que exploten y crear contenido diseñado para que el algoritmo trabaje a favor del cliente.

## Modo por defecto: modo-productivo

## Estado actual
- Fase: MVP publicado, HTTPS activo, email operativo
- Hosting: Netlify (site: predictaflow, URL: predictaflow.netlify.app)
- Dominio: predictaflow.me (Namecheap, Student Pack gratuito 1 ano)
- Email: judy@predictaflow.me (Zoho Mail Lite, misma org que verticedata.tech)

## Contexto tecnico
- Stack: HTML/CSS puro, sin framework JS
- Hosting: Netlify — deploy manual via `netlify deploy --prod --dir=. --site=6b427796-2a42-478d-85aa-7e9287eab3cb`
- Dominio: predictaflow.me registrado via Namecheap con GitHub Student Pack
- DNS: A record → 75.2.60.5 (Netlify), CNAME www → predictaflow.netlify.app
- Email: Zoho Mail Lite (2 usuarios: alejandro@verticedata.tech + judy@predictaflow.me)
- Fonts: Manrope (body) + DM Sans (headings) via Google Fonts
- Colores: primary `#4343FF`, accent `#FFD802`, highlight `#DAFFAA`
- Tema: claro, estilo Platanomelon (fondo blanco, secciones alternas blanco/verde lima/gris)

## Archivos clave
| Archivo | Descripcion | Estado |
|---|---|---|
| `index.html` | Landing page MVP completa | Publicada |
| `css/style.css` | Estilos principales (tema claro) | Publicada |
| `CNAME` | Eliminado (era de GitHub Pages) | N/A |
| `branding.json` | Referencia de branding de Platanomelon | Referencia |

## Decisiones tomadas
- **Netlify elegido sobre GitHub Pages**: HTTPS instantaneo, Netlify Forms para leads, misma infra que Vertice.
- **Vercel descartado**: No encaja con el stack actual (HTML estatico) ni con trends-engine (Python). Queda en radar para cuando se valide el SaaS y se necesite frontend pro en Next.js.
- **Tema claro**: Se eligio estilo Platanomelon (blanco/verde lima) en lugar de tema oscuro.
- **SSL via Netlify**: Automatico, sin configuracion manual. Namecheap SSL no necesario.
- **Zoho Mail compartido con Vertice**: Misma organizacion, 2 dominios (verticedata.tech + predictaflow.me). Coste: ~21.60 EUR/ano total (2 usuarios).
- **Repo placeholder liberado**: `acamposla.github.io` era un placeholder de Namecheap al que se le quito el custom domain para reasignarlo a `predictaflow`.
- **Email de contacto**: judy@predictaflow.me (CTA en la landing, buzon Zoho operativo)

## Proximos pasos
- [x] Registrar dominio predictaflow.me (Namecheap, Student Pack)
- [x] Inicializar repo GitHub y configurar GitHub Pages
- [x] Crear landing page MVP (hero, servicios, proceso, FAQ, CTA)
- [x] Redisenar a tema claro estilo Platanomelon
- [x] Migrar hosting a Netlify con HTTPS automatico
- [x] Configurar DNS en Namecheap (A → Netlify, CNAME www, MX → Zoho)
- [x] Configurar email judy@predictaflow.me via Zoho Mail Lite
- [ ] Review del copy y diseno de la landing tras uso real
- [ ] Investigar bot de tendencias: Helium10, Google Trends scraping, o SaaS de tendencias

## Deuda tecnica conocida
- La landing no tiene analytics (Google Analytics / Plausible / Fathom pendiente)
- Sin formulario de contacto funcional — el CTA es un mailto: a judy@predictaflow.me
- Sin version movil revisada en dispositivos reales

## Recursos disponibles
- GitHub Student Pack: https://education.github.com/pack (ver Catalogo_Recursos_GitHub en cerebro-digital)
- Cuenta Netlify: predictaflow.netlify.app (admin: app.netlify.com/projects/predictaflow)
- Zoho Mail admin: mailadmin.zoho.eu
- `branding.json`: referencia de estilo de platanomelon.com


## Integración con el sistema

- **Ficha Notion**: [rellenar URL o ID en DB Proyectos]
- **Capa de ejecución**: Notion
- **Tracking URL**: -
- **Routing**: ver `~/dotfiles/claude/skills/cierre-sesion/references/sistema-productividad.md` (Calendario de routing)

`cierre-sesion` actualiza las tareas en Notion DB Tareas (relación Proyecto → ficha de este repo) vía MCP Notion.
Reglas completas del sistema en `~/dotfiles/claude/skills/cierre-sesion/references/sistema-productividad.md`.
