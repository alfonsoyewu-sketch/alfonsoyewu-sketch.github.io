# Día final de programación — Radar MDR × AI Act

**Objetivo de hoy:** congelar la máquina. Al terminar, todo lo que quede del verano se hace editando `.json`/`.md` y hablando con humanos. Cero programación después de hoy.

Copia el contenido de esta carpeta **en la raíz de tu repo** (las rutas ya coinciden: `src/pages/…`, `src/components/…`, `scripts/…`, `.github/…`, `public/…`).

---

## Orden del día (≈ 5-7 h en total)

### PRIORIDAD A — sin esto no hay Radar (≈ 3 h)

1. **Dominio + Vercel** (45 min) — si aún no está hecho, es lo primero. Nada compuesta hasta que haya URL.
2. **Copiar archivos + dependencias** (20 min)
   ```bash
   npm i @astrojs/rss marked
   npm i -D pagefind
   npx astro add sitemap        # responde "yes" a todo
   ```
3. **astro.config.mjs** (5 min): añade tu dominio —
   ```js
   export default defineConfig({ site: 'https://TU-DOMINIO', /* …integraciones… */ });
   ```
4. **package.json** (2 min): `"build": "astro build && pagefind --site dist"`
5. **Ajustes de campos** (20 min): los archivos asumen el esquema del plan (`id, norma, referencia_legal, fecha, rol_afectado, descripcion_corta, estado, fuente_url, fecha_verificacion, nota_cambio`). Si algún nombre difiere en tus JSON, ajusta los imports/campos — están todos marcados con comentarios `AJUSTA`.
6. **Countdown en la cronología** (15 min): importa `Countdown.astro` en tu página de inicio y añade `<Countdown fecha={p.fecha} estado={p.estado} />` a cada fila.
7. **Probar en local** (30 min):
   ```bash
   npm run build && npm run preview
   ```
   Checklist de URLs: `/calendario.ics` (descarga y ábrelo en tu calendario) · `/api/plazos.json` · `/rss.xml` · `/cambios/` · `/guias/` · `/pro/` · `/buscar/` (solo funciona tras build, no en dev).
8. **Deploy** y repetir el checklist en producción.

### PRIORIDAD B — la automatización (≈ 1,5 h)

9. **GitHub → Settings → Actions → General → Workflow permissions:** marca *Read and write permissions* (el workflow también lo pide en su bloque `permissions`, pero así no hay sorpresas).
10. **Secrets opcionales** (Settings → Secrets and variables → Actions):
    - `VERCEL_DEPLOY_HOOK`: créalo en Vercel (Project → Settings → Git → Deploy Hooks) y pégalo. Hace que el sitio se reconstruya cada mañana → las cuentas atrás se refrescan solas.
    - `ANTHROPIC_API_KEY`: opcional, para el borrador de alerta con IA (céntimos por ejecución con Haiku). Sin la clave, el paso se salta solo.
11. **Sembrar snapshots:** pestaña Actions → "Vigilancia regulatoria" → *Run workflow*. La primera ejecución solo guarda los snapshots iniciales (no abre issue). A partir de mañana, cada cambio real en las 8 fuentes abre un issue con el diff — tu backlog se escribe solo.

### PRIORIDAD C — si sobra tiempo (≈ 1 h)

12. **Buttondown** (formulario de suscripción, adelanta la S2): crea cuenta, y pega en tu página de inicio:
    ```html
    <form action="https://buttondown.com/api/emails/embed-subscribe/TU_USUARIO" method="post">
      <label for="bd-email">Boletín quincenal de plazos y cambios</label>
      <input type="email" name="email" id="bd-email" placeholder="tu@email.com" required />
      <button type="submit">Suscribirme</button>
    </form>
    ```
13. **Tally** para `/pro/`: crea el formulario (tamaño de empresa · clase de producto · "¿qué precio mensual te parecería justo?") y sustituye `TALLY_ID` en `src/pages/pro.astro`.
14. **robots.txt:** sustituye `TU-DOMINIO` en `public/robots.txt`.
15. **Commit final con tag:**
    ```bash
    git add -A && git commit -m "v0.2 — code freeze de verano" && git tag v0.2 && git push --tags
    ```

---

## Qué hace cada archivo

| Archivo | Qué aporta |
|---|---|
| `src/pages/calendario.ics.ts` | Calendario suscribible con todos los plazos + alarma a 30 días. Tu mejor imán de emails. |
| `src/pages/api/plazos.json.ts` / `fuentes.json.ts` | API pública de solo lectura. Te posiciona como infraestructura; semilla del Pro 2027. |
| `src/pages/rss.xml.js` | Feed RSS autogenerado desde `nota_cambio` + `fecha_verificacion`. |
| `src/pages/cambios.astro` | Changelog público. **Doble uso:** las entradas desde el último envío = borrador de la newsletter. |
| `src/components/Countdown.astro` | Chips "faltan N días" con resaltado a 90/30. Convierte la tabla en radar. |
| `src/pages/guias/index.astro` + `[id].astro` | Plantillas de fichas MDCG. Añadir ficha = editar `guias.json`. |
| `src/components/TablaEQMS.astro` + `herramientas.ejemplo.json` | Comparador con la regla de neutralidad codificada (≥2 fuentes o muestra ⚠). |
| `src/pages/pro.astro` | Página fantasma del Pro (S7-S8 ya construida hoy). |
| `src/pages/buscar.astro` | Buscador Pagefind. |
| `scripts/vigilancia.py` + `.github/workflows/vigilancia.yml` | Vigilancia diaria: diff de 8 fuentes → issue automático → redeploy. |
| `scripts/resumen_ia.py` | Opcional: borrador de alerta en español dentro del issue (humano revisa antes de publicar). |
| `public/robots.txt` | SEO básico (con el sitemap que añade `astro add sitemap`). |

---

## La regla de congelación (pégala en tu README)

A partir de mañana, cada tarea pendiente del verano es **datos o personas, nunca código**:

| Tarea S2-S8 | Ahora es… |
|---|---|
| 5 fichas MDCG | escribir en `src/data/guias.json` |
| Comparador eQMS | rellenar `herramientas.json` (≥2 fuentes por fila) |
| Newsletter nº 1-3 | copiar `/cambios/` desde el último envío → Buttondown |
| Alertas de cambios | revisar los issues que abre el bot |
| Página Pro | ya existe; solo mirar las respuestas de Tally |
| 10 entrevistas | LinkedIn + calendario, cero código |

Si un viernes dudas entre una feature y dos mensajes a RA managers, **ganan los mensajes** — el sitio es la excusa; las entrevistas son el producto.
