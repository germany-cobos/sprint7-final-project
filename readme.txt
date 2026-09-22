# 📊 Análisis de Clientes ConnectaTel

Análisis de datos de una empresa de telecomunicaciones en Latinoamérica para comprender el comportamiento de sus clientes, identificar problemas de calidad en los datos, detectar patrones de consumo, segmentar usuarios y generar recomendaciones comerciales.

## 🎯 Objetivo del proyecto

El objetivo es analizar información histórica de ConnectaTel registrada hasta 2024 para responder preguntas relacionadas con:

* ¿Cómo utilizan los clientes los servicios de telecomunicaciones?
* ¿Qué problemas de calidad existen en los datos?
* ¿Qué patrones de consumo pueden identificarse?
* ¿Qué segmentos de clientes existen?
* ¿Qué oportunidades comerciales pueden identificarse a partir del comportamiento de los usuarios?

Los resultados buscan apoyar decisiones relacionadas con **segmentación, retención de clientes y diseño de planes**.

---

## 📂 Datos utilizados

El proyecto utiliza tres datasets principales:

### `plans.csv`

Contiene información sobre los planes ofrecidos por ConnectaTel:

* Precio del plan
* Minutos incluidos
* GB incluidos
* Costo por excedente

### `users_latam.csv`

Contiene información de los clientes:

* ID de usuario
* Edad
* Ciudad
* Fecha de registro
* Plan contratado
* Información de cancelación (churn)

### `usage.csv`

Contiene información histórica sobre el uso de los servicios:

* Llamadas
* Mensajes
* Duración de llamadas
* Fechas de uso

---

## 🛠️ Herramientas

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Jupyter Notebook

---

## 🔎 Metodología

El análisis se realizó en varias etapas.

### 1. Exploración de datos

Se revisó la estructura de los datasets, tipos de datos, columnas disponibles y calidad general de la información.

### 2. Calidad y limpieza de datos

Se identificaron:

* Valores nulos.
* Valores sentinels.
* Fechas fuera del rango de análisis.
* Posibles inconsistencias.

Entre los principales problemas encontrados:

| Variable     | Problema identificado   |
| ------------ | ----------------------- |
| `city`       | ~11.7% de valores nulos |
| `churn_date` | ~88% de valores nulos   |
| `duration`   | ~55% de valores nulos   |
| `length`     | ~44% de valores nulos   |

Los valores faltantes en `duration` y `length` se interpretaron considerando el tipo de uso registrado: las llamadas utilizan `duration`, mientras que los mensajes utilizan `length`.

También se identificaron valores sentinels como `-999` en `age` y `"?"` en `city`, que fueron tratados durante el proceso de limpieza.

### 3. Creación de métricas

Se construyeron métricas agregadas por usuario para analizar:

* Cantidad de llamadas.
* Cantidad de mensajes.
* Minutos totales de llamadas.
* Comportamiento general de consumo.

### 4. Análisis de distribuciones y outliers

Se utilizaron histogramas y boxplots para estudiar la distribución de las variables de consumo y detectar valores extremos mediante el método IQR.

### 5. Segmentación de clientes

Se crearon dos tipos principales de segmentos:

**Por nivel de uso**

* Bajo uso
* Uso medio
* Alto uso

**Por edad**

* Joven
* Adulto
* Adulto Mayor

---

# 📈 Principales hallazgos

## 1. La base de clientes presenta diferentes niveles de consumo

El análisis identificó tres grupos principales según el nivel de uso:

* **Bajo uso:** usuarios con pocas llamadas y pocos mensajes.
* **Uso medio:** clientes con consumo moderado.
* **Alto uso:** usuarios con niveles elevados de llamadas y mensajes.

Esta segmentación permite diferenciar clientes según la intensidad con la que utilizan los servicios de ConnectaTel.

### 💡 Insight de negocio

Los clientes de alto uso representan un segmento relevante porque concentran un mayor consumo de los servicios y pueden representar una oportunidad para estrategias comerciales y de retención.

---

## 2. Los patrones de consumo varían entre los clientes

Las distribuciones de llamadas, mensajes y minutos presentan **sesgo hacia la derecha**, debido a la existencia de usuarios con niveles de consumo considerablemente mayores que la mayoría.

En particular:

* `cant_mensajes` presenta usuarios con cantidades de mensajes muy elevadas.
* `cant_llamadas` presenta clientes con un número inusualmente alto de llamadas.
* `cant_minutos_llamada` presenta varios valores extremos y una fuerte asimetría positiva.

### 💡 Insight de negocio

Estos usuarios intensivos pueden representar necesidades de comunicación diferentes a las del cliente promedio y podrían requerir una oferta de servicios más adecuada a su nivel de consumo.

---

## 3. Los outliers representan comportamiento real del negocio

Los valores extremos encontrados en mensajes, llamadas y minutos no fueron eliminados automáticamente.

Se conservaron porque representan usuarios reales con **consumo intensivo** y pueden proporcionar información útil para la segmentación y el diseño de productos.

### 💡 Insight de negocio

En lugar de considerar estos valores únicamente como anomalías, ConnectaTel puede utilizarlos para identificar clientes de alto consumo, evaluar oportunidades de monetización y detectar posibles necesidades no cubiertas por los planes actuales.

---

## 4. La edad permite complementar la segmentación

Los clientes fueron agrupados en:

* Jóvenes
* Adultos
* Adultos mayores

La distribución no muestra una concentración extrema en un único grupo etario.

El análisis también sugiere diferencias en el comportamiento: los clientes de mayor edad tienden a mostrar patrones de consumo más estables, mientras que los usuarios más jóvenes presentan mayor variabilidad en llamadas y mensajes.

### 💡 Insight de negocio

La segmentación por edad puede complementar la segmentación por uso y ayudar a diseñar campañas y beneficios más específicos para diferentes perfiles de clientes.

---

# 💼 Insights ejecutivos

A partir del análisis, se pueden destacar cuatro conclusiones principales:

### 1. ConnectaTel tiene una base de clientes heterogénea

Los usuarios presentan diferentes niveles de consumo, por lo que una estrategia única de planes puede no responder de la misma manera a todas sus necesidades.

### 2. Existe un segmento de usuarios intensivos

Los clientes con altos niveles de llamadas, mensajes y minutos representan una oportunidad para desarrollar productos y estrategias comerciales específicas.

### 3. Los datos de consumo permiten construir segmentos accionables

La combinación de variables de uso y edad permite crear perfiles de clientes que pueden utilizarse como base para estrategias comerciales y de retención.

### 4. La calidad de los datos debe considerarse antes de tomar decisiones

La presencia de valores faltantes y sentinels demuestra la importancia de mantener procesos de limpieza y validación de datos antes de utilizarlos para análisis comerciales.

---

#
