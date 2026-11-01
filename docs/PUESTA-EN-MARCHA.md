# Puesta en marcha: lo que necesita tus cuentas

Todo lo técnico está hecho. Estos pasos requieren cuentas, pagos o decisiones tuyas.

## Hecho

- Repositorio en la organización `radar-mdr`: https://github.com/radar-mdr/radar-mdr.github.io
- Web publicada en GitHub Pages: https://radar-mdr.github.io (se republica en cada push y cada mañana).
- Correo del proyecto y LinkedIn configurados en `src/config.ts`.

## 1. Ajustes pendientes en GitHub (5 min)

1. En tu carpeta local, apunta git al repo nuevo (GitHub redirige el antiguo, pero mejor no depender de ello):

```bash
git remote set-url origin https://github.com/radar-mdr/radar-mdr.github.io.git
```

2. **Settings → Pages → Source: GitHub Actions.** Quita el check rojo de Jekyll.
3. En la portada del repo, engranaje de «About»: web `https://radar-mdr.github.io`.
4. Si conservas el proyecto de Vercel, bórralo: la web ya vive en Pages.

## 2. Dominio propio (opcional, unos 10 €/año)

1. Compra `radar-mdr.es` en un registrador que venda `.es`.
2. En su DNS: cuatro registros **A** para `@` (`185.199.108.153`, `185.199.109.153`,
   `185.199.110.153`, `185.199.111.153`) y un **CNAME** `www` → `radar-mdr.github.io`.
3. GitHub → Settings → Pages → *Custom domain*: `radar-mdr.es`, y marca *Enforce HTTPS*.
4. Cambia `dominio` en [src/config.ts](../src/config.ts): de ahí salen el `og:url`, el
   sitemap, el `robots.txt`, el RSS y el calendario.

## 3. Vigilancia automática (ya funciona a diario)

1. GitHub → *Settings → Actions → General → Workflow permissions*: marca *Read and write*.
2. Opcional, en *Settings → Secrets and variables → Actions*:
   - `ANTHROPIC_API_KEY`: añade un borrador de alerta en español a cada issue.
3. Revisa de vez en cuando los issues que abre: cada uno trae el diff de la fuente que ha cambiado.

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

Lee [sobre-mi.astro](../src/pages/sobre-mi.astro): está escrito a partir de tu CV. El correo
público es el de la cuenta del proyecto (`email` en `src/config.ts`); cámbialo a
`contacto@` de tu dominio cuando lo tengas. Si quieres contar algo más personal, como por qué te importa la accesibilidad, es tu decisión:
no lo he incluido.
