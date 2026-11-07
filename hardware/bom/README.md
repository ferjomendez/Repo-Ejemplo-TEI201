# Lista de materiales (BOM)

> **Precios inventados.** Los componentes son los reales del proyecto RockU, pero los costos son estimaciones de ejemplo en pesos chilenos y no vienen de una cotización. En tu proyecto debes poner el precio real y el enlace de compra de cada ítem.

El mismo contenido está en [BOM.csv](BOM.csv), que se abre directo en Excel.

| Ref | Componente | Cant. | Unitario CLP | Subtotal CLP | Función |
|---|---|---|---|---|---|
| PI1 | Raspberry Pi 4 Model B | 1 | 65.000 | 65.000 | Análisis de imagen, servidor y base de datos |
| SD1 | Tarjeta microSD de 32 GB | 1 | 8.000 | 8.000 | Sistema operativo y base de datos |
| PS1 | Fuente USB-C de 5 V y 3 A | 1 | 12.000 | 12.000 | Alimenta la Raspberry Pi |
| TEL1 | Teléfono Android (Samsung S25 Ultra) | 1 | 0 | 0 | Cámara cenital. Equipo que ya tenía el equipo, no se cuenta |
| ESP1 | ESP32-CAM | 1 | 9.000 | 9.000 | Nodo de distancia, la cámara no se usa |
| SN1 | Sensor ultrasónico HC-SR04 | 1 | 2.500 | 2.500 | Detección de objetos sobre la correa |
| R1-R2 | Resistencias de 1 kΩ y 2 kΩ | 2 | 100 | 200 | Divisor de voltaje para el pin ECHO del HC-SR04 |
| U1 | ESP32 TTGO T-Call V1.4 | 1 | 18.000 | 18.000 | Genera los pulsos STEP y DIR del motor |
| U2 | Driver A4988 (HR4988) | 1 | 3.500 | 3.500 | Controla el motor paso a paso |
| M1 | Motor paso a paso Minebea 17PM-K374BN02CN | 1 | 12.000 | 12.000 | Mueve la correa a escala |
| PB1 | Perfboard de pads individuales 70 x 90 mm | 1 | 1.500 | 1.500 | Soporta el control del motor |
| S1-S2 | Socket hembra 1x8 | 2 | 300 | 600 | Alojan el driver |
| S3-S4 | Socket hembra 1x21 | 2 | 500 | 1.000 | Alojan la TTGO |
| TB1 | Bornera de tornillo de 2 pines, paso 5.08 mm | 1 | 500 | 500 | Entrada de 12 V |
| C1 | Condensador electrolítico 100 µF 25 V | 1 | 300 | 300 | Absorbe picos de tensión en VMOT |
| J1 | Header macho 1x4 | 1 | 200 | 200 | Salida al motor |
| PS2 | Fuente de 12 V y 2 A | 1 | 7.000 | 7.000 | Alimenta motor y driver |
| D1 | Pantalla SPI de 3.5 pulgadas con touch XPT2046 | 1 | 15.000 | 15.000 | Estado en la caja de control |
| L1-L2 | Lámpara LED de corriente continua | 2 | 4.000 | 8.000 | Iluminación sin parpadeo de 50 Hz |
| B1 | Materiales de la correa (lona blanca, rodillos, estructura) | 1 | 20.000 | 20.000 | Correa a escala de 15 cm de ancho |
| E1 | Filamento PLA, unos 150 g | 1 | 3.500 | 3.500 | Caja de control |
| E2 | Soporte y brazo para teléfono y sensor | 1 | 6.000 | 6.000 | Mantiene la cámara a 28 cm y el sensor a 12 cm |
| H1 | Tornillos M3, separadores y cables | 1 | 3.000 | 3.000 | Montaje y conexiones |
| | **Total** | | | **196.800** | |

## Cómo leer el BOM

- La referencia (Ref) coincide con la del documento de la perfboard cuando el componente va ahí, como U1 para la TTGO, U2 para el driver, TB1, C1, J1 y S1 a S4.
- El teléfono no suma al costo porque es un equipo que el equipo ya tenía. Si hubiera que comprarlo, es el ítem que más cambia el total.
- Las lámparas LED se cuentan de a dos, a 4.000 pesos cada una.
- El total no incluye herramientas, soldador ni despacho.
