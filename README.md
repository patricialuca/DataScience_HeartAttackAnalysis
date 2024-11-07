# Heart Attack Analysis & Prediction

Este proyecto aborda la limpieza, análisis y modelado predictivo de un conjunto de datos de ataques al corazón. Utilizamos métodos de estadística y aprendizaje supervisado para clasificar las probabilidades de sufrir un ataque al corazón en función de varias características clínicas.

> **Nota**: Este proyecto fue realizado para la asignatura **Tipología y ciclo de vida de los datos** del **Máster de Ciencia de Datos** en la **Universitat Oberta de Catalunya (UOC)**.

## Descripción del Dataset

El conjunto de datos contiene 303 observaciones con 14 variables relacionadas con la salud del paciente, como edad, colesterol, frecuencia cardíaca, y características electrocardiográficas. Estas variables se procesaron y categorizan para facilitar el análisis y la modelización.

### Principales Variables
- `age`: Edad del paciente
- `sex`: Sexo del paciente
- `cp`: Tipo de dolor en el pecho
- `trtbps`: Presión arterial en reposo
- `chol`: Niveles de colesterol
- `fbs`: Glucemia en ayunas (> 120 mg/dl)
- `restecg`: Resultados electrocardiográficos en reposo
- `thalachh`: Frecuencia cardíaca máxima alcanzada
- `output`: Indicador de ataque al corazón (0: menor riesgo, 1: mayor riesgo)

## Preprocesamiento de Datos

1. **Renombrado de Variables**: Para mejorar la claridad, las columnas se renombraron y se asignaron etiquetas a los valores categóricos.
2. **Limpieza de Datos**: El dataset no contenía valores nulos; sin embargo, se eliminaron ciertos valores extremos en colesterol y frecuencia cardíaca.
3. **Factorización**: Se convirtieron las variables categóricas en factores para los modelos de análisis.

## Análisis Estadístico

### Análisis Univariante
Se realizaron pruebas de normalidad y homocedasticidad:
- **Normalidad**: Todas las variables numéricas presentan una distribución no normal según el test de Shapiro-Wilk.
- **Homocedasticidad**: La presión arterial y el colesterol no presentan varianzas significativamente diferentes entre grupos.

### Análisis de Correlación
- Se observó una correlación positiva entre la frecuencia cardíaca y el riesgo de ataque.
- Inesperadamente, a mayor edad, menor fue el riesgo de ataque.

### Regresión Logística
Un modelo de regresión logística probó la relación de variables numéricas y categóricas (frecuencia cardíaca y número de vasos). La frecuencia cardíaca resultó ser un predictor significativo.

### Random Forest
Para la clasificación dicotómica (`output`), se utilizó un modelo de Random Forest, obteniendo:
- **Precisión**: 0.82
- **Sensibilidad**: 0.91
- **Especificidad**: 0.71

## Conclusiones

- **Frecuencia cardíaca**: Es un predictor fuerte para ataques al corazón.
- **Edad y colesterol**: Tuvieron menos peso en el modelo.
- **Dolor en el pecho**: Los pacientes con dolor atípico o relacionado con la angina tienen mayor riesgo de ataque.

## Requisitos

- Lenguaje: R
- Librerías: `tidyverse`, `caret`, `rpart`, `rpart.plot`

## Estructura del Repositorio

- `data/`: Contiene el dataset.
- `scripts/`: Código en R para el análisis y modelos.

## Contribuciones

Este proyecto fue realizado por **Patricia Luengo Carretero**. Puedes ver más sobre mi trabajo en [mi sitio web personal](https://www.patricialuca.es).



