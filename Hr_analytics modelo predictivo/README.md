# 📈 HR Analytics – Predicción de Promociones de Empleados

Este proyecto final consiste en el desarrollo de un flujo completo de Ciencia de Datos para resolver un problema estratégico de Recursos Humanos: predecir qué empleados son candidatos idóneos para una promoción laboral. Se abordan etapas que van desde el Análisis Exploratorio de Datos (EDA) hasta el modelado predictivo de alta seguridad orientado a la mitigación de riesgos y optimización de presupuestos.

---

## 👥 Integrantes
* Asencios Huaman, Roberth William
* Espinoza Celestino, María del Pilar
* García Melgar, Carlos Javier
* Huaman Pio Guillermo, Fabrizio
* Montes Lobo, Erick Andrés
* Romero Estremadoyro, Jean Paul
* Sarmiento, Alonso

---

## 🛠️ Tecnologías y Librerías Utilizadas
* **Python:** Lenguaje base del desarrollo.
* **Pandas & NumPy:** Carga, preprocesamiento y manipulación de estructuras matriciales.
* **Matplotlib & Seaborn:** Creación de gráficos y visualización de mapas de calor para correlación.
* **Scikit-Learn (Sklearn):** Ingeniería de características, escalado de datos, división de muestras y entrenamiento de modelos.

---

## 📊 Fases del Proyecto

### 1. Análisis Exploratorio de Datos (EDA) e Insights de Negocio
Se analizaron las variables demográficas y de rendimiento del dataset (`hr_analytics.csv`), destacando los siguientes hallazgos:
* **Desbalance de Clases:** El volumen de empleados promovidos es significativamente bajo (solo ~8.5% de la plantilla), lo que representa un reto analítico clásico.
* **Mérito vs. Antigüedad:** El cumplimiento de metas (KPI > 80%), la obtención de premios (`awards_won?`) y altas calificaciones de capacitación son los factores de mayor correlación con un ascenso. Variables como la edad o la antigüedad no reflejan un impacto directo, demostrando meritocracia.
* **Educación:** La gran mayoría de la plantilla posee grado de Bachiller, siendo también la categoría con mayor volumen de ascensos.

### 2. Preprocesamiento e Ingeniería de Características
Para garantizar la calidad de los datos de entrada al modelo, se implementaron las siguientes técnicas:
* **Tratamiento de Nulos:** Imputación por mediana para variables numéricas y por frecuencia para variables categóricas (como Educación).
* **Codificación (Encoding):** Mapeo ordinal para el nivel educativo (`education`) y codificación One-Hot (`get_dummies`) para el resto de variables cualitativas.
* **Manejo de Outliers:** Aplicación de técnicas de truncado (*clipping*) utilizando los percentiles 5 y 99 en variables de servicio, edad y puntajes.
* **Escalado:** Transformación de características numéricas al rango $0, 1$ mediante `MinMaxScaler`.

### 3. Entrenamiento del Modelo Orientado a Negocio (Control de Pérdidas)
Dado que el objetivo estratégico de la organización es evitar pérdidas financieras causadas por falsos positivos (ascender incorrectamente a perfiles no óptimos que generen gastos de capacitación o fugas de capital), se diseñó un modelo ultra estricto:
* **Distribución Real:** Se entrenó directamente sobre la distribución real y orgánica de los datos, evitando sobremuestreos artificiales que distorsionen la realidad operativa.
* **Optimización en Cuadrícula:** Se utilizó `GridSearchCV` ($k=5$) evaluando combinaciones de hiperparámetros para un `RandomForestClassifier`.
* **Métrica Clave:** Se configuró el parámetro `scoring='precision'` para penalizar drásticamente los falsos positivos en el negocio.

### 4. Evaluación Definitiva del Modelo
El clasificador final basado en Random Forest arrojó resultados de alta seguridad analítica en el conjunto de prueba:
* **Accuracy Global:** **93.3%**, demostrando un dominio robusto sobre el comportamiento histórico de la plantilla.
* **Precisión de Promoción (Clase 1):** **94.4%**. Cada recomendación de ascenso emitida por el algoritmo cuenta con una certeza casi absoluta, garantizando que el capital se invierta únicamente en perfiles ganadores.
* **Recall (Clase 1):** **23.4%**, una consecuencia directa e idónea de establecer un filtro corporativo altamente riguroso y selectivo para blindar la rentabilidad.

### 5. Importancia de las Variables (Feature Importance)
El análisis del peso de cada variable dentro de las decisiones del bosque aleatorio (*Random Forest*) arrojó que:
* **Factores Dominantes:** El puntaje promedio de capacitación (`avg_training_score` con 0.330) y el cumplimiento de KPIs superiores al 80% (`KPIs_met >80%` con 0.260) dominan las decisiones de ascenso.
* **Impacto Comercial:** Ambos factores suman **casi el 60% de toda la importancia del modelo**, lo que consolida una cultura empresarial orientada netamente al rendimiento y la capacitación técnica.

---

## 🎯 Entregable Final de Negocio
Como valor agregado para el área de Talento y Recursos Humanos, el modelo calcula la probabilidad matemática de ascenso para cada colaborador. Este listado se exporta automáticamente en orden descendente al archivo:
* 📄 **`ranking_promociones.csv`**

Este archivo permite a los tomadores de decisiones identificar de forma inmediata a los mejores perfiles de la organización para planes de sucesión o ascensos inmediatos con un riesgo de pérdida minimizado al mínimo.

---

## 🚀 Cómo Ejecutar el Proyecto
1. Asegúrate de tener instalado un entorno de Python o usa **Google Colab**.
2. Clona este repositorio o descarga la carpeta del proyecto de manera local.
3. Recuerda guardar tus datasets de datos (`hr_analytics.csv` u `olympics.zip`) en la misma raíz que el cuaderno de Jupyter.
4. Abre el archivo `.ipynb` y ejecuta todas las celdas en orden secuencial.
