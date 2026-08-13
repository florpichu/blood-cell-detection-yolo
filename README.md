# Detección y conteo de glóbulos y plaquetas con YOLOv8

Proyecto de **Laboratorio 6** (FCEyN, UBA) — el laboratorio de fin de carrera donde cada estudiante propone y desarrolla su propio proyecto experimental. Realizado en conjunto con [Maximiliano Rodríguez Camps](https://github.com/).

## Contexto

Este proyecto se enmarca dentro de una línea de investigación más amplia sobre **diagnóstico de bajo costo para contextos de recursos limitados**: automatizar la preparación y el análisis de frotis de sangre (smears) para facilitar el diagnóstico de enfermedades como el dengue, donde el conteo manual de células al microscopio es lento y depende de personal entrenado.

## Objetivo

Entrenar un modelo de detección de objetos capaz de identificar y contar automáticamente, a partir de una foto de un frotis de sangre en monocapa, tres tipos de elementos:

- Glóbulos rojos (GR)
- Glóbulos blancos (GB)
- Plaquetas (PQT)

## Pipeline

El proyecto se organiza en tres etapas secuenciales:

1. **[`01_merge_dataset.ipynb`](./01_merge_dataset.ipynb)** — Creación del dataset: anotación manual de imágenes de frotis en [Roboflow](https://roboflow.com/), generando tres versiones del dataset con distintas variaciones/aumentaciones, y unificación en un único dataset combinado (cuidando no duplicar imágenes repetidas entre versiones).
2. **[`02_entrenamiento.ipynb`](./02_entrenamiento.ipynb)** — Entrenamiento de un modelo **YOLOv8** sobre el dataset combinado, con evaluación de precision/recall por clase.
3. **[`03_deteccion.ipynb`](./03_deteccion.ipynb)** — Pipeline de inferencia: al subir una imagen nueva, el modelo ya entrenado detecta y cuenta automáticamente cada tipo de célula presente.

## Herramientas

Python · YOLOv8 (Ultralytics) · Roboflow (anotación y gestión de datasets) · OpenCV

## Estado

Modelo funcional: dado un frotis nuevo, produce detección y conteo automático por clase. Próximos pasos posibles: ampliar el dataset con más muestras e integrar el pipeline con el sistema de preparación automatizada de frotis (impresión 3D + microfluídica) del proyecto de laboratorio en curso.
