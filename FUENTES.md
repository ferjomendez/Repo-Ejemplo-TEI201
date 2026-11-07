# Fuentes

Este archivo vive en la raíz del repositorio porque la rúbrica del Avance 3 lo exige. Sin él, la dimensión Software se evalúa con nota 1.0. Aquí van el origen de todo lo que no escribió el equipo y las referencias técnicas que respaldan las decisiones.

## Código y proyecto de origen

| Elemento | Origen | Uso |
|---|---|---|
| Código de la Raspberry Pi, app Android, firmware, panel web y documentos técnicos | Repositorio propio [ferjomendez/RockU](https://github.com/ferjomendez/RockU), licencia MIT | Base técnica de este ejemplo |
| Estructura de carpetas y esqueleto del README | Plantilla [sebasdv/proyecto_final_TEI201](https://github.com/sebasdv/proyecto_final_TEI201), licencia MIT | Organización del repositorio |

## Librerías de software

| Librería | Dónde se usa | Licencia | Sitio |
|---|---|---|---|
| Flask | Servidor y API de la Pi | BSD-3-Clause | https://flask.palletsprojects.com |
| OpenCV (`opencv-python-headless`) | Correlación de fase, detección de líneas y manejo de imagen | Apache-2.0 | https://opencv.org |
| NumPy | Cálculo numérico en la detección | BSD-3-Clause | https://numpy.org |
| Requests | Pedir cuadros al teléfono | Apache-2.0 | https://requests.readthedocs.io |
| SQLite (módulo `sqlite3` de Python) | Registro de muestras y eventos | Dominio público | https://sqlite.org |
| CameraX | Captura de imagen en la app Android | Apache-2.0 | https://developer.android.com/media/camera/camerax |
| NanoHTTPD | Servidor HTTP dentro de la app Android | BSD-3-Clause | https://github.com/NanoHttpd/nanohttpd |
| Fuente Archivo | Tipografía del panel | SIL OFL 1.1 | https://fonts.google.com/specimen/Archivo |

Las versiones exactas están en [software/librerias/README.md](software/librerias/README.md).

## Modelos 3D de terceros

El archivo `diseno_3d/fusion360/perfboard_controlador_motor.f3d` incluye modelos descargados de terceros para la placa TTGO T-Call, el driver A4988 y el condensador. Los modelos originales no se redistribuyen por separado en este repositorio. No se anotó el autor ni el enlace al descargarlos, y ese dato queda por completar. Quien los necesite debe buscarlos en el sitio de cada fabricante.

## Datasheets y documentación técnica consultada

- Hoja de datos del driver A4988 (Allegro MicroSystems), para la fórmula de Vref y los micropasos. https://www.allegromicro.com/en/products/motor-drivers/brush-dc-motor-drivers/a4988
- Hoja de datos del sensor HC-SR04, para el rango y el ángulo de medición. https://cdn.sparkfun.com/datasheets/Sensors/Proximity/HCSR04.pdf
- Pinout de la placa TTGO T-Call V1.4 de LilyGO, para evitar los pines que usa el módem SIM800L. https://github.com/Xinyuan-LilyGO/LilyGo-T-Call-SIM800
- Hoja de datos del motor Minebea 17PM-K374BN02CN, del fabricante.
- Documentación de la Raspberry Pi. https://www.raspberrypi.com/documentation/computers/raspberry-pi.html

## Datos

| Dato | Origen |
|---|---|
| Métricas de `testing/datos/metricas` y `metricas_dificil` | Generadas por los scripts `evaluar_metricas.py` y `evaluar_dificil.py` sobre imágenes sintéticas del simulador del propio repositorio |
| Capturas del panel | Obtenidas del panel en modo simulador |
| Comparación de fuentes de imagen, teléfono contra ESP32-CAM | Medición propia, descrita en `software/docs/plan_sistema_deteccion.md` |
| Imágenes, plano, BOM con precios y resultados con usuarios y con la correa física | **Inventados para este ejemplo.** No corresponden a mediciones ni a modelos reales |

## Herramientas

Fusion 360 para el modelado, Android Studio para la app, Arduino IDE para el firmware y Chrome en modo headless para las capturas del panel. Las ilustraciones inventadas se generaron con Python y Matplotlib.
