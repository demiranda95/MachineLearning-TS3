# 📊 Machine Learning – Trabajo Sumativo Unidad 3

## 📌 Descripción del Proyecto
Este repositorio contiene el desarrollo del **Trabajo Sumativo Unidad 3** de la asignatura *Machine Learning*, dando continuidad al trabajo realizado en las Unidades 1 y 2 sobre el caso **Walmart Sales Forecasting**.

En esta etapa, el enfoque se centra en la aplicación de técnicas de **aprendizaje no supervisado (clustering)** para identificar patrones y segmentaciones dentro del dataset, utilizando variables económicas, temporales, promocionales y características de las tiendas.

---

## 🎯 Objetivo
Aplicar y comparar distintos algoritmos de clustering para identificar grupos de observaciones similares dentro del dataset Walmart Sales Forecasting.

El objetivo principal es:
- Detectar estructuras internas en los datos
- Comparar algoritmos de clustering
- Evaluar el impacto del uso de PCA
- Analizar métricas de cohesión y separación
- Interpretar clusters desde una perspectiva de negocio

---

## 🧠 Modelos Implementados
Se ejecutaron y compararon los siguientes algoritmos:

### 🔹 Modelos basados en distancia
- MiniBatchKMeans
- BIRCH
- Agglomerative Clustering

### 🔹 Modelos basados en densidad
- DBSCAN
- OPTICS

---

## 🧪 Escenarios Evaluados
Cada modelo fue evaluado en dos escenarios:

- ✅ Dataset escalado original (**sin PCA**)
- ✅ Dataset reducido mediante **PCA**

En total:
- **5 modelos**
- **2 escenarios**
- **10 corridas evaluadas**

---

## 📊 Métricas de Evaluación
Se utilizaron métricas internas de clustering:

- Silhouette Score ⭐
- Davies-Bouldin Index
- Calinski-Harabasz Index

Además, se evaluó:
- Cantidad de clusters generados
- Observaciones consideradas como ruido (`-1`)

---

## ⚙️ Procesamiento y Preparación de Datos
El pipeline desarrollado incluye:

1. Integración de `train.csv`, `features.csv` y `stores.csv`
2. Transformación de fechas (`Year`, `Month`, `Week`)
3. Tratamiento de valores nulos en variables MarkDown
4. Creación de variables binarias promocionales
5. Exclusión de variables identificadoras
6. Escalamiento mediante `StandardScaler`
7. Reducción de dimensionalidad mediante PCA

---

## 📉 PCA (Principal Component Analysis)
Se aplicó PCA para reducir dimensionalidad y facilitar el clustering.

Resultados:
- 19 variables originales
- 9 componentes principales
- ~90% de varianza acumulada conservada

Beneficios observados:
- Reducción de ruido
- Mejor separación visual
- Menor costo computacional
- Mejora en métricas de clustering

---

## 📈 Resultados Principales
### 🥇 Mejor Silhouette
- **DBSCAN con PCA**
- Silhouette ≈ **0.4469**

### ⚖️ Mejor equilibrio general
- **BIRCH con PCA**
- **Agglomerative con PCA**

### 🚀 Modelo operativo seleccionado
- **MiniBatchKMeans con PCA**

Seleccionado debido a:
- Escalabilidad
- Estabilidad
- Facilidad de interpretación
- Buen desempeño computacional

---

## 🧩 Interpretación de Clusters
El análisis permitió identificar distintos contextos comerciales:

| Cluster | Interpretación |
|---|---|
| Cluster 0 | Semanas sin promociones relevantes |
| Cluster 1 | Alta actividad promocional |
| Cluster 2 | Comportamiento intermedio o estacional |

Las variables MarkDown fueron uno de los factores más relevantes en la segmentación obtenida.

---

## ⚠️ Consideraciones Computacionales
Debido al alto costo computacional de algunos algoritmos:

- Dataset maestro: **100.000 registros**
- Benchmarking: muestra de **10.000 registros**

Esto permitió mantener tiempos de ejecución razonables sin perder representatividad del análisis.

---

## 🗂️ Estructura del Proyecto
```bash
📁 MachineLearning-TS3
│
├── Trabajo_Sumativo_3_Machine_Learning.ipynb
└── README.md
