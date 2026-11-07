# Firmware

| Carpeta | Estado | Contenido |
|---|---|---|
| [test_motor](test_motor/test_motor.ino) | Listo | Prueba de giro del motor paso a paso con rampa de velocidad. Pines STEP en GPIO18, DIR en GPIO19 y ENABLE en GPIO25 |

## Pendiente

El firmware del ESP32-CAM que lee el HC-SR04 y envía `POST /event` a la Pi no está escrito todavía. El contrato del evento está en [docs/api.md](../../docs/api.md). Mientras tanto, se pueden enviar eventos de prueba a la Pi con `curl`.
