# 📈 HR Analytics – Predicción de Promociones de Empleados

Este proyecto final consiste en el desarrollo de un flujo completo de Ciencia de Datos para resolver un problema estratégico de Recursos Humanos: predecir qué empleados son candidatos idóneos para una promoción laboral. Se abordan etapas que van desde el Análisis Exploratorio de Datos (EDA) hasta el modelado predictivo de alta seguridad orientado a la mitigación de riesgos y optimización de presupuestos.

---

## 🎯 GUÍA DE REVISIÓN PARA RECLUTADORES (Lectura Rápida)

Si eres Reclutador, Gestor de Talento Humano o Tomador de Decisiones, puedes auditar todo nuestro trabajo de inmediato con un solo clic, sin instalar programas ni lidiar con bloqueos de carga:

* 👁️ **[HAGA CLIC AQUÍ PARA ABRIR EL CÓDIGO Y LAS GRÁFICAS COMPILADAS](https://nbviewer.org/github/R000123/PORTAFOLIO-PORTFOLIO/blob/a65ea643ba9c9b1210c3fa2111b7437d4bb91f3d/Hr_analytics%20modelo%20predictivo/HR_Analytics_Proyecto_Final_Completo%20%282%29.ipynb)**
* 📊 **¿Qué ver en el enlace?:** Al presionar el botón azul de arriba, se abrirá tu navegador mostrando de forma consecutiva todas nuestras celdas de Python y, **justo debajo de cada línea de código, verás impresas las tablas reales y los gráficos de Seaborn a color** (incluyendo la matriz de confusión azul y el gráfico de barras de importancia).
* 📄 **Entregable de Negocio:** En esta misma carpeta del repositorio puedes abrir directamente el archivo `ranking_promociones.csv` para auditar el producto final: un listado ordenado con las probabilidades exactas para optimizar planes de sucesión inmediatos.

---

## 👥 Integrantes (WE Education)
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
* **Pandas & NumPy:** Carga, preprocesamiento y manipulación de estructuras de datos.
* **Matplotlib & Seaborn:** Creación de gráficos y mapas de calor.
* **Scikit-Learn (Sklearn):** Ingeniería de características, división de muestras y modelado predictivo.

---

## 📊 Fases del Proyecto

### 1. Análisis Exploratorio de Datos (EDA) e Insights de Negocio
Se analizaron las variables demográficas y de rendimiento del dataset (`hr_analytics.csv`), destacando los siguientes hallazgos:
* **Desbalance de Clases:** El volumen de empleados promovidos es significativamente bajo (solo ~8.5% de la plantilla), lo que representa un reto analítico clásico.
* **Mérito vs. Antigüedad:** El cumplimiento de metas (KPI > 80%), la obtención de premios (`awards_won?`) y altas calificaciones de capacitación son los factores de mayor correlación con un ascenso. Variables tradicionales como la edad o la antigüedad no reflejan un impacto directo, demostrando meritocracia corporativa.

### 2. Entrenamiento del Modelo Orientado a Negocio (Control de Pérdidas)
Dado que el objetivo estratégico de la organización es evitar pérdidas financieras causadas por falsos positivos (ascender incorrectamente a perfiles no óptimos que generen gastos innecesarios), se diseñó un modelo ultra estricto:
* **Distribución Real:** Se entrenó directamente sobre la distribución real de los datos, evitando sobremuestreos artificiales.
* **Optimización:** Se utilizó `GridSearchCV` configurando el parámetro `scoring='precision'` para penalizar drásticamente los falsos positivos en el negocio.

### 3. Evaluación Definitiva del Modelo
El clasificador final basado en Random Forest arrojó resultados de alta seguridad analítica en el conjunto de prueba:
* **Accuracy Global:** **93.3%**, demostrando un dominio robusto sobre el comportamiento histórico de la plantilla.
* **Precisión de Promoción (Clase 1):** **94.4%**. Cada recomendación de ascenso emitida por el algoritmo cuenta con una certeza casi absoluta, garantizando que el capital se invierta únicamente en perfiles ganadores.
* **Recall (Clase 1):** **23.4%**, una consecuencia directa de establecer un filtro corporativo altamente riguroso para blindar la rentabilidad. El bajo F1-Score resultante (0.38) está plenamente justificado por dar prioridad absoluta a la precisión.

### 4. Importancia de las Variables (Feature Importance)
El análisis del peso de cada variable dentro de las decisiones del bosque aleatorio (*Random Forest*) arrojó que:
* **Factores Dominantes:** El puntaje promedio de capacitación (`avg_training_score` con 50.0%) y el cumplimiento de KPIs superiores al 80% (`KPIs_met >80%` con 15.2%) dominan las decisiones de ascenso.
* **Impacto Comercial:** Ambos factores suman **más del 65% de toda la importancia del modelo**, consolidando una cultura empresarial orientada netamente al rendimiento y la capacitación técnica.

---

## 🚀 GUÍA TÉCNICA DE CLONACIÓN Y EJECUCIÓN (Para Programadores)

Si deseas descargar el repositorio completo para compilar, auditar y ejecutar este modelo predictivo de forma local en tu computadora, sigue estas instrucciones:

### Paso 1: Clonar el Repositorio
Abre tu terminal y ejecuta:
```bash
git clone https://github.com
```

### Paso 2: Navegar a la carpeta del proyecto
```bash
cd "PORTAFOLIO-PORTFOLIO/Hr_analytics modelo predictivo"
```

### Paso 3: Abrir y Recompilar el Código
1. Abre tu entorno local preferido (como **Visual Studio Code** o **Jupyter Lab**).
2. Abre el archivo de código fuente: `HR_Analytics_Proyecto_Final_Completo (2).ipynb`.
3. Selecciona tu Kernel de Python y haz clic en **"Run All"** (Ejecutar todo) para limpiar la memoria caché, volver a compilar las celdas matemáticas desde cero y regenerar los gráficos estadísticos de manera dinámica en tu propia máquina.
