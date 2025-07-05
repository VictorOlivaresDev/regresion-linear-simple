# Predicción del PIB de México con Regresión Logística

## 📝 Descripción del Proyecto

Este proyecto de ciencia de datos tiene como objetivo predecir el Producto Interno Bruto (PIB) de México utilizando un modelo de regresión logística. Se analiza la evolución histórica del PIB desde 1960 hasta 2021 para construir un modelo capaz de estimar el valor del PIB para el año 2022.

---

## 📊 Datos Utilizados

La base de datos utilizada para este proyecto contiene el **PIB de México** para el periodo comprendido entre los años **1960 y 2021**. El conjunto de datos consta de dos columnas:

- **Periodo**: El año correspondiente al registro del PIB.
- **GDP**: El valor del Producto Interno Bruto para ese año.

---

## 🛠️ Técnicas y Metodología

Para el desarrollo de este modelo predictivo se aplicaron las siguientes técnicas:

### **1. Preprocesamiento de Datos**

Se llevó a cabo la **normalización** de los datos para escalar las variables a un rango específico y así mejorar el rendimiento del modelo de regresión. Esto se realizó dividiendo cada valor de las columnas "Periodo" y "GDP" entre el valor máximo de su respectiva columna.

### **2. División del Conjunto de Datos**

El conjunto de datos se dividió en dos subconjuntos:

- **80% para entrenamiento**: Utilizado para entrenar el modelo.
- **20% para pruebas**: Empleado para evaluar el rendimiento y la precisión del modelo entrenado.

### **3. Modelo de Regresión Logística (Función Sigmoide)**

Se implementó una función **sigmoide** para modelar la relación entre el año y el PIB. La ecuación de la función sigmoide utilizada es:

$$y = \frac{1}{1 + e^{-\beta_1(x - \beta_2)}}$$

Donde:

- $y$ es la predicción del PIB.
- $x$ es el año.
- $\beta_1$ y $\beta_2$ son los parámetros del modelo que se ajustan durante el entrenamiento.

Se utilizó la función `curve_fit` de la librería `scipy.optimize` para encontrar los valores óptimos de $\beta_1$ y $\beta_2$ que mejor se ajustan a los datos de entrenamiento.

---

## 📈 Resultados y Conclusiones

### **Evaluación del Modelo**

El modelo de regresión logística demostró tener un excelente rendimiento al ser evaluado con los datos de prueba. Las métricas obtenidas fueron las siguientes:

- **Error Absoluto Medio (MAE):** 0.03. Este valor tan bajo indica que las predicciones del modelo son muy cercanas a los valores reales.
- **Error Cuadrático Medio (MSE):** 0.00. Un valor de cero sugiere que no hay una penalización significativa por errores en las predicciones.
- **Coeficiente de Determinación (R²):** 0.99. Este valor, muy cercano a 1, indica que el modelo es capaz de explicar el 99% de la variabilidad de los datos, lo que lo convierte en un modelo casi perfecto para este conjunto de datos.

### **Predicción del PIB para 2022**

Utilizando el modelo entrenado, se realizó una predicción del PIB de México para el año 2022. Para ello, se normalizó el dato del año 2022 y se aplicó la función sigmoide con los parámetros $\beta_1$ y $\beta_2$ obtenidos. Finalmente, se realizó el proceso inverso a la normalización para obtener el valor del PIB en su escala original.

El resultado de la predicción fue:
**PIB para el año 2022: 1.256339e+12**

En conclusión, el modelo de regresión logística se ajustó de manera muy precisa a los datos históricos del PIB de México, lo que permitió realizar una predicción confiable para el año 2022.
