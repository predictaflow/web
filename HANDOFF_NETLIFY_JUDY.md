# Sesión 2026-04-25 — Diagnóstico Netlify y siguiente paso: workflow de Judy

> Documento de traspaso. Origen: sesión Claude en repo `vertice/vertice-main` que terminó identificando que el problema real está en Predictaflow. Leer antes de retomar este repo.

## Qué encontramos

**Problema visible:** la cuenta Netlify free de `acamposla` (compartida entre Vértice y Predictaflow) agotó los 300 credits/mes el 25 abr (ciclo 13 abr — 12 may).

**Causa real (verificada vía `netlify-cli`):**

| Sitio | Deploys en el ciclo | Diagnóstico |
|---|---|---|
| **predictaflow** (`predictaflow/web`) | **21** | 18 push directos a `main` por `judymoneva`, uno por cada microajuste de copy. 3 deploys iniciales del setup. |
| **verticedata** (`Vertice-Data/verticedata-web`) | **0** | No tocada en el periodo. Inocente. |

**Patrón de Judy (ejemplo 15 abr):** 9 deploys el mismo día con commits tipo "fix: copy", "fix: simplificar CTA", "feat: nuevo tagline". Cada microcambio = `git push` directo a `main` = 1 deploy en producción = ~15 credits.

**Por qué pasa:** Judy usa `main` como borrador editable. No es un problema de mala intención, es de workflow + falta de capa de abstracción técnica.

## Decisión tomada (Vértice ↔ Predictaflow)

Separar cuentas Netlify por motivos **fiscales/contables + contención de impacto**, no por urgencia técnica. Sin prisa. Tarea para cuando haya 30 min libres.

**Email para nueva cuenta Netlify de Predictaflow:** `judy@predictaflow.me` (ya operativo). A futuro, cuando tenga sentido tener email de servicio, migrar a `admin@predictaflow.com` (o equivalente).

## Lo que toca trabajar AQUÍ (repo Predictaflow web)

**Objetivo:** Judy publica cambios en la web sin fricción técnica y sin quemar credits cada microedit.

**Restricciones de diseño (no negociables):**
- Judy no aprende git branches/PRs. Cualquier solución que le obligue a entender `git checkout -b` está descartada.
- Judy debe poder iterar copy y diseño en tiempo real (es su trabajo, lo hace bien).
- Alejandro no quiere ser cuello de botella revisando PRs de copy.

**Opciones a evaluar (ninguna decidida):**

1. **CMS visual sobre el repo** (Decap CMS, TinaCMS, Sveltia CMS). Judy edita por interfaz web tipo WordPress; el CMS commitea por ella, agrupando o publicando cuando le da a "Publicar". Coste: setup de 2-4h. Beneficio: cero git para Judy + control de cuándo se publica.

2. **`netlify.toml` con `[build.ignore]`**: red de seguridad para que cambios irrelevantes (logos, README, branding) no disparen deploy. No resuelve el patrón de microcommits de copy, solo los falsos positivos.

3. **Convención `[skip netlify]`** en commits intermedios. Requiere disciplina de Judy → no encaja con la restricción.

4. **Branch `draft` con auto-deploy a preview, `main` solo para producción**. Judy trabaja en `draft`, alguien (¿Claude? ¿Alejandro?) promociona a `main` cuando hay bloque cerrado. Carga operativa para Alejandro.

5. **Cloudflare Pages** en vez de Netlify (modelo de pricing distinto, builds ilimitados en free). Decisión separada, no resuelve el workflow pero quita el techo de credits.

**Recomendación de partida (a validar):** opción 1 (CMS) + opción 2 (`build.ignore`). El CMS resuelve el problema de raíz quitando git de la ecuación de Judy; `build.ignore` es seguro de bajo coste.

## Siguiente paso al abrir sesión aquí

1. Decidir si vamos por CMS o por workflow git con disciplina.
2. Si CMS: comparar Decap vs Sveltia vs TinaCMS para sitio estático con `index.html` (sin framework). Probable ganador: Decap o Sveltia (más simples, sin lock-in).
3. Implementar.

## Datos útiles para retomar

- Repo de la web (deploy source): `github.com/predictaflow/web`, branch `main`
- Site ID Netlify: `6b427796-2a42-478d-85aa-7e9287eab3cb`
- Local clone: `/home/alejandro/Proyectos/predictaflow/predictaflow/` (apunta al repo correcto, suele estar desactualizado porque Judy pushea desde su máquina — `git pull` antes de tocar nada)
- Stack actual del sitio: HTML estático puro (`index.html` + `css/`, sin framework)
- Comando para auditar deploys del periodo: `netlify api listSiteDeploys --data='{"site_id":"6b427796-2a42-478d-85aa-7e9287eab3cb","per_page":50}'`

## Ya cerrado en sesión origen (Vértice)

- `netlify-cli` instalado globalmente y autenticado (cuenta `acamposla`).
- `~/dotfiles/packages/npm_globals.txt` creado con `netlify-cli`.
- `~/dotfiles/scripts/bootstrap-ubuntu.sh` actualizado con paso 11 (instala npm globals + configura `~/.npmrc` con prefix). Reproducible en máquina nueva.
