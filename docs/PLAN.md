# Radar MDR × AI Act — Plan de construcción (verano 2026)

**Fecha del plan:** 5 de julio de 2026 · **Ventana:** 8 semanas (julio-agosto) · **Presupuesto:** ~10-15 € (dominio) · **Dedicación:** 15-20 h/semana, con kill-switch a 10 h si llega la media jornada.

---

## 0. Qué es y qué no es

**Es:** un observatorio en español de plazos y obligaciones regulatorias para tecnología médica e IA clínica (MDR, IVDR, AI Act, FDA QMSR). Cumple tres funciones a la vez: activo de validación del futuro SaaS, motor de contenido para LinkedIn y newsletter, y pieza de portfolio que demuestra dominio clínico-regulatorio + capacidad web.

**No es:** el SaaS. Este verano no factura por diseño — proteges la tarifa plana de 24 meses y la Cuota Cero (exigen no haber estado de alta en los 2 años previos) para el lanzamiento real de 2027-28.

**Criterio de éxito a 31 de agosto:** 30-50 suscriptores de newsletter · 10 entrevistas de problema completadas · 3-5 "pagaría por X" documentados con cita literal. Si alguien ofrece dinero espontáneamente por una versión pro, la señal de 2027 se ha adelantado un año.

**Por qué ahora:** el Digital Omnibus sobre IA acaba de cerrarse (acuerdo político 7-may-2026, Parlamento 16-jun, Consejo 29-jun; publicación en el DOUE inminente, en vigor a los 3 días) y ha movido las fechas que toda la industria tenía en sus planes. Todo fabricante necesita re-basar su calendario de cumplimiento — y ese re-baseo no existe compilado en español. Lanzas con la noticia caliente.

---

## 1. Contenido estrella ya verificado: la cronología post-Omnibus

Esta tabla es tu dato semilla — cárgala la primera semana tal cual y es ya la página más útil del sitio en español:

| Fecha | Qué aplica | Norma / referencia | A quién afecta |
|---|---|---|---|
| 2 feb 2026 | FDA QMSR en vigor (21 CFR 820 armonizado con ISO 13485) | FDA QMSR | Fabricantes que venden en EE. UU. |
| 26 may 2026 | Fin del transitorio para implantables a medida de clase III | MDR / Reg. (UE) 2023/607 | Fabricantes de producto a medida implantable de clase III |
| 28 may 2026 | Obligatoriedad de los 4 primeros módulos de EUDAMED (actores/SRN, UDI-dispositivos, ON y certificados, vigilancia de mercado); registro previo a comercializar dispositivos nuevos | Reg. (UE) 2024/1860 + Decisión (UE) 2025/2371 | Todos los operadores económicos MDR/IVDR |
| 2 ago 2026 | Obligaciones de transparencia del art. 50 AI Act — **no aplazadas** (salvo 50(2) para sistemas legacy) | AI Act, art. 50 | Proveedores y desplegadores de IA generativa/interactiva |
| 27-28 nov 2026 | Registro en EUDAMED de dispositivos legacy que sigan comercializándose *(confirmar día exacto en el aviso oficial: las fuentes citan 27 y 28)* | Reg. (UE) 2024/1860 | Fabricantes con producto anterior a may-2026 |
| 2 dic 2026 | Etiquetado de contenido sintético (art. 50(2)) para sistemas legacy + nuevas prácticas prohibidas (NCII/CSAM, art. 5) | AI Act (Omnibus) | Proveedores de IA generativa |
| 28 may 2027 | Carga por los organismos notificados de los certificados emitidos antes de may-2026 | Reg. (UE) 2024/1860 | Organismos notificados |
| 2 ago 2027 | Sandboxes regulatorios nacionales de IA + actos delegados para el Anexo I + fin de transición de GPAI legacy | AI Act (Omnibus) | Estados miembros / Comisión / proveedores GPAI |
| 2 dic 2027 | **Obligaciones de alto riesgo — sistemas independientes (Anexo III)** | AI Act cap. III (Omnibus) | Proveedores de HRAIS standalone |
| 31 dic 2027 | Fin del transitorio MDR: certificados legacy de clase III y IIb implantables (salvo exenciones listadas) | MDR / Reg. (UE) 2023/607 | Fabricantes legacy de alto riesgo |
| 2 ago 2028 | **Obligaciones de alto riesgo — IA embebida en productos regulados (Anexo I, incluye productos sanitarios)** | AI Act cap. III (Omnibus) | Fabricantes MedTech con IA |
| 31 dic 2028 | Fin del transitorio MDR: resto de IIb, IIa y clase I con intervención de ON (estéril, medición, quirúrgicos reutilizables) | MDR / Reg. (UE) 2023/607 | Fabricantes legacy de riesgo medio-bajo |

**Los matices que el 90% de los resúmenes se salta** (cada uno = un post de LinkedIn):

1. **Definición estrechada de "componente de seguridad":** la IA que solo asiste al usuario u optimiza rendimiento sin crear riesgo para la salud/seguridad queda fuera del alto riesgo. Crítico para clasificar SaMD.
2. **Grandfathering:** los sistemas comercializados antes de las fechas evitan las obligaciones de alto riesgo salvo "modificación sustancial" — qué cuenta como sustancial es contenido evergreen de altísimo valor.
3. **Mecanismo AI Act ↔ legislación sectorial:** la Comisión podrá desactivar duplicidades con la normativa de productos sanitarios vía actos de ejecución. Seguir esos actos = tu ventaja informativa permanente.
4. **Registro en la base de datos UE incluso para autoexcluidos:** quien se considere exento de la clasificación de alto riesgo debe registrarlo igualmente.
5. **Nueva categoría SMC (small mid-caps):** simplificaciones de documentación técnica extendidas más allá de las pymes.
6. **Los módulos de Vigilancia y PMS de EUDAMED llegan después** (previstos hacia finales de 2026): hasta que sean declarados funcionales, la notificación de incidentes sigue por las autoridades nacionales.

---

## 2. Arquitectura del sitio (9 secciones)

1. **Cronología viva** (la home): todos los plazos filtrables por norma, clase de producto y rol (fabricante/importador/distribuidor/desplegador).
2. **Obligaciones por clase de producto:** matrices MDR (I, Is/Im, IIa, IIb, III) e IVDR (A-D) × requisitos (evaluación clínica, organismo notificado, UDI/EUDAMED, PMS/PMCF, PSUR).
3. **IA clínica — intersección MDR × AI Act:** cuándo un SaMD con IA es alto riesgo (criterio doble confirmado por la MDCG 2025-6: ser producto sanitario o componente de seguridad + requerir organismo notificado, es decir clases IIa/IIb/III en MDR y B/C/D en IVDR), flujos de doble evaluación de conformidad y principio de no escalamiento recíproco de riesgos. Fichas estrella: **MDCG 2025-6** (interacción MDR/IVDR × AI Act, confirmada en el índice oficial de la Comisión) y **MDCG 2025-4** (software de producto sanitario en plataformas digitales y app stores).
4. **Fichas de guías MDCG en español:** una página por guía relevante (resumen de 300 palabras + a quién aplica + enlace oficial). Casi todo el material original está solo en inglés: traducir-resumir es el foso.
5. **Directorio de organismos notificados:** designados MDR/IVDR (base NANDO) con ámbito, país y, cuando llegue, designación AI Act.
6. **Comparador eQMS:** Greenlight Guru, Qualio, MasterControl, Matrix Requirements, openRegulatory (open source), etc. — precio orientativo, público objetivo, módulos.
7. **España:** AEMPS (licencia previa de funcionamiento, comunicaciones de comercialización), AESIA, tasas, particularidades nacionales.
8. **Glosario ES/EN:** términos regulatorios bilingües. Barrera mínima, valor SEO enorme.
9. **Newsletter "Radar quincenal":** cambios, guías nuevas, fechas que se acercan a 90/30 días.

**Prioridad para las 8 semanas:** secciones 1, 3, 4 (cinco fichas) y 9. El resto queda en esqueleto visible ("próximamente") — también comunica ambición.

---

## 3. Esquema de datos (6 entidades)

El valor de producto no está en los artículos: está en los **datos estructurados con fecha de verificación**. Nadie mantiene esto en español.

**Plazo (Deadline)**
`id · norma (MDR/IVDR/AI Act/QMSR) · referencia_legal (artículo) · fecha · tipo (aplicación / fin transitorio / registro / informe periódico) · rol_afectado · clases_producto[] · descripcion_corta · estado (vigente / aplazado / pendiente_confirmacion) · fuente_url · fecha_verificacion · nota_cambio`

**Obligación**
`id · norma · artículo · rol · clases_producto[] · obligacion · evidencia_requerida (doc. técnica, SGC, vigilancia…) · sancion_asociada · guia_relacionada (FK) · fuente_url · fecha_verificacion`

**Guía (MDCG y otras)**
`id · codigo (p. ej. MDCG 2020-1) · titulo · emisor · fecha · temas[] · resumen_es (~300 palabras) · relevancia_IA (1-5) · enlace_oficial`

**Organismo Notificado**
`id · numero_NANDO · nombre · pais · ambito (MDR/IVDR/AI Act) · codigos_designacion[] · web · notas`

**Herramienta eQMS**
`id · nombre · empresa · precio_desde · publico (startup/pyme/enterprise) · modulos[] (control documental, CAPA, ISO 13485, 21 CFR Part 11…) · especifica_IA (sí/no) · web`

**Fuente**
`id · nombre · tipo (legal / guía / agencia / industria) · url · idioma · frecuencia_actualizacion · tiene_RSS (sí/no)`

**Formato técnico:** colecciones de contenido de Astro (archivos JSON/Markdown con frontmatter validado por esquema Zod). Alternativa v0: Airtable o Google Sheets exportado a JSON. Los campos `estado + fecha_verificacion + nota_cambio` son el foso competitivo: convierten un blog en una base de datos confiable.

---

## 4. Las primeras 23 fuentes

**Textos legales (primarias absolutas)**
1. Reglamento (UE) 2017/745 (MDR), texto consolidado — EUR-Lex · *columna vertebral de plazos y clases*
2. Reglamento (UE) 2017/746 (IVDR), consolidado — EUR-Lex
3. Reglamento (UE) 2024/1689 (AI Act), consolidado — EUR-Lex · *añadir el Reglamento Omnibus en cuanto se publique en el DOUE*
4. Reglamento (UE) 2023/607 (prórroga de transitorios MDR/IVDR) — EUR-Lex · *fechas legacy por clase*
5. RD 192/2023 de productos sanitarios (España) — BOE
6. FDA QMSR / 21 CFR 820 final rule — fda.gov · *comparativa UE-EE. UU., contenido diferencial*

**Comisión Europea / gobernanza**
7. Índice de guías MDCG — health.ec.europa.eu (Medical Devices — Guidance) · *la madre de la sección 4*
8. MDCG 2025-6 (interacción MDR/IVDR × AI Act) y MDCG 2025-4 (MDSW en plataformas digitales) — health.ec.europa.eu · *documentos estrella de las secciones 3 y 4; añadir MDCG 2025-10 (vigilancia poscomercialización, dic-2025)*
9. AI Office / página oficial del AI Act — digital-strategy.ec.europa.eu · *actos de ejecución y guidelines*
10. EUDAMED — portal oficial + Decisión (UE) 2025/2371 · *4 módulos obligatorios desde 28-may-2026; legacy antes de fin de nov-2026; carga de certificados por ONs antes de 28-may-2027*
11. NANDO (base de organismos notificados) — ec.europa.eu/growth · *sección 5 completa*
12. Team-NB (asociación europea de ONs) — position papers y encuestas de capacidad
13. Lista de normas armonizadas MDR/IVDR publicadas en el DOUE

**España**
14. AEMPS — productos sanitarios (comunicaciones, licencia previa, notas informativas) — aemps.gob.es
15. AESIA (Agencia Española de Supervisión de la IA) — comunicaciones y régimen sancionador nacional
16. BOE — alertas temáticas por materia (suscripción gratuita)

**Normas técnicas (se citan, no se copian: son de pago)**
17. Fichas de catálogo: ISO 13485:2016, ISO 14971, IEC 62304, IEC 82304-1 — iso.org / UNE

**Industria y análisis (secundarias de calidad)**
18. MedTech Europe — posiciones y encuestas de capacidad de ONs
19. COCIR — IA en imagen médica y salud digital
20. RAPS Regulatory Focus — noticias regulatorias diarias
21. IMDRF — documentos marco de SaMD
22. FDA Digital Health Center of Excellence — IA/ML en dispositivos, PCCP
23. openRegulatory — plantillas open source (además, candidato al comparador) · blogs técnicos de BSI y TÜV SÜD como alerta temprana de interpretación

**Vigilancia:** Feedly (RSS de todo lo que lo tenga) + alertas de EUR-Lex + alertas del BOE + 3-4 Google Alerts con consultas exactas ("MDCG guidance", "AI Act medical devices", "AESIA").

---

## 5. Stack y flujo de trabajo

**Stack recomendado:** dominio (~10 €/año) · Astro + Vercel (gratis, y Astro suma a tu portfolio técnico) · Buttondown o Beehiiv para la newsletter (gratis en tu volumen) · Tally para formularios · umami o Plausible para analítica (opcional). Alternativa ultrarrápida si Astro te frena la primera semana: Notion publicado con Super — pero migra a Astro antes de septiembre.

**Rutina semanal (encaja en 15-20 h):**
- Lunes (45 min): pasada de vigilancia RSS/alertas → actualizar entidades con `fecha_verificacion`.
- Martes y jueves (1 h cada): un post de LinkedIn derivado de un dato del Radar.
- Viernes alternos (2 h): newsletter quincenal.
- Resto: construcción de secciones y entrevistas.

**Mini-automatización (semanas 6-7):** script en Python que descarga 10 URLs clave, compara hashes y te avisa por correo/Telegram si algo cambió. Es tu primer "agente de vigilancia regulatoria", te ahorra la mitad del lunes, y es un post excelente ("cómo vigilo 20 fuentes regulatorias en 30 minutos con 80 líneas de Python").

---

## 6. Calendario de 8 semanas

| Semana | Entregable de corte |
|---|---|
| S1 (6-12 jul) | Dominio + repo + esquema de datos definido + **cronología de la sección 1 online** (aunque sea fea) + 10 primeras fuentes cargadas |
| S2 (13-19 jul) | Resto de fuentes + formulario de suscripción + primer post: "El Omnibus ha movido tus fechas: la cronología completa en español" |
| S3-S4 (20 jul-2 ago) | 5 fichas MDCG en español + página de intersección IA clínica + arranque del outreach de entrevistas |
| S5-S6 (3-16 ago) | 5 entrevistas hechas + comparador eQMS v0 (5 herramientas) + script de vigilancia funcionando |
| S7-S8 (17-30 ago) | 5 entrevistas más + newsletters nº 2-3 + **página "Pro" fantasma**: lista de espera para "alertas personalizadas por clase de producto" — mide intención de pago real |
| 31 ago | Revisión contra criterios de corte → decisión de orientación del TFM y del ancla |

---

## 7. Guion de entrevista de problema (estilo Mom Test: pasado y concreto, nunca "¿usarías…?")

**A quién (4 perfiles):** responsable de Regulatory/Quality de pyme MedTech española · consultor/a regulatorio independiente · fundador de SaMD o IA clínica · técnico de calidad de fabricante tradicional. **Dónde encontrarlos:** LinkedIn (búsqueda "regulatory affairs" + "medical devices" + España), profesores y empresas colaboradoras del máster UC3M, contactos del 12 de Octubre, directorio de asociados de Fenin.

1. Cuéntame la última vez que tuviste que verificar un plazo o requisito nuevo. ¿Cómo lo hiciste, paso a paso?
2. ¿Qué fuentes revisas hoy y cada cuánto? ¿Quién lo hace en tu empresa?
3. ¿Cómo os habéis enterado del Omnibus de mayo y cuánto os llevó re-basar vuestro plan?
4. ¿Qué pasó la última vez que un cambio regulatorio os pilló tarde? ¿Qué costó (tiempo, dinero, certificado)?
5. ¿Cómo circula esta información dentro de la empresa? ¿Quién más la necesita?
6. ¿Pagáis hoy por alguna herramienta o servicio de vigilancia regulatoria? ¿Cuánto y qué os da?
7. ¿Qué parte del seguimiento regulatorio no querrías volver a hacer jamás?
8. Si existiera en español y siempre actualizado, ¿qué tendría que incluir para que lo consultaras cada semana?
9. ¿Qué te haría pagar 50-200 €/mes por ello? ¿Qué no pagarías nunca?
10. ¿A quién más debería hacerle estas preguntas? *(la que multiplica la muestra)*

**Registro por entrevista:** dolor (1-5) · herramienta actual · presupuesto declarado · cita literal · señal de compra (sí/no). Cinco filas de esta tabla valen más que cualquier plan de negocio.

---

## 8. Reglas y riesgos

- **0 € de ingresos este verano, por diseño.** Si alguien insiste en pagar: "en septiembre hablamos" + consulta al gestor sobre facturación puntual no habitual **con alta censal mediante el Modelo 036 (el 037 fue suprimido en febrero de 2025) y sin alta en RETA**, cursando la baja censal al terminar el encargo. Coste de oportunidad de quemar la tarifa plana + Cuota Cero por un cobro estival: en tu caso supera los 5.000 € (24 meses bonificados + reintegro autonómico + posible prórroga), no los 3.000 € del cálculo genérico de 12 meses.
- **Regla de neutralidad del comparador eQMS:** cada celda necesita ≥2 fuentes independientes (página oficial de precios del fabricante + G2/Capterra o consulta directa por email), las estimaciones se etiquetan como estimaciones y toda celda lleva `fecha_verificacion` visible. El blog de un fabricante que participa en la comparación (p. ej., openRegulatory/Formwork) puede ser *una* fuente, nunca el árbitro: si una herramienta gana todas las filas citando solo a su propio vendedor, eso es marketing, no datos — y publicarlo destruiría el único foso del Radar, su confiabilidad.
- **Copyright:** resumir con enlace a la fuente oficial; jamás republicar textos íntegros de guías, y las normas ISO/IEC se citan, no se copian (son de pago).
- **Disclaimer visible en todas las páginas:** información divulgativa; no constituye asesoramiento legal ni regulatorio.
- **Accesibilidad AA del sitio** (contraste, navegación por teclado, subtítulos en cualquier vídeo): coherencia con tu historia y ventaja SEO.
- **Kill-switch de tiempo:** si la media jornada llega en agosto, el Radar baja a 10 h/semana (vigilancia + newsletter + entrevistas; se pausa construcción). Está diseñado para sobrevivir a eso.
- **Regla de identidad:** el Radar es válido aunque el SaaS nunca exista — como portfolio, red y autoridad ya paga su coste. Eso te permite ejecutarlo sin ansiedad de resultado.
