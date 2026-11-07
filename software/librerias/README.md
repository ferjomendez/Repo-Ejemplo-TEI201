# Librerías

Ninguna librería viene incluida en el repositorio. Esta lista indica qué instalar y con qué versión se desarrolló el proyecto.

## Raspberry Pi y simulador

Se instalan con `pip install -r ../src/pi/requirements.txt` o con `apt` en la Pi.

| Librería | Versión mínima | Para qué |
|---|---|---|
| Flask | 3.0 | Servidor, API y stream SSE |
| NumPy | cualquiera reciente | Cálculo de medidas |
| OpenCV (`opencv-python-headless`) | cualquiera reciente | Correlación de fase y detección de líneas |
| Requests | cualquiera reciente | Pedir cuadros al teléfono |

En Raspberry Pi OS conviene usar los paquetes del sistema.

```bash
sudo apt install python3-opencv python3-numpy python3-requests python3-flask
```

## App Android

Las versiones están fijadas en `../src/android/gradle/libs.versions.toml`.

| Librería | Versión |
|---|---|
| Android Gradle Plugin | 9.4.1 |
| CameraX (core, camera2, lifecycle) | 1.4.2 |
| NanoHTTPD | 2.3.1 |
| AndroidX Lifecycle Service | 2.8.7 |
| Material Components | 1.10.0 |

## Firmware del ESP32

La prueba del motor no usa librerías externas. Solo necesita el paquete de placas ESP32 de Espressif instalado desde el gestor de placas de Arduino IDE 2.x.
