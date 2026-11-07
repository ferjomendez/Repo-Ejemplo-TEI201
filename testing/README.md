# Testing y validación

## Objetivo

Comprobar que el prototipo mide bien, detecta las tres situaciones y entrega información que sirve para decidir. La validación se hizo en tres niveles.

| Nivel | Qué se probó | Estado en este ejemplo |
|---|---|---|
| Simulación | Algoritmos con imágenes sintéticas en condiciones moderadas y extremas | **Real**, datos generados por los scripts del repositorio |
| Correa física | Detenciones, desalineaciones y objetos sobre la correa a escala | **Inventado** |
| Usuarios | Cinco personas interpretando el panel | **Inventado** |

> Las secciones inventadas existen para que el ejemplo tenga el formato completo. No son mediciones. En tu proyecto, el testing con usuarios debe tener al menos 5 personas reales y evidencia fotográfica o en video.

## Carpetas

| Carpeta | Contenido |
|---|---|
| [reportes](reportes) | Protocolo de pruebas y reporte de resultados |
| [datos](datos) | Métricas en JSON y tablas CSV |
| [evidencias](evidencias) | Gráficos de la simulación y una ilustración de la disposición de las pruebas |

## Documentos principales

- [Protocolo de pruebas](reportes/protocolo_pruebas.md)
- [Reporte de testing](reportes/reporte_testing.md)

## Resumen de resultados

| Prueba | Resultado | Origen |
|---|---|---|
| Exactitud de estados, condiciones moderadas | 100 % | Real |
| Exactitud de estados, condiciones extremas | 86.9 % | Real |
| Detención confirmada en la correa física | 19 de 20 | Inventado |
| Desalineación confirmada en la correa física | 18 de 20 | Inventado |
| Piedras detectadas | 28 de 30 | Inventado |
| Estados bien identificados por los usuarios | 19 de 20 | Inventado |
