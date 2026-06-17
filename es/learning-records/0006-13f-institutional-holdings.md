# Learning Record 0006 — 13F y Tenencias Institucionales

**Date**: 2026-06-17
**Lesson**: 0006-13f-institutional-holdings.html
**Status**: Completado

## Conclusiones clave

1. **La esencia del 13F**: Es una instantánea de fin de trimestre, no un registro de flujo intratrimestral. Toda comparación entre períodos es una "aproximación de rebalanceo" entre dos 13F consecutivos — no es un turnover real.
2. **El error de unidad es una fuente frecuente de bugs**: El nombre del campo `value_x1000` significa "en miles de dólares". Errar por un factor de 1000 es un error clásico. Método de verificación: precio de la acción × número de acciones ≈ value_x1000 × 1000.
3. **En comparaciones interperíodos, usar número de acciones, no valor de mercado**: Cambio en número de acciones = rebalanceo activo; el cambio en valor de mercado está contaminado por fluctuaciones de precio. Si una institución mantiene 1 millón de acciones de CVNA sin moverse y el precio sube de $100 a $150, es un aumento pasivo de valor de mercado, no una compra adicional.
4. **El punto ciego del 13F es una limitación estructural**: Solo cubre posiciones largas, solo acciones estadounidenses, solo fin de trimestre, solo instituciones con >$100M bajo gestión. No muestra posiciones cortas, opciones, rebalanceos intratrimestrales, instituciones pequeñas ni inversores minoristas. **Esto determina que el 13F puede responder "quién compra y vende", pero no "por qué".**
5. **Condiciones de borde (5 estados de tenencia)**: Inicio / Liquidación / Aumento / Disminución / Sin cambio. Completar con `institution_name` tras un FULL OUTER JOIN para evitar división por cero cuando prev_value = 0.
6. **En la agregación, rankear por institución, no hacer simple SUM**: Las tenencias de Carvana por $1.92B frente a las de UXIN por $3M difieren 600 veces; sumar directamente diluiría la señal de UXIN. Los Top Buyers/Sellers deben agruparse "por ticker" o "por institución".
7. **El informe IHS Markit P2-P7 está construido casi enteramente sobre datos 13F** — por eso el 13F es la "base de datos del análisis de tenencias cruzadas".

## Acciones pendientes

- Verificar: Revisar si el pivot_table de cross_holding.py está agrupado y ordenado "por ticker" (no una simple SUM)
- Verificar: Revisar si el campo `value_x1000` mantiene la unidad original de la SEC en todo el flujo de datos
- Dar seguimiento: Considerar agregar una tarjeta comparativa "cambio en número de acciones vs. cambio en valor de mercado" en el Dashboard para que el ranking de Top Buyers/Sellers sea más preciso
