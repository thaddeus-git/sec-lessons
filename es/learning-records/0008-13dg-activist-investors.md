# Learning Record 0008 — Schedule 13D/G e Inversores Activistas

**Date**: 2026-06-17
**Lesson**: 0008-13dg-activist-investors.html
**Status**: Completado

## Conclusiones clave

1. **La diferencia esencial entre 13D y 13G radica en la "intención"**: 13D = inversor activista (activist), posee >5% y tiene intención de influir en la compañía; 13G = inversor pasivo (fondos indexados, pensiones), pura inversión sin intervenir en la gestión. El monitoreo de competidores casi solo se interesa por 13D.
2. **13D ocurre solo unos cientos de veces al año, frente a las 20 mil veces/trimestre de 13F = extremadamente escaso pero de señal extremadamente fuerte**. Cada aparición significa "alguien ha acumulado una posición significativa en tu empresa".
3. **Item 4 (Purpose of Transaction) es el alma del 13D**: El activista explica aquí "qué pretende hacer con esta empresa". Intenciones comunes: exigir una escisión, impulsar una fusión o adquisición, exigir cambio de CEO, exigir ajustes en la asignación de capital.
4. **Criterios para identificar a un activista**: ① Historial de presentaciones 13D; ② Historial de proxy fights; ③ Campañas activistas públicas; ④ Hedge fund con cartera concentrada y alta rotación.
5. **Estrategias comunes de activistas (ordenadas por intensidad de señal)**:
   - Asiento en el consejo (⭐⭐⭐⭐⭐) — Confrontación pública con la dirección
   - Asignación de capital (⭐⭐⭐⭐) — Voto de desconfianza
   - Impulso de M&A (⭐⭐⭐⭐) — Cambio de control
   - Mejora operativa (⭐⭐⭐) — Señal de valor oculto
6. **La "irreversibilidad" de la presentación 13D**: Una vez presentado públicamente un 13D, el activista y el consejo de administración entran en un "juego público" — ambas partes deben responder. No es tenencia pasiva, es **una declaración de confrontación activa**.
7. **Lenguaje vago en Item 4 = activista del tipo "primero iza la bandera, luego observa"**: Podría ser simplemente una toma de posición para presionar, sin intención real de lucha. Hay que esperar 60-90 días para ver si hay 13D complementario / proxy fight / nominación pública de consejeros.
8. **Particularidad de los ADR chinos**: UXIN es ADR, por lo que 13D/G aplica, pero la baja liquidez + el consejo chino + diferencias en el entorno legal → la capacidad real de impulsar cambios del activista es limitada. Que aparezca uno es, en sí mismo, una señal fuerte (evento raro).
9. **Brecha actual frente a IHS**: Lista estática de 8 activistas frente a ~50-100 de IHS. Para cerrar la brecha se necesita comprar WhaleWisdom / SharkWatch o realizar un escaneo manual mensual del informe mensual de 13D en EDGAR. En la fase MVP, la combinación más económica es "8 activistas + escaneo manual mensual + alerta de nuevo activista".

## Acciones pendientes

- Verificar: Si la lista ACTIVIST_INSTITUTIONS en config.py incluye a los activistas principales (Elliott, Starboard, Third Point, Baupost, Pershing Square, etc.)
- Verificar: Si la pestaña "Activists" del Dashboard está en una página separada (no mezclada con otras instituciones)
- Verificar: Si la extracción del Item 4 del 13D es automática o manual (en MVP debería ser revisión manual con resaltado)
- Dar seguimiento: Evaluar el ROI del tier más bajo de WhaleWisdom ($500-2000/año)
- Dar seguimiento: Evaluar si es necesario implementar una alerta automática de "nuevo activista" (basada en el informe mensual de 13D de EDGAR + filtrado por palabras clave)
