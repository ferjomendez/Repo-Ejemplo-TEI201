# Protocolo de pruebas

Documento escrito antes de ejecutar las pruebas. Define qué se mide, bajo qué condiciones, cómo se hace y qué resultado se considera exitoso.

> Los protocolos B y C son el plan que seguiría el equipo en el ejemplo. Sus resultados son inventados, ver el [reporte](reporte_testing.md). El protocolo A se ejecutó de verdad con los scripts del repositorio.

## Prueba A, algoritmos con imágenes sintéticas

| Elemento | Detalle |
|---|---|
| Objetivo | Medir la exactitud del clasificador de estados y el error de las medidas de velocidad, desvío y ángulo |
| Condiciones | Imágenes de 1080x1440 a 10 cuadros por segundo con ruido, desenfoque, parpadeo de luz, vibración, reflejos y cambios de escala. Hay dos niveles, moderado y extremo |
| Procedimiento | 1. Calibrar con imágenes limpias. 2. Ejecutar `python3 evaluar_metricas.py` y `python3 evaluar_dificil.py`. 3. Revisar los JSON de `testing/datos` y los gráficos de `testing/evidencias` |
| Criterio de éxito | Exactitud de 95 % o más en condiciones moderadas y error medio de velocidad menor a 2 % |
| Evidencia | Archivos JSON y 13 gráficos |

## Prueba B, correa física

| Elemento | Detalle |
|---|---|
| Objetivo | Confirmar que el prototipo detecta detenciones, desalineaciones y objetos reales |
| Condiciones | Correa a escala de 15 cm de ancho a 10 cm/s, teléfono a 28 cm, sensor a 12 cm, dos lámparas LED, calibración hecha con la correa en condición normal |
| Procedimiento | 1. Calibrar. 2. Provocar 20 detenciones apagando el motor. 3. Provocar 20 desalineaciones de 6 mm corriendo un rodillo. 4. Pasar 30 piedras bajo el sensor. 5. Dejar la correa 30 minutos en condición normal. 6. Anotar cada detección y su tiempo de confirmación |
| Criterio de éxito | 90 % o más de detección en cada situación y menos de una falsa alarma cada 30 minutos |
| Evidencia | Tabla CSV, fotos de cada evento guardadas por el sistema y registro de la base de datos |

## Prueba C, usuarios

| Elemento | Detalle |
|---|---|
| Objetivo | Ver si una persona sin entrenamiento entiende el estado de la correa mirando el panel |
| Participantes | 5 personas con perfiles distintos |
| Procedimiento | 1. Explicar el prototipo en 5 minutos. 2. Mostrar cuatro estados, normal, detenida, desalineada y objeto. 3. Medir el tiempo que tarda cada persona en nombrar el estado. 4. Hacer una entrevista corta de 10 minutos |
| Criterio de éxito | 80 % o más de estados bien identificados y menos de 10 segundos en promedio |
| Evidencia | Tabla CSV, notas de la entrevista y fotos de la sesión |
