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

## 2. Leer «Sobre mí» (10 min)

Lee [sobre-mi.astro](../src/pages/sobre-mi.astro). Comprueba sobre todo que la declaración de
independencia es exacta: no recibes dinero de fabricantes, consultoras, organismos notificados
ni proveedores de eQMS. Si algo cambia, se edita ahí mismo.

## 3. Vista previa en LinkedIn (5 min)

Pega `https://radar-mdr.github.io` y `https://radar-mdr.github.io/sobre-mi/` en el
[Post Inspector](https://www.linkedin.com/post-inspector/). Debe salir la imagen de 1200 × 627,
el título y la descripción. Para medir de dónde vienen las visitas, añade UTM a los enlaces de
cada post (ver [DISTRIBUCION.md](DISTRIBUCION.md)) y `?ref=linkedin` a los enlaces a `/pro/`.

## 4. GoatCounter (2 min)

En tu panel de GoatCounter → *Settings*, activa la opción de no contar tus propias visitas para
que tus pruebas no inflen las cifras.

## 5. Newsletter con Buttondown (20 min)

1. Crea la cuenta con radar.mdr.aiact@gmail.com y elige el nombre de usuario.
2. Pon ese usuario en `buttondownUsuario` de [src/config.ts](../src/config.ts).
3. Al publicar, /newsletter muestra el formulario con su casilla de consentimiento y la página
   de privacidad nombra a Buttondown. Cambia la fecha de «Última actualización» en
   [privacidad.astro](../src/pages/privacidad.astro).

## 6. Vercel

Si el proyecto de Vercel sigue existiendo, bórralo (*Settings → General → Delete Project*):
la web vive en GitHub Pages y no conviene tener dos copias.

## 7. Dominio propio (opcional, unos 10 €/año)

1. Compra `radar-mdr.es` en un registrador que venda `.es`.
2. En su DNS: cuatro registros **A** para `@` (`185.199.108.153`, `185.199.109.153`,
   `185.199.110.153`, `185.199.111.153`) y un **CNAME** `www` → `radar-mdr.github.io`.
3. GitHub → *Settings → Pages → Custom domain*: `radar-mdr.es`, y marca *Enforce HTTPS*.
4. Cambia `dominio` en [src/config.ts](../src/config.ts) y, si creas `contacto@radar-mdr.es`,
   también `email`. GitHub redirige solo desde radar-mdr.github.io.
