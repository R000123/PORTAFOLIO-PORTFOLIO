# 🏦 Loan Approval Analysis / Análisis de Aprobación de Préstamos

> 🌐 [English](#english) | [Español](#español)

---

<a name="english"></a>
## 🇬🇧 English

### Context
Financial institutions receive many mortgage loan applications and must decide which ones to approve. This project analyzes **592 loan applications** (614 originally, after cleaning) that include applicant profile data (gender, marital status, dependents, education, self-employment), financial capacity (applicant and co-applicant income), loan conditions (amount and term), credit history and property area. The target variable is the final decision: approved or rejected.

### Objectives
**General objective:** identify which applicant and loan factors influence loan approval, and evaluate whether a self-proposed ratio adds explanatory value.

**Specific objectives:**
1. Clean the data and document the treatment of missing values and data types (614 → 592 records).
2. Describe the profile of approved vs. rejected applications (69.4% vs. 30.6%).
3. Measure the relationship between each variable (credit history, dependents, co-applicant, property area, income) and approval.
4. Build and test a new variable not present in the original dataset: the **Loan-to-Income Ratio** = Loan Amount ÷ Total Income (applicant + co-applicant).
5. Compare three models (Logistic Regression, Random Forest, XGBoost) and tune the decision threshold.
6. Identify the most important variables and translate them into useful credit-risk criteria.

### Main findings
- **Credit history is the dominant factor:** applicants with a positive history were approved 80.1% of the time, versus only 8.2% for those without it. It is also the most important variable in both Random Forest and XGBoost.
- **Property area matters:** approval was highest in Semiurban areas (76.8%), followed by Urban (67.5%) and Rural (61.8%).
- **Loan-to-Income Ratio hypothesis was not supported:** I expected this ratio to explain approval better than income alone, but the median ratio is practically the same for approved (0.0243) and rejected (0.0238) applications (Mann-Whitney p = 0.58). Total income also shows no clear difference between groups. Its high importance score in tree-based models should not be read as real predictive signal, since continuous variables tend to inflate that metric. Testing a hypothesis and finding it is not supported is still a valid result.
- **Co-applicant shows only a slight trend:** 72.2% approval with a co-applicant vs. 65.9% without, but the difference is not statistically significant (chi-square p ≈ 0.12).

### Model performance
| Model | Accuracy (test set, threshold 0.5) |
|---|---|
| Logistic Regression | 78.2% |
| Random Forest | 79.0% |
| XGBoost | 74.8% |

With the decision threshold set to 0.40, Random Forest reaches ~79.8% accuracy. It detects nearly all approved loans (recall 98%) but only 39% of rejected ones. For a lender, this matters: approving a risky loan is usually costlier than rejecting a good one, so a real deployment would prioritize detecting rejections.

### Limitations
- Small sample (592 rows) and a single train/test split of 119 records.
- The threshold was compared on the same test set used for evaluation, which can make results slightly optimistic. Cross-validation or a separate validation set would be the next step.
- Accuracy alone is misleading with imbalanced classes; recall of the "Rejected" class is the more relevant metric.

### Tools
- **Python:** Pandas, NumPy, Matplotlib, Seaborn
- **Machine Learning:** Scikit-learn (Logistic Regression, Random Forest), XGBoost

### Dataset
Dataset originally obtained from [Kaggle](https://www.kaggle.com/) and edited for this project.

---

<a name="español"></a>
## 🇵🇪 Español

### Contexto
Las entidades financieras reciben muchas solicitudes de préstamo hipotecario y deben decidir cuáles aprobar. Este proyecto analiza **592 solicitudes de préstamo** (614 originales, tras la limpieza) que incluyen datos del perfil del solicitante (género, estado civil, dependientes, educación, empleo independiente), su capacidad económica (ingreso del solicitante y del co-solicitante), las condiciones del préstamo (monto y plazo), el historial crediticio y el área de la propiedad. La variable a explicar es la decisión final: aprobado o rechazado.

### Objetivos
**Objetivo general:** identificar qué factores del solicitante y del préstamo influyen en la aprobación crediticia, y evaluar si un ratio propio aporta información adicional.

**Objetivos específicos:**
1. Limpiar los datos y documentar el tratamiento de nulos y tipos de datos (614 → 592 registros).
2. Describir el perfil de las solicitudes aprobadas frente a las rechazadas (69.4% vs. 30.6%).
3. Medir la relación de cada variable (historial crediticio, dependientes, co-solicitante, área de la propiedad, ingresos) con la aprobación.
4. Construir y evaluar una variable que no estaba en el dataset original: el **Ratio Préstamo/Ingreso** = Monto del préstamo ÷ Ingreso total (solicitante + co-solicitante).
5. Comparar tres modelos (Regresión Logística, Random Forest, XGBoost) y ajustar el umbral de decisión.
6. Identificar las variables más importantes y traducirlas en criterios útiles para el riesgo crediticio.

### Hallazgos principales
- **El historial crediticio es el factor dominante:** con historial positivo se aprobó el 80.1% de las solicitudes, frente a solo 8.2% sin él. Además es la variable más importante tanto en Random Forest como en XGBoost.
- **El área de la propiedad importa:** la aprobación fue mayor en zonas Semiurbanas (76.8%), seguida de Urbanas (67.5%) y Rurales (61.8%).
- **La hipótesis del Ratio Préstamo/Ingreso no fue respaldada:** esperaba que este ratio explicara la aprobación mejor que el ingreso solo, pero la mediana del ratio es prácticamente igual en aprobados (0.0243) y rechazados (0.0238) (Mann-Whitney p = 0.58). El ingreso total tampoco muestra una diferencia clara entre grupos. Su alta importancia en los modelos de árboles no debe leerse como señal predictiva real, ya que las variables continuas tienden a inflar esa métrica. Probar una hipótesis y encontrar que no se sostiene sigue siendo un resultado válido.
- **El co-solicitante muestra solo una tendencia leve:** 72.2% de aprobación con co-solicitante frente a 65.9% sin él, pero la diferencia no es estadísticamente significativa (chi-cuadrado p ≈ 0.12).

### Rendimiento del modelo
| Modelo | Accuracy (conjunto de prueba, umbral 0.5) |
|---|---|
| Regresión Logística | 78.2% |
| Random Forest | 79.0% |
| XGBoost | 74.8% |

Con el umbral de decisión en 0.40, Random Forest alcanza ~79.8% de accuracy. Detecta casi todos los préstamos aprobados (recall 98%), pero solo el 39% de los rechazados. Para una entidad financiera esto importa: aprobar un préstamo riesgoso suele costar más que rechazar uno bueno, por lo que una implementación real priorizaría detectar los rechazos.

### Limitaciones
- Muestra pequeña (592 filas) y una sola partición entrenamiento/prueba con 119 registros de prueba.
- El umbral se comparó sobre el mismo conjunto de prueba usado para evaluar, lo que puede hacer los resultados algo optimistas. El siguiente paso sería usar validación cruzada o un conjunto de validación aparte.
- Con clases desbalanceadas el accuracy por sí solo engaña; el recall de la clase "Rechazado" es la métrica más relevante.

### Herramientas
- **Python:** Pandas, NumPy, Matplotlib, Seaborn
- **Machine Learning:** Scikit-learn (Logistic Regression, Random Forest), XGBoost

### Dataset
Dataset obtenido originalmente de [Kaggle](https://www.kaggle.com/) y editado para este proyecto.
