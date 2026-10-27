# Segmentación de Clientes y Diseño de Campañas de Marketing

Proyecto de segmentación de clientes de un negocio tipo e-commerce usando
técnicas de *clustering* no supervisado sobre el dataset **Mall Customers**
(200 clientes: género, edad, ingreso anual y puntaje de gasto).

El objetivo es identificar grupos de clientes con comportamiento de compra
similar y traducirlos en perfiles y estrategias de marketing concretas.

## Estructura del proyecto

```
├── Segmentacion_de_clientes_2.0.ipynb   # Notebook principal (versión 2.0)
├── Mall_Customers.csv                   # Dataset
├── requirements.txt
└── README.md
```

## Versión 2.0 (actual)

1. **Exploración y limpieza**: traducción de variables al español, revisión de
   nulos y duplicados, estadísticas por género.
2. **Análisis exploratorio**: histogramas, boxplots, distribución por género,
   gráficos de dispersión 2D y 3D, detección de outliers (IQR) y mapa de calor
   de correlaciones.
3. **Preparación**: normalización de variables numéricas (`MinMaxScaler` /
   `StandardScaler`).
4. **Modelos de clustering comparados**:
   - K-Means (método del codo para elegir *k*)
   - Clustering jerárquico aglomerativo
   - Bisecting K-Means
   - DBSCAN
   - Mean Shift
   - Gaussian Mixture Models (GMM)
5. **Evaluación** con Silhouette Score, Davies–Bouldin y Calinski–Harabasz.
   K-Means obtuvo los mejores resultados.
6. **Perfiles y estrategias de marketing** para cada segmento.

### Segmentos obtenidos (K-Means, k = 5)

| Cluster | Perfil | Edad | Ingreso anual (k$) | Puntaje de gasto | Clientes |
|---|---|---|---|---|---|
| 0 | Adultos de alto ingreso y bajo gasto | 44.0 | 90.1 | 17.9 | 30 |
| 1 | Jóvenes de bajo ingreso y alto gasto | 25.5 | 26.3 | 78.6 | 23 |
| 2 | Adultos de mayor edad con gasto moderado | 55.6 | 48.5 | 41.8 | 58 |
| 3 | Adultos jóvenes de alto ingreso y alto gasto | 32.9 | 86.1 | 81.5 | 40 |
| 4 | Jóvenes de ingreso y gasto moderados | 27.1 | 52.0 | 41.0 | 49 |

Al ejecutarse, el notebook genera un CSV por segmento
(`clientes_kmeans_perfil_<n>.csv`) y un Excel `clientes_con_perfiles.xlsx`
con el detalle de clientes y el resumen de segmentos.

## Cómo ejecutarlo

```bash
pip install -r requirements.txt
jupyter notebook Segmentacion_de_clientes_2.0.ipynb
```

También puede abrirse en Google Colab subiendo el notebook junto con
`Mall_Customers.csv`.

## Historial

Este repositorio unifica tres repositorios previos. Las versiones anteriores
(v1 enfocada en e-commerce y v2 enfocada solo en clientas) fueron reemplazadas
por la versión 2.0 y se conservan únicamente en el historial de git.
