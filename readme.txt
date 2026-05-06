# Proyecto: Análisis de Clientes ConnectaTel

## 📌 Objetivo del Proyecto

El objetivo de este proyecto es analizar el comportamiento de los clientes de ConnectaTel, una empresa de telecomunicaciones en Latinoamérica, utilizando información histórica registrada hasta el año 2024.

A través del análisis de datos se busca:

- identificar patrones de consumo;
- detectar problemas de calidad en los datos;
- analizar distribuciones y valores atípicos;
- segmentar clientes según su comportamiento;
- generar insights accionables para el negocio.

Este análisis permite comprender mejor a los usuarios y apoyar la toma de decisiones relacionadas con retención, segmentación y mejora de planes.

---

## 📂 Datasets Utilizados

El proyecto utiliza tres datasets principales:

### `plans.csv`
Contiene información sobre los planes ofrecidos por ConnectaTel:
- precio del plan
- minutos incluidos
- GB incluidos
- costo por excedente

### `users_latam.csv`
Contiene información de los clientes:
- identificador de usuario
- edad
- ciudad
- fecha de registro
- plan contratado
- información de cancelación (churn)

### `usage.csv`
Contiene el detalle histórico del uso de servicios:
- llamadas
- mensajes
- duración de llamadas
- fechas de uso

---

## 🔎 Etapas del Análisis

### 1. Carga y exploración de datos
- carga de datasets;
- revisión de estructura;
- análisis de columnas y tipos de datos.

### 2. Calidad de datos
- detección de valores nulos;
- identificación de sentinels;
- validación de fechas;
- revisión de inconsistencias.

### 3. Limpieza de datos
- reemplazo de sentinels;
- corrección de fechas inválidas;
- tratamiento de valores nulos.

### 4. Estadísticas y agregaciones
- creación de métricas por usuario;
- cálculo de llamadas, mensajes y minutos consumidos;
- combinación de datasets.

### 5. Visualización y detección de outliers
- histogramas;
- boxplots;
- análisis de distribuciones;
- detección de valores extremos usando IQR.

### 6. Segmentación de clientes
- clasificación por nivel de uso;
- agrupación por edad;
- análisis de comportamiento de clientes.

### 7. Insights ejecutivos
- interpretación de resultados;
- recomendaciones comerciales;
- oportunidades de mejora para ConnectaTel.

---

## ▶️ Cómo Ejecutar el Notebook

### Opción 1: Google Colab
1. Abrir Google Colab:
   https://colab.research.google.com/

2. Subir el notebook `.ipynb`.

3. Subir los datasets:
   - `plans.csv`
   - `users_latam.csv`
   - `usage.csv`

4. Ejecutar las celdas en orden.

---

### Opción 2: Jupyter Notebook
1. Instalar Python y Jupyter Notebook.
2. Instalar las librerías necesarias:
```bash
pip install pandas matplotlib seaborn numpy