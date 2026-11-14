# Práctica 3: Machine Learning — Comparativa de clasificadores

Instituto Politécnico Nacional · Escuela Superior de Cómputo · Inteligencia Artificial

Comparación de seis clasificadores sobre un dataset sintético con ruido estructurado y el dataset de benchmark Wine, con validación Hold Out 70/30 y K-Fold (k = 5).

## Integrantes y responsabilidades

| Integrante | Nombre | Clasificadores | Notebook |
|---|---|---|---|
| 1 | Arenas Garduño Dafne Yazinari | Distancia Mínima (desde cero) y MLP (Scikit-learn) | `practica_clasificadores_integrante1.ipynb` |
| 2 | Martínez Rodríguez Karen Paola | 1-NN (desde cero) y SVM (Scikit-learn) | `practica_clasificadores_integrante2.ipynb` |
| 3 | Cruz Pinzón Jorge | K-NN (desde cero) y Naïve Bayes (Scikit-learn) | `practica_clasificadores_integrante3.ipynb` |

## Contenido del repositorio

| Archivo | Descripción |
|---|---|
| `practica_clasificadores_integrante1.ipynb` | Generación del dataset sintético, Distancia Mínima, MLP y optimización del MLP |
| `practica_clasificadores_integrante2.ipynb` | 1-NN, SVM, optimización de SVM (kernel, C y gamma) y tiempos de ejecución |
| `practica_clasificadores_integrante3.ipynb` | Análisis exploratorio, normalización, K-NN, Naïve Bayes, optimización de K-NN, complejidad temporal e integración de los seis clasificadores |
| `wine_preparado.csv` | Dataset Wine sin normalizar, con las columnas `holdout` y `fold` que fijan las particiones del equipo |
| `sintetico_preparado.csv` | Dataset sintético sin normalizar, con las mismas columnas de partición |
| `resultados_equipo.csv` | Métricas y tiempos de los seis clasificadores (2 datasets × 2 validaciones) |
| `resultados_integrante3.csv` | Métricas y tiempos de K-NN y Naïve Bayes |
| `requirements.txt` | Versiones de las bibliotecas utilizadas |

## Datasets

- **Sintético:** 1,000 muestras, 6 características y 3 clases, generado con `make_classification`. Incluye 5 % de etiquetas alteradas y ruido correlacionado sumado a las dos primeras características (ruido estructurado).
- **Wine:** 178 muestras, 13 características numéricas reales y 3 clases (UCI Machine Learning Repository, disponible en Scikit-learn).

## Protocolo de evaluación

- Semilla común: 42.
- Hold Out 70/30 estratificado y K-Fold estratificado con 5 pliegues.
- Escalado Z-Score ajustado únicamente con los datos de entrenamiento de cada partición.
- Métricas: exactitud, precisión, recall y F1 (promedio macro), y tiempos de entrenamiento y predicción.
- Los tres integrantes usan las mismas particiones; la verificación está en la sección 9 del notebook del Integrante 3.

## Resultados (exactitud con K-Fold, parámetros base)

| Clasificador | Wine | Sintético |
|---|---|---|
| Distancia Mínima | 97.75 % | 70.20 % |
| 1-NN | 95.51 % | 79.60 % |
| K-NN (k = 5) | 97.17 % | 85.60 % |
| Naïve Bayes | 97.19 % | 75.30 % |
| SVM | 98.33 % | 84.90 % |
| MLP | 97.76 % | 87.40 % |

## Cómo ejecutar

1. Abrir el notebook en Google Colab (o en Jupyter con las bibliotecas de `requirements.txt`).
2. Seleccionar **Entorno de ejecución → Ejecutar todas**.

Los notebooks de los Integrantes 2 y 3 leen los archivos CSV directamente desde este repositorio, por lo que no es necesario descargarlos.
