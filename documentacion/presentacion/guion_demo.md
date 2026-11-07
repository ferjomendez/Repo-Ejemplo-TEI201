# Guion de la presentación y de la demo

La presentación dura entre 8 y 10 minutos y deja 3 para preguntas. Este guion reparte el tiempo y propone cómo mostrar un resultado que se pueda interpretar.

## Reparto del tiempo

| Láminas | Tema | Tiempo |
|---|---|---|
| 1 a 3 | Problema y solución | 1.5 minutos |
| 4 | Demo en vivo | 3 minutos |
| 5 a 7 | Datos, hardware y diseño 3D | 2 minutos |
| 8 a 10 | Resultados, fallas y validación | 2 minutos |
| 11 y 12 | Iteraciones y conclusiones | 1 minuto |

## Demo en vivo

La demo debe capturar datos, mostrarlos en el dashboard y terminar interpretando un resultado.

1. Arranca el servidor con `python3 servidor.py --fuente sim`, o con `--fuente real` si la correa está armada.
2. Abre el panel y muestra el estado normal con las cuatro medidas.
3. Provoca una detención, ya sea apagando el motor o con el atajo `2` en la pantalla de 3.5 pulgadas.
4. Espera a que el estado cambie a detenida y señala el tiempo que tardó en confirmarse.
5. Pasa una piedra bajo el sensor y muestra la foto en el registro de eventos.
6. Interpreta el resultado en voz alta, por ejemplo "esta detención duró un minuto y la disponibilidad de la última hora bajó de 100 a 96.4 por ciento".
7. Descarga el CSV para mostrar que el histórico queda disponible.

Prepara un plan B con el simulador por si falla la red del laboratorio. Un video pregrabado solo sirve como respaldo, no como demo principal.

## Preguntas probables y cómo responderlas

| Pregunta | Idea de respuesta |
|---|---|
| ¿Por qué un teléfono y no la ESP32-CAM? | Medimos las dos. El teléfono da 10.3 cuadros por segundo a 1080x1440 y la ESP32-CAM 5.6 a 320x240, además de una imagen verdosa |
| ¿Cómo evitan las falsas alarmas? | Cada estado debe mantenerse varios cuadros seguidos antes de confirmarse |
| ¿Cómo se calibran los umbrales? | Con la correa en condición normal, a partir del ruido medido |
| ¿Dónde falla el sistema? | Con contraste muy bajo, con una línea tapada y con valores pegados al umbral. Ya está analizado en el reporte de testing |
| ¿Cómo va montado el sensor y qué distancia tiene? | En un brazo a 12 cm sobre la correa, aguas arriba de la cámara, con un divisor de voltaje en el pin ECHO |
| ¿Cómo se repara? | Driver y TTGO en sockets, bornera de tornillo y tapa con cuatro tornillos M3 |
| ¿Qué falta? | Validar con la correa real, el firmware del sensor y el punto de acceso WiFi |

Todos los integrantes deben poder responder. Conviene que cada uno conozca los datos de su área y los del resto.
