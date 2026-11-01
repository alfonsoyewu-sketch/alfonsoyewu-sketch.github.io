# Lo que falta: pasos que requieren tus cuentas

Todo lo técnico está hecho. Esto es lo único pendiente, ordenado por prioridad.

## 1. Revisar la vigilancia (30 min, y luego cada lunes)

En GitHub → *Issues* hay una incidencia por cada día en que alguna fuente vigilada cambió.
Para cada una:

1. Mira el diff. La mayoría son cambios de noticias o de menú, sin efecto en los datos.
2. Si cambia un dato (una guía MDCG nueva, una fecha), actualiza el JSON correspondiente con su
   entrada de `historial` (ver «Cómo corregir un plazo» en el README).
3. Cierra la incidencia con una línea: «Sin cambios de datos» o «Actualizado en <commit>».

Empieza por las del índice MDCG y de la AI Office: son las que más probablemente traen algo.

## 2. Vista previa en LinkedIn (5 min)

Pega `https://radar-mdr.github.io` y `https://radar-mdr.github.io/sobre-mi/` en el
[Post Inspector](https://www.linkedin.com/post-inspector/). Debe salir la imagen de 1200 × 627,
el título y la descripción. Para medir de dónde vienen las visitas, añade UTM a los enlaces de
cada post (ver [DISTRIBUCION.md](DISTRIBUCION.md)) y `?ref=linkedin` a los enlaces a `/pro/`.

## 3. GoatCounter (5 min)

1. Abre `https://radar-mdr.github.io/#toggle-goatcounter` en cada navegador y dispositivo que
   uses y acepta el aviso: desde entonces tus visitas no cuentan. Si borras los datos del
   navegador, repítelo.
2. Verifica el correo de la cuenta con el enlace que te envió GoatCounter.

## 4. Newsletter con Buttondown (20 min)

1. Crea la cuenta con radar.mdr.aiact@gmail.com y elige el nombre de usuario.
2. Pon ese usuario en `buttondownUsuario` de [src/config.ts](../src/config.ts).
3. Al publicar, /newsletter muestra el formulario con su casilla de consentimiento y la página
   de privacidad nombra a Buttondown. Cambia la fecha de «Última actualización» en
   [privacidad.astro](../src/pages/privacidad.astro).

## Si el Radar tiene tracción (decisión futura)

Hoy la beta cuesta 0 €. Antes de cobrar suscripciones conviene revisar:

- **Dominio propio** (`radar-mdr.es`, unos 10 €/año): en su DNS, cuatro registros **A** para
  `@` (`185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`) y un
  **CNAME** `www` → `radar-mdr.github.io`; después, GitHub → *Settings → Pages → Custom
  domain* y cambiar `dominio` y `email` en [src/config.ts](../src/config.ts).
- **GoatCounter** es gratuito para uso no comercial: con un producto de pago habría que pasar a
  su plan de pago, alojarlo por tu cuenta o cambiar de herramienta (compruébalo en su web).
- **Buttondown** es gratuito hasta 100 suscriptores (compruébalo en su web: cambia de planes a menudo).
- **Alta como autónomo** antes de facturar la primera suscripción (ver el plan, sección 8).
