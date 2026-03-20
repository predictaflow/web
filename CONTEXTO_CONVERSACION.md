# Contexto de Conversacion

## Ultima actualizacion
2026-03-20

## Que estabamos haciendo?
Lanzamiento del MVP web de Predictaflow: desde cero hasta una landing page publicada en GitHub Pages con dominio propio predictaflow.me.

## Estado de la tarea actual
La landing esta publicada y accesible. El bloqueo inmediato es el HTTPS: GitHub aun no ha generado el certificado SSL via Let's Encrypt. Hasta que no este listo, el boton "Enforce HTTPS" en GitHub Pages Settings aparece desactivado.

## Problemas abiertos
- **HTTPS pendiente**: GitHub Pages necesita propagar el DNS antes de emitir el certificado. Puede tardar hasta 24h desde que se configuro el custom domain. No hay accion a tomar salvo esperar y verificar en Settings > Pages.
- **DNS sin verificar**: Los registros A de Namecheap deben apuntar a las cuatro IPs de GitHub Pages (185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153). Pendiente confirmar que estan bien configurados.
- **Email no operativo**: judy@predictaflow.me existe como CTA en la landing pero Zoho Mail aun no esta configurado. Cualquier email enviado a esa direccion no llega a ninguna bandeja.

## Proximo paso concreto
Entrar en GitHub > repo predictaflow > Settings > Pages y verificar si el certificado SSL ya se genero. Si aparece el check verde y el boton "Enforce HTTPS" esta disponible, activarlo. Si aun no, volver a revisar en unas horas.

Despues, configurar Zoho Mail free para el dominio predictaflow.me:
1. Crear cuenta en zoho.com/mail
2. Verificar el dominio via TXT record en Namecheap
3. Crear el buzon judy@predictaflow.me

## Notas de sesion
- El repo `acamposla.github.io` era un repo placeholder que Namecheap habia creado automaticamente al registrar el dominio con el Student Pack. Se tuvo que quitar el custom domain de ese repo para poder asignarlo al repo `predictaflow`.
- El SSL del Student Pack de Namecheap (SectigoSSL) NO hace falta activarlo. GitHub Pages genera su propio certificado Let's Encrypt de forma automatica y gratuita.
- La landing tiene stats animados (72h anticipacion, 3x alcance, 100% datos), ticker marquee, proceso en 3 fases, 4 servicios, seccion "Para quien", comparativa agencia tradicional vs Predictaflow, FAQ con 5 preguntas, y footer completo.
- Idea pendiente de desarrollar: bot de tendencias que combine datos historicos (que se hablaba esta semana el ano pasado) con senales emergentes (que esta ganando traccion ahora). Herramientas candidatas: Helium10, Google Trends API, scraping de SaaS de tendencias.
