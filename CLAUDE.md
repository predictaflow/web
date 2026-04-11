# Predictaflow

## Proposito
Agencia creativa de contenido data-driven: detectar tendencias antes de que exploten y crear contenido diseñado para que el algoritmo trabaje a favor del cliente.

## Modo por defecto: modo-productivo

## Estado actual
- Fase: MVP publicado, pendiente de verificacion DNS/SSL y configuracion de email
- Hosting: GitHub Pages (rama main, directorio /)
- Dominio: predictaflow.me (Namecheap, Student Pack gratuito 1 ano)

## Contexto tecnico
- Stack: HTML/CSS puro, sin framework JS
- Hosting: GitHub Pages — repo `acamposla/predictaflow` (privado)
- Dominio: predictaflow.me registrado via Namecheap con GitHub Student Pack
- Fonts: Manrope (body) + DM Sans (headings) via Google Fonts
- Colores: primary `#4343FF`, accent `#FFD802`, highlight `#DAFFAA`
- Tema: claro, estilo Platanomelon (fondo blanco, secciones alternas blanco/verde lima/gris)

## Archivos clave
| Archivo | Descripcion | Estado |
|---|---|---|
| `index.html` | Landing page MVP completa | Publicada |
| `css/style.css` | Estilos principales (tema claro) | Publicada |
| `CNAME` | Apunta GitHub Pages a predictaflow.me | Configurado |
| `branding.json` | Referencia de branding de Platanomelon | Referencia |

## Decisiones tomadas
- **Netlify descartado**: GitHub Pages es suficiente para la landing estatica. Simplifica el stack.
- **Tema claro**: Se eligio estilo Platanomelon (blanco/verde lima) en lugar de tema oscuro.
- **SSL de Namecheap no necesario**: GitHub Pages incluye SSL via Let's Encrypt de forma gratuita. No hace falta activar el SSL del Student Pack de Namecheap.
- **Repo placeholder liberado**: `acamposla.github.io` era un placeholder de Namecheap al que se le quito el custom domain para reasignarlo a `predictaflow`.
- **Email de contacto**: judy@predictaflow.me (CTA en la landing)

## Proximos pasos
- [x] Registrar dominio predictaflow.me (Namecheap, Student Pack)
- [x] Inicializar repo GitHub y configurar GitHub Pages
- [x] Crear landing page MVP (hero, servicios, proceso, FAQ, CTA)
- [x] Redisenar a tema claro estilo Platanomelon
- [ ] Verificar HTTPS: esperar a que GitHub genere el certificado SSL (Let's Encrypt) y activar "Enforce HTTPS" en Settings > Pages
- [ ] Configurar DNS: confirmar que los registros A de Namecheap apuntan a las IPs de GitHub Pages
- [ ] Configurar email judy@predictaflow.me via Zoho Mail free (hasta 5 usuarios, 5GB)
- [ ] Review del copy y diseno de la landing tras uso real
- [ ] Investigar bot de tendencias: Helium10, Google Trends scraping, o SaaS de tendencias

## Deuda tecnica conocida
- La landing no tiene analytics (Google Analytics / Plausible / Fathom pendiente)
- Sin formulario de contacto funcional — el CTA es un mailto: a judy@predictaflow.me
- Sin version movil revisada en dispositivos reales

## Recursos disponibles
- GitHub Student Pack: https://education.github.com/pack (ver Catalogo_Recursos_GitHub en cerebro-digital)
- Cuenta Netlify disponible si se necesita en el futuro
- `branding.json`: referencia de estilo de platanomelon.com


## Integración con el sistema

- **Ficha Notion**: [rellenar URL o ID en DB Proyectos]
- **Capa de ejecución**: Notion
- **Tracking URL**: -
- **Routing**: ver `~/dotfiles/claude/skills/cierre-sesion/references/sistema-productividad.md` (Calendario de routing)

`cierre-sesion` actualiza las tareas en Notion DB Tareas (relación Proyecto → ficha de este repo) vía MCP Notion.
Reglas completas del sistema en `~/dotfiles/claude/skills/cierre-sesion/references/sistema-productividad.md`.
