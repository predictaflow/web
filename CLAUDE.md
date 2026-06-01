# Predicta Flow — Web

## Propósito
Landing page pública de Predicta Flow en predictaflow.me.
Reglas globales del proyecto: `cerebro/CLAUDE.md`.

## Modo por defecto: modo-productivo

## Contexto técnico

| Pieza       | Detalle                                                            |
|-------------|--------------------------------------------------------------------|
| Stack       | HTML/CSS puro, sin framework JS                                    |
| Hosting     | Netlify team `PredictaFlow` · deploy desde este repo · site ID `23eb2703-43cb-43ba-9b9b-f28dd294d509` |
| URL         | predictaflow.me · www.predictaflow.me · predictaflow.netlify.app   |
| Dominio     | predictaflow.me (Namecheap, GitHub Student Pack)                   |
| DNS         | A record → 75.2.60.5 (Netlify), CNAME www → predictaflow.netlify.app |
| Deploy      | Automático al hacer push a `main`                                  |

## Branding (referencia rápida)
Fuente de verdad: `cerebro/branding.json` (v3.0). Si este CLAUDE.md y el JSON divergen, prevalece el JSON.
En producción, el CSS (`css/style.css`) debe estar en sync con el JSON.

- **Fonts**: Familjen Grotesk (body) + Fraunces Italic (accent en titulares)
- **Tinta**: `#1A1530` · **Violeta**: `#5E3DF0` · **Lila**: `#C8B6F8` · **Cielo**: `#BEE5F3` · **Crema**: `#F4F1EC`
- **Tema**: directo, data-forward, agencia creativa con criterio

## Archivos clave

| Archivo          | Descripción                                                         |
|------------------|---------------------------------------------------------------------|
| `index.html`     | Landing page principal de Predicta Flow                             |
| `garza.html`     | Caso de estudio Garza (referencia de estilo para páginas internas)  |
| `prueba1.html`   | Borrador landing de servicios personales de Judy Moneva             |
| `css/style.css`  | Sistema de diseño compartido por todas las páginas                  |
| `images/`        | Logos, iconos, fondos, portfolio                                    |

## Contexto arquitectónico — prueba1.html

`prueba1.html` es el borrador de la sección de servicios de Judy dentro de un **colectivo** que está formando con Alejandro (datos/PIM) y Sergio (branding). La idea es que cada uno tenga su propia sección en una web conjunta futura.

- **Estructura de la página**: 7 secciones — Hero, Qué hago (5 tipos de servicio: Orgánico / UGC / Influencer / IA / Paid), Cómo trabajo (3 fases: Detección → Estrategia → Ejecución), Metodología (heatmap contenido×audiencia), Caso Garza, La diferencia (tabla comparativa), CTA.
- **Sistema de diseño**: usa `css/style.css` y las mismas tipografías y colores que el resto del sitio.
- **Pendiente de decidir**: nombre y dominio del colectivo — la URL final no está cerrada.
- `predictaflow.me` (index.html) se mantiene intacta y separada de este borrador.

## Reglas

- Este repo es **PÚBLICO**. No incluir datos internos, credenciales ni documentación de negocio.
- Branding, estrategia y decisiones internas están en el repo privado `cerebro/`.
- Cambios de contenido: editar `index.html` directamente. Netlify despliega al hacer push a main.
- No crear ramas. Acumular cambios en local y hacer push al final de sesión.
