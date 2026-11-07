# Datos

| Archivo o carpeta | Origen | Contenido |
|---|---|---|
| [metricas/metricas.json](metricas/metricas.json) | Real | Caso base con calibración, exactitud, errores, latencias, barridos y 22 escenarios |
| [metricas_dificil/metricas_dificil.json](metricas_dificil/metricas_dificil.json) | Real | Escenarios moderados y extremos, con exactitud por grupo |
| [metricas](metricas) y [metricas_dificil](metricas_dificil) | Real | Imágenes de las matrices de confusión y de los resultados por escenario |
| [pruebas_correa_fisica_inventadas.csv](pruebas_correa_fisica_inventadas.csv) | **Inventado** | Resultados de la prueba con la correa física |
| [usuarios_inventados.csv](usuarios_inventados.csv) | **Inventado** | Resultados de la prueba con cinco usuarios |

## Cómo se generan los datos reales

Desde `software/src/pi`, con las dependencias instaladas.

```bash
python3 evaluar_metricas.py
python3 evaluar_dificil.py
python3 graficos_ppt.py
```

Los scripts usan el simulador de correa del repositorio, por lo que los resultados se pueden reproducir. Los archivos de este directorio son una copia de lo que producen.

## Los CSV se abren en Excel

Los archivos usan UTF-8 con BOM, así que los acentos se ven bien al abrirlos directamente.
