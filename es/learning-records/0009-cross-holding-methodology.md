# Learning Record 0009 — Metodología de Análisis de Tenencias Cruzadas

**Date**: 2026-06-17
**Lesson**: 0009-cross-holding-methodology.html
**Status**: Completado

## Conclusiones clave

1. **Cada página responde una pregunta de inversión concreta** es la filosofía de diseño central del informe de tenencias cruzadas. El informe IHS P4 tiene 10 páginas = 10 preguntas. Acumular datos no es un informe.
2. **La validación cruzada entre páginas es donde reside la verdadera percepción**. 4 escenarios clásicos:
   - Confirmatorio (P2 gran tenencia + P3 aumento + P5 Top Buyer) = señal fuerte
   - Contradictorio (P2 gran tenencia + P3 pequeña reducción + P6 no es Top Seller) = podría ser rebalanceo
   - Peligroso (P4 activist + P7 nueva posición) = alerta de alto nivel
   - Cambio de tendencia (P8 capital pasivo en aumento + P9 rotación valor/crecimiento) = cambio en el ciclo de vida del sector
3. **Orden correcto de lectura del informe**: Vista rápida de 30 segundos → tendencias de 2 minutos → profundidad de 5 minutos → investigación de 15 minutos. El diseño del Dashboard debe soportar este ritmo (tarjetas de resumen más visibles, datos profundos en pestañas).
4. **6 principios de diseño**:
   - Cada página responde una pregunta
   - Cada página deja espacio en blanco para Commentary (para que el analista escriba su juicio)
   - Las columnas de las tablas deben alinearse con los estándares del sector (Style / Turnover / Peer Average son imprescindibles)
   - Las tablas de ranking deben indicar la métrica de clasificación
   - Gráficos y tablas deben complementarse (gráfico circular para distribución, gráfico de barras para flujos)
   - El descargo de responsabilidad debe ser visible (al pie de cada página, no al final del documento)
5. **Flujo unidireccional de Top Buyers/Sellers = 99% de probabilidad de bug**. En condiciones normales hay flujo bidireccional (unos compran, otros venden). Causas comunes: error en comparación interperíodos, error en mapeo de campos, fuente de datos faltante. **La lista de autoverificación debe incluir obligatoriamente "¿Tanto Buyers como Sellers tienen datos?"**.
6. **En comparaciones interperíodos, usar número de acciones (shares delta), no valor de mercado (value delta)**. El cambio en valor de mercado está contaminado por fluctuaciones de precio. Los Top Buyers deben ordenarse por "compra activa" o "cambio en número de acciones".
7. **Análisis práctico de Carvana 2026Q1**: Vanguard/BlackRock mantienen su participación sin cambios (capital pasivo indexado estable) + Baupost añadió $480M (inversor value reingresando) + sin activist = "índice estable + revalorización value + sin interferencia de activistas" → estado más bien positivo.
8. **Lista de autoverificación de 10 puntos para calidad de salida**: Unidades, métrica de ranking, institution_name, condiciones de borde de delta_pct, simetría Buyers/Sellers, comparación interperíodos adyacente, descargo de responsabilidad, rezago temporal, revisión de Item 4, etiquetado "No aplica" para ADR chinos.

## Acciones pendientes

- Verificar: Si la salida de cross_holding.py cumple con el diseño de "cada página responde una pregunta" (referencia IHS P2-P10)
- Verificar: Si el ritmo de lectura del informe Markdown soporta los niveles de 30 segundos / 2 minutos / 5 minutos / 15 minutos
- Verificar: Si los 10 puntos de la lista de autoverificación se ejecutan automáticamente antes de exportar el informe (no manualmente)
- Dar seguimiento: Si es necesario añadir espacio en blanco para "Commentary" al pie de cada página del Dashboard (donde el analista escribe su juicio)
- Dar seguimiento: Evaluar si la lógica de "comparación interperíodos" debe unificarse en la función `comparative_holdings()` (para evitar que cada pestaña implemente la suya propia)
