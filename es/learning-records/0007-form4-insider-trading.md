# Learning Record 0007 — Form 3/4/5 y Operaciones de Internos

**Date**: 2026-06-17
**Lesson**: 0007-form4-insider-trading.html
**Status**: Completado

## Conclusiones clave

1. **Ámbito de aplicación de Section 16**: Solo cubre a internos que poseen **valores registrados en EE. UU.** Los ejecutivos de ADR chinos (UXIN/ATHM) normalmente poseen derechos a nivel de VIE → no aplica. Por lo tanto, "sin datos" ≠ "fallo de recolección", es una "no aplicabilidad" estructural.
2. **Diferencias entre los tres formularios**: Form 3 (declaración inicial, una sola vez) / Form 4 (cada operación, 2 días hábiles, el más importante) / Form 5 (resumen anual, operaciones exentas).
3. **Table I vs Table II**: Table I = tenencias directas; Table II = opciones/derivados. M (ejercicio) + F (venta para impuestos) = operación combinada, no es señal bajista.
4. **Ponderación de códigos de transacción**:
   - P (compra activa) = 1.0 (señal fuerte)
   - S (venta activa) = 1.0
   - F (venta para impuestos) = 0.2 (señal débil conservada)
   - G (donación) = 0.3
   - A (concesión) = 0.0 (no cuenta como operación activa)
   - M (ejercicio) = 0.0 (solo considerar la venta posterior al ejercicio)
5. **Ponderación por rol**: CEO/CFO = 2.0 (el más sensible) / 10% Owner = 1.5 / Director = 1.0 / EVP/SVP/VP = 0.8.
6. **El plan 10b5-1 es la mayor fuente de error de interpretación**: Los planes de negociación preestablecidos por ejecutivos generan muchos pares de códigos F/S. **Para juzgar, es necesario revisar la fecha de presentación del plan 10b5-1** (en 8-K Item 8.01 o DEF 14A), no la operación en sí.
7. **Form 144 es un "avance"**: Notificación previa, no divulgación posterior. "Plan de vender en 90 días" ≠ "ya vendió". Múltiples Form 144 presentados consecutivamente = señal de reducción continua.
8. **Regla de alerta anómala para ADR chinos**: Si UXIN/ATHM presenta repentinamente un Form 4 → es una señal extremadamente importante (evento raro), el sistema debe activar una alerta roja.

## Acciones pendientes

- Verificar: Si insider_tracker.py implementa el algoritmo ponderado InsiderSentiment (ponderación por rol × ponderación por código de transacción)
- Verificar: Si los ADR chinos en el Dashboard muestran "No aplica" + nota explicativa (no "Sin datos")
- Dar seguimiento: Si es necesario incorporar el seguimiento de la fecha de presentación de planes 10b5-1 al sistema (alto ROI, reduce un 80% de los errores de interpretación)
- Dar seguimiento: Fuente de datos de "tasa de ejecución real" de Form 144 (OpenInsider tiene estos datos)
