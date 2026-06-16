# 🏦 Loan Approval Analysis / Análisis de Aprobación de Préstamos

> 🌐 [English](#english) | [Español](#español)

---

<a name="english"></a>
## 🇬🇧 English

### What is this project about?
Analysis of loan application data to understand which variables actually influence approval or rejection decisions — and whether a self-proposed financial ratio could explain outcomes better than raw income alone.

### Key insight
I proposed a new variable not present in the original dataset:

**Loan-to-Income Ratio** = Loan Amount ÷ Total Income (applicant + co-applicant)

My hypothesis was that this ratio would better explain credit approval than income alone — and the data confirmed it.

### Main findings
- Credit history was the single most determinant factor for approval
- The Loan-to-Income Ratio proved to be a key predictive variable
- Having a co-applicant significantly improves approval chances

### Model performance
Three models were tested (Logistic Regression, Random Forest, XGBoost), reaching ~79% accuracy. This is expected given the dataset's constraints: it is **synthetic data from Kaggle** with only 592 rows. Synthetic data has artificial patterns that naturally cap model performance — real-world data would yield different results.

### Tools
- **Python:** Pandas, NumPy, Matplotlib, Seaborn
- **Machine Learning:** Scikit-learn (Logistic Regression, Random Forest), XGBoost

### Dataset
Synthetic dataset sourced from [Kaggle](https://www.kaggle.com/).

---

<a name="español"></a>
## 🇵🇪 Español

### ¿De qué trata este proyecto?
Análisis de datos de solicitudes de préstamos para entender qué variables realmente influyen en las decisiones de aprobación o rechazo, y si un ratio financiero propuesto por mí podía explicar los resultados mejor que el ingreso bruto solo.

### Insight principal
Propuse una variable nueva que no estaba en el dataset original:

**Ratio Préstamo/Ingreso** = Monto del préstamo ÷ Ingreso total (solicitante + co-solicitante)

Mi hipótesis era que este ratio explicaría mejor la aprobación que el ingreso solo — y los datos lo confirmaron.

### Hallazgos principales
- El historial crediticio fue el factor más determinante para la aprobación
- El Ratio Préstamo/Ingreso resultó ser una variable predictiva clave
- Tener un co-solicitante mejora significativamente las probabilidades de aprobación

### Rendimiento del modelo
Se probaron 3 modelos (Logistic Regression, Random Forest, XGBoost), alcanzando ~79% de accuracy. Esto es esperado dadas las limitaciones del dataset: es **data sintética de Kaggle** con solo 592 filas. Los datos sintéticos tienen patrones artificiales que limitan el techo del modelo — con datos reales los resultados serían distintos.

### Herramientas
- **Python:** Pandas, NumPy, Matplotlib, Seaborn
- **Machine Learning:** Scikit-learn (Logistic Regression, Random Forest), XGBoost

### Dataset
Dataset sintético obtenido de [Kaggle](https://www.kaggle.com/).
