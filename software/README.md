# Software

Esta carpeta reúne todo el código del sistema y su documentación técnica. Está dividido según el equipo donde corre cada pieza.

## Carpetas

- `src/pi/` es el código Python de la Raspberry Pi. Incluye la detección, el servidor Flask, el registro en SQLite y el panel web.
- `src/android/` es el proyecto Android Studio de la app CorreaCam, que convierte el teléfono en cámara de red.
- `src/firmware/` guarda el firmware de Arduino para el ESP32. Por ahora contiene la prueba del motor paso a paso.
- `docs/` tiene la API, el plan del sistema, la explicación de la captura de datos y las capturas del panel.
- `librerias/` lista las dependencias con sus versiones.

## Stack tecnológico

| Equipo | Lenguaje | Piezas principales |
|---|---|---|
| Raspberry Pi 4 | Python 3 | Flask, OpenCV, NumPy, SQLite |
| Teléfono Android | Kotlin | CameraX, NanoHTTPD |
| ESP32 TTGO T-Call | C++ con Arduino IDE 2.x | Sin librerías externas en la prueba del motor |
| Panel y pantalla | HTML, CSS y JavaScript | Sin dependencias, todo se sirve desde la Pi |

## Cómo está organizado el código de la Pi

| Archivo | Qué hace |
|---|---|
| `deteccion.py` | Mide velocidad con correlación de fase, mide alineación con las dos líneas de la correa, calibra y clasifica el estado con confirmación por persistencia |
| `servidor.py` | Servidor Flask con la API, el stream en vivo por SSE, el panel y las exportaciones CSV |
| `fuentes.py` | Dos fuentes de datos intercambiables, la simulada y la real (teléfono, detector y ESP32) |
| `registro.py` | Guarda muestras y eventos en SQLite y exporta a CSV |
| `grabar.py` y `analizar.py` | Graban cuadros etiquetados desde el teléfono y los analizan fuera de línea |
| `simulador.py` | Genera correas sintéticas para probar los algoritmos sin hardware |
| `test_sintetico.py` y `test_servidor.py` | Pruebas automáticas de los algoritmos y del servidor |
| `evaluar_metricas.py` y `evaluar_dificil.py` | Producen las métricas de `testing/datos` |
| `graficos_ppt.py` | Dibuja los gráficos de `testing/evidencias` |

Cada módulo tiene un propósito único y las dos fuentes de datos comparten la misma interfaz. Por eso el panel funciona igual con el simulador que con la correa real.

## Instalación

### Raspberry Pi

```bash
sudo apt install python3-opencv python3-numpy python3-requests python3-flask
git clone https://github.com/ferjomendez/Repo-Ejemplo-TEI201.git
cd Repo-Ejemplo-TEI201/software/src/pi
```

En un computador cualquiera sirve `pip install -r requirements.txt`.

### Teléfono Android

1. Abre `software/src/android` en Android Studio y compila el módulo `app`.
2. Instala la app y concede los permisos de cámara y notificaciones.
3. Pulsa el botón de inicio. La app muestra la IP y el puerto 8080.
4. Desde un navegador de la misma red abre `http://IP_DEL_TELEFONO:8080/` y bloquea exposición, balance de blancos y enfoque.

El proyecto de Android Studio no incluye el `gradle-wrapper.jar`. Android Studio lo genera al sincronizar.

### ESP32

Abre `src/firmware/test_motor/test_motor.ino` en Arduino IDE 2.x, elige la placa ESP32 y carga el programa. Los pines están definidos al inicio del archivo.

## Uso

### Con el simulador

```bash
cd software/src/pi
python3 servidor.py --fuente sim
```

El panel queda en `http://IP_DE_LA_PI:5000/` y la pantalla de 3.5 pulgadas en `/mini`.

### Con la correa real

Primero se graba y se calibra con la correa en condición normal.

```bash
python3 grabar.py normal --segundos 20 --url http://IP_DEL_TELEFONO:8080
python3 grabar.py detenida --segundos 10 --url http://IP_DEL_TELEFONO:8080
python3 analizar.py calibrar videos/normal_<fecha> --detenida videos/detenida_<fecha> -o calibracion.json
python3 servidor.py --fuente real --telefono http://IP_DEL_TELEFONO:8080 --calibracion calibracion.json
```

El ESP32 avisa los objetos con `POST /event` y un cuerpo como `{"distancia_mm": 74, "n": 12}`. La Pi pide una foto al teléfono en ese instante y la guarda en `fotos/`.

### Pruebas automáticas

```bash
python3 test_sintetico.py
python3 test_servidor.py
```

## Calidad del código

- Cada función de `deteccion.py` tiene un solo trabajo y los umbrales viven en la calibración, no en el código.
- Los módulos se pueden probar por separado gracias a las fuentes intercambiables.
- La detección se valida con escenarios sintéticos antes de usar la correa, y las métricas quedan guardadas en `testing/datos`.
- La API está documentada en [docs/api.md](docs/api.md).

## Documentación

- [Captura de datos, repositorio e información generada](docs/captura_y_datos.md)
- [API del servidor](docs/api.md)
- [Plan del sistema](docs/plan_sistema_deteccion.md)
- [Servicio de arranque automático](docs/rockU.service)
