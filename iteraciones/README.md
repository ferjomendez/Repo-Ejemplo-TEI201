# Historial de iteraciones

El proceso iterativo es lo que se evalúa en esta carpeta. Cada versión cuenta qué se probó, qué falló y qué se cambió.

> **Qué es real y qué es inventado.** La secuencia de decisiones técnicas, ESP32-CAM, luego teléfono y luego panel y control del motor, viene del proyecto real. Las fechas de cada versión y las fotos son inventadas. Los diagramas de arquitectura de cada carpeta sí son reales en su contenido.

## Estructura

```
iteraciones/
├── iteracion_1/    Concepto inicial con ESP32-CAM
├── iteracion_2/    Teléfono como cámara y Raspberry Pi
└── iteracion_3/    Sistema completo con panel, pantalla y control del motor
```

## Tabla comparativa

| Aspecto | v1 | v2 | v3 |
|---|---|---|---|
| Fecha (ejemplo) | 04-09-2026 | 02-10-2026 | 06-11-2026 |
| Cámara | ESP32-CAM, 320x240 | Teléfono, 1080x1440 | Teléfono, 1080x1440 |
| Cuadros por segundo | 5.6 | 10.3 | 10.3 |
| Análisis | Básico en la Pi | Velocidad y alineación con calibración | Igual que v2 con confirmación por persistencia |
| Salidas | Monitor serial | CSV y fotos | Panel web, pantalla 3.5 pulgadas, SQLite y CSV |
| Control de la correa | Manual | Manual | Motor paso a paso con driver A4988 |
| Principal problema | Imagen verdosa y sin JPEG por hardware | Sin interfaz para el operador | Falta validar con la correa real |

## Lecciones aprendidas

1. Un sensor de imagen barato limita todo lo que viene después. Cambiar la cámara mejoró más que ajustar los algoritmos.
2. Probar con imágenes sintéticas antes de la correa real permitió encontrar los modos de falla sin gastar tiempo de armado.
3. Un panel claro para el operador cambia el valor del sistema, porque convierte datos en una decisión.

## Detalle por versión

- [Iteración 1](iteracion_1/README.md)
- [Iteración 2](iteracion_2/README.md)
- [Iteración 3](iteracion_3/README.md)
