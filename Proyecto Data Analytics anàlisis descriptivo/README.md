# 🇵🇪 Análisis Histórico de la Participación de Perú en los Juegos Olímpicos

Este proyecto realiza un análisis exploratorio de datos (EDA) centrado en la participación histórica de las delegaciones peruanas en los Juegos Olímpicos, analizando disciplinas, deportistas destacados y profundizando en el perfil físico de las medallistas olímpicas de voleibol femenino.

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
El análisis se desarrolló en **Python** utilizando un Jupyter Notebook y las siguientes librerías de ciencia de datos:
* **Pandas:** Para la carga, manipulación y limpieza del dataset.
* **NumPy:** Para soporte de operaciones matriciales y cálculo numérico.
* **Seaborn:** Para la creación de gráficos estadísticos avanzados (Histogramas y Boxplots).
* **Matplotlib:** Para la personalización de figuras y visualizaciones de datos.

---

## 📊 Principales Hallazgos del Análisis

### 1. Panorama General de Perú en los JJOO
* **Diversidad:** A nivel global el dataset registra 66 disciplinas. Perú ha competido históricamente en **26 disciplinas distintas**.
* **Atletas:** Se registran **353 deportistas peruanos** únicos a lo largo de la historia de las olimpiadas.
* **Medallero por Jugador:** En el registro por atletas (conteo individual en deportes de equipo), el país acumula un conteo histórico reflejado principalmente en medallas de plata y oro.
* **Disciplinas Laureadas:** El éxito olímpico peruano se concentra fuertemente en dos deportes históricos: **Voleibol** y **Tiro**.

### 2. Perfil Físico de las Medallistas de Voleibol Femenino
Al profundizar en el equipo de voleibol femenino (medallistas de plata), se obtuvieron los siguientes promedios biofísicos:
* **Edad Promedio:** 22 años (con una tendencia de concentración máxima entre los 23 y 24 años).
* **Estatura Promedio:** 176 cm.
* **Peso Promedio:** 65 kg.

### 3. Análisis Estadístico Visual
* **Distribución de Altura:** El gráfico de caja (*Boxplot*) revela que la mediana de altura ronda los 175 cm. Se identificaron valores atípicos (*outliers*) superiores que alcanzan los 185 cm y 195 cm.
* **Distribución de Peso:** Los datos de peso son homogéneos y estables. La tendencia se sitúa en torno a los 70 kg sin presencia de valores atípicos significativos.

---

## 🚀 Cómo Ejecutar el Proyecto
1. Asegúrate de tener instalado un entorno de Python o usa **Google Colab**.
2. Clona este repositorio o descarga la carpeta del proyecto de manera local.
3. Coloca el archivo de datos `olympics.csv` en la misma raíz que el cuaderno de Jupyter.
4. Abre el archivo `.ipynb` y ejecuta todas las celdas en orden secuencial.
