# Datos de vuelos del Departamento de Transporte de Estados Unidos (2013)

## Descripción general
Este proyecto analiza datos reales de vuelos comerciales en Estados Unidos durante el año 2013, publicados por el Departamento de Transporte de EE. UU. El objetivo principal es estudiar el comportamiento de los retrasos en la salida y llegada de los vuelos, así como evaluar distintos modelos estadísticos para su análisis y predicción.

El problema se aborda desde dos enfoques:
- **Regresión**, para modelar el tiempo de retraso en minutos.
- **Clasificación**, para determinar si un vuelo llega tarde (más de 15 minutos de retraso).

---

## Objetivos
- Analizar patrones asociados a los retrasos en vuelos comerciales.
- Evaluar modelos de regresión lineal múltiple y regresión polinómica.
- Reformular el problema como una tarea de clasificación mediante un modelo lineal generalizado (regresión logística).
- Interpretar el desempeño de los modelos y sus limitaciones.

---

## Dataset
El conjunto de datos contiene **271,940 observaciones** y **20 variables**, correspondientes a vuelos nacionales en EE. UU. durante 2013.

Algunas variables relevantes son:
- `Month`, `DayofMonth`, `DayOfWeek`
- `Carrier` (compañía aérea)
- `OriginAirportID`, `DestAirportID`
- `CRSDepTime`, `CRSArrTime`
- `DepDelay`, `ArrDelay`
- `DepDelay15`, `ArrDelay15` (indicadores binarios de retraso > 15 minutos)
- `Cancelled`

---

## Metodología y modelos implementados

### 1. Preprocesamiento y EDA
- Imputación de valores nulos en variables binarias usando la información de retraso en minutos.
- Eliminación de valores atípicos extremos en retrasos de salida y llegada.
- Análisis exploratorio de retrasos por aerolínea, día de la semana, aeropuerto y ruta.

### 2. Regresión lineal múltiple
Se ajustó un modelo de regresión lineal múltiple para predecir el retraso en la llegada (`ArrDelay`) a partir de variables temporales y categóricas.

Métricas evaluadas:
- RMSE
- MAE
- R²

### 3. Regresión polinómica
Se extendió el modelo lineal incorporando términos polinómicos de grado 2 y 3 con el objetivo de capturar posibles relaciones no lineales.

Los resultados mostraron mejoras marginales respecto al modelo lineal, con un incremento mínimo en el R².

### 4. Modelo Lineal Generalizado (GLM) con familia binomial
Se reformuló el problema como clasificación binaria utilizando la variable `ArrDelay15`.

- Modelo: Regresión logística
- Salida: Probabilidad de que un vuelo llegue tarde
- Evaluación mediante matriz de confusión, sensibilidad y especificidad
- Análisis del efecto de las variables a través de los coeficientes del modelo

---

## Estructura del repositorio

---

## Requisitos
Para ejecutar el proyecto se requiere:

- R (versión 4.0 o superior)
- Paquetes:
  - tidyverse
  - ggplot2
  - broom
  - caret
  - yardstick

Los paquetes pueden instalarse ejecutando:
```r
install.packages(c("tidyverse", "ggplot2", "broom", "caret", "yardstick"))
```

---
## Instrucciones de uso

1. Clonar el repositorio
2. Abrir el archivo Proyecto.ipynb en RStudio o Jupyter Notebook con kernel de R.
3. Ejecutar las celdas en orden para reproducir el análisis completo.

---

## Autor

#### -Jesús García Abreu
#### -Proyecto Final – Estadística Avanzada
#### -Escuela Superior de Cómputo (ESCOM – IPN)
