# Distribución y medición

## Tres públicos distintos

| Papel | Quién | Qué necesita del Radar | Qué publicar para ellos |
|---|---|---|---|
| **Usuario** | Técnico/a de RA/QA en una pyme medtech | Saber qué fecha le toca y cuándo | Posts con un plazo concreto + enlace a la cronología filtrada (`/?rol=fabricante&clase=IIa`) |
| **Cliente** (quien pagaría Pro) | Dirección de calidad o gerencia de la pyme | Ahorro de horas y evidencia para auditorías | Posts sobre el coste de que se pase un plazo; casos de auditoría |
| **Prescriptor** | Consultoras, profesores, asociaciones (Fenin), organismos notificados | Material fiable que puedan citar | Recursos citables: matrices, ISO 14971 en 5 minutos, glosario, API (CC BY) |

Una regla práctica: uno de cada tres posts, para prescriptores.

## UTM en cada enlace

Formato fijo para que la analítica (GoatCounter) agrupe bien:

```
?utm_source=linkedin&utm_medium=social&utm_campaign=AAAA-MM-DD-tema
```

- `utm_source`: `linkedin`, `newsletter`, `email`, `whatsapp`, `clase`
- `utm_medium`: `social`, `email`, `referral`
- `utm_campaign`: fecha del post + tema corto, p. ej. `2026-10-20-eudamed-legacy`

Ejemplo de enlace a una vista filtrada con UTM:

```
https://TU-DOMINIO/?rol=fabricante&clase=IIa&utm_source=linkedin&utm_medium=social&utm_campaign=2026-10-20-eudamed-legacy
```

Los parámetros `utm_*` no interfieren con los filtros: la portada solo lee `norma`, `rol`, `clase` y `pasados`.

## Comprobar la vista previa antes de publicar

1. Despliega con el dominio definitivo en `src/config.ts` (`SITIO.dominio`).
2. Pega la URL en el [Post Inspector de LinkedIn](https://www.linkedin.com/post-inspector/).
3. Debe salir la imagen `og-radar.png` (1200 × 627), el título y la descripción. Si sale una
   versión antigua, pulsa «Inspect» de nuevo para refrescar la caché.

## Primeros posts sugeridos

1. EUDAMED: el 28-11-2026 vence el registro de productos legacy (con el dato resuelto y la fuente HPRA).
2. «El Omnibus movió tu fecha»: 2-8-2028 para productos sanitarios con IA, y por qué la MDCG 2025-6 ya está desfasada.
3. La escalera del lunar: cómo sube la clase MDR con cada función (para prescriptores y docentes).
4. Fe de erratas pública: qué aprendí al equivocarme con «modificación sustancial» (CAPA en abierto).
5. 52 organismos notificados MDR y ninguno todavía para el AI Act (dato de NANDO).
