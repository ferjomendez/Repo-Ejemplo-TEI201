# Archivos de Fusion 360

| Archivo | Origen | Qué contiene |
|---|---|---|
| [perfboard_controlador_motor.f3d](perfboard_controlador_motor.f3d) | Real, del proyecto RockU | Modelo editable de la perfboard con la TTGO T-Call, el driver A4988, el condensador, la bornera, los sockets y el cableado |
| [perfboard_controlador_motor.stl](perfboard_controlador_motor.stl) | Real, exportado del anterior | Vista 3D que GitHub abre en el navegador. No lleva colores ni pads de cobre para pesar menos de 10 MB |
| [ensamble_ejemplo_inventado.stl](ensamble_ejemplo_inventado.stl) | **Inventado** | Caja de control con la Pi, la perfboard, los separadores y la pantalla, más el motor, el ESP32-CAM, el HC-SR04, el teléfono y la fuente a un costado. Son volúmenes simples para ilustrar el gemelo 3D |

## Cómo abrirlos

- Para el `.f3d`, en Fusion 360 usa File, Open, Open from my computer.
- Para los `.stl`, haz clic en el archivo en GitHub y se abre el visor 3D.

## Modelos de terceros

El `.f3d` incluye modelos de la TTGO T-Call, del driver A4988 y del condensador, descargados de terceros. Están citados en [FUENTES.md](../../FUENTES.md).

## Qué falta para una entrega real

En un proyecto real, el `.f3d` del ensamble completo reemplaza al STL inventado. Debe abrir sin errores, ser paramétrico y mostrar todos los componentes con sus dimensiones reales.
