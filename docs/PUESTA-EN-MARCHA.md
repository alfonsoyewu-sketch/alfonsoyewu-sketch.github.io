# Puesta en marcha: lo que necesita tus cuentas

Todo lo técnico está hecho. Estos pasos requieren cuentas, pagos o decisiones tuyas. En orden,
calcula unas 2 horas en total.

## 0. Fusionar la rama de mejoras

La v0.3 vive en la rama `mejoras-feedback-octubre`. Revísala en local (`npm run dev`) y, si te
convence:

```bash
git checkout main
```

```bash
git merge mejoras-feedback-octubre
```

## 1. Dominio (15 min)

1. Cómpralo en cualquier registrador. Si no tienes preferencia, Vercel también los vende y te
   ahorras configurar DNS.
2. Cambia **una sola línea**: `dominio` en [src/config.ts](../src/config.ts), por ejemplo
   `'https://radar-mdr.es'`. De ahí salen el `og:url`, el sitemap, el `robots.txt`, el
   calendario y los botones de suscripción a Google Calendar y Outlook, que aparecen solos al
   cambiarla.

## 2. GitHub y Vercel (20 min)

1. Crea un repositorio vacío en GitHub (sin README ni licencia: ya existen).
2. Conéctalo y sube todo, sustituyendo `TU-USUARIO`:

```bash
git remote add origin https://github.com/TU-USUARIO/radar-mdr-ai-act.git
```

```bash
git push -u origin main --tags
```

3. En vercel.com: *Add New → Project*, importa el repo y despliega. Astro se detecta solo.
4. En *Settings → Domains* añade el dominio del paso 1.
5. Pon la URL del repo en `repositorio` de `src/config.ts`: aparecerá en el pie y en «Sobre mí».

## 3. Vigilancia automática (10 min)

1. GitHub → *Settings → Actions → General → Workflow permissions*: marca *Read and write*.
2. Opcional, en *Settings → Secrets and variables → Actions*:
   - `VERCEL_DEPLOY_HOOK`: créalo en Vercel (*Settings → Git → Deploy Hooks*). Redespliega cada mañana.
   - `ANTHROPIC_API_KEY`: añade un borrador de alerta en español a cada issue.
3. Pestaña *Actions → Vigilancia regulatoria → Run workflow*. Los snapshots ya están sembrados,
   así que desde la primera ejecución abrirá un issue si alguna fuente ha cambiado.

## 4. Vista previa en LinkedIn (5 min)

Pega la URL en el [Post Inspector](https://www.linkedin.com/post-inspector/). Debe salir la
imagen 1200 × 627, el título y la descripción. Más detalles y la convención de UTM en
[DISTRIBUCION.md](DISTRIBUCION.md).

## 5. Newsletter con Buttondown (20 min)

1. Crea la cuenta y elige el nombre de usuario.
2. Si tienes correo del dominio, úsalo como remitente.
3. En `src/config.ts`: `buttondownUsuario` (tu usuario) y `email` (el correo del dominio).
   El formulario con casilla de consentimiento sustituye solo al alta por correo, y la página
   de privacidad pasa a nombrar a Buttondown y su enlace de baja.

## 6. Analítica sin cookies con GoatCounter (5 min)

Crea un sitio en goatcounter.com y pon su código en `goatcounterCodigo` (por ejemplo `radar-mdr`
para radar-mdr.goatcounter.com). La página de privacidad se actualiza sola. GoatCounter no usa
cookies, así que no necesitas banner.

## 7. Formulario de Radar Pro con Tally (15 min)

Crea un formulario con estas preguntas, que son las de [ENTREVISTAS.md](ENTREVISTAS.md):

1. Tamaño de la empresa.
2. Clases de producto y mercados.
3. Horas al mes que dedicáis hoy a vigilar cambios regulatorios.
4. Qué haríais si el Radar no existiera (a mano, consultora, otra herramienta) y cuánto os cuesta.
5. Precio mensual que os parecería justo.

Luego descomenta el `iframe` de [pro.astro](../src/pages/pro.astro) y sustituye `TALLY_ID`.

## 8. Revisar «Sobre mí»

Lee [sobre-mi.astro](../src/pages/sobre-mi.astro): está escrito a partir de tu CV. Decide qué
correo quieres publicar (hoy figura alfonsoyewu@gmail.com y el CV usa alfonsoobreja@gmail.com).
Si quieres contar algo más personal, como por qué te importa la accesibilidad, es tu decisión:
no lo he incluido.
