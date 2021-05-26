---
layout: article
title: "Predicción de accidentes cerebrovasculares"
categories: portfolio
excerpt: "Proyecto de Machine Learning para intentar predecir accidentes cerebrovasculares"
image:
  teaser: stroke-prediction.jpg
---

Según la Organización Mundial de la Salud (OMS), los accidentes cerebrovasculares son la segunda causa principal de muerte a nivel mundial, responsables de, aproximadamente, el 11% del total de muertes.

El objetivo de este proyecto de *Machine Learning* es intentar predecir si una persona va a padecer o no un accidente cerebrovascular.

Para ello, vamos a ir pasando por cada fase que implica un proyecto de *Machine Learning*.

#### ANÁLISIS EXPLORATORIO DE DATOS

Lo primero que tenemos que hacer, es entender los datos de los que disponemos. A continuación, se exponen las siguientes gráficas explicando su posterior análisis:

![image](/PORTFOLIO/images/stroke-distribucion-variables.jpg)

- Se puede observar que algunas variables como son **hipertensión**, **enfermedades del corazón** o el target que es **stroke** se encuentran desbalanceadas, habiendo una gran diferencia entre personas que **NO** tienen dichas enfermedades con respecto a las que **SÍ** las padecen.
- La **edad** tiene una distribución normal, encontrando más personas entre los 40 y los 55-60 años, y luego de 80 años.
- Encontramos más gente que **trabaja** en el sector privado, mientras que el resto de trabajos están más o menos a la par excepto gente que no ha trabajado nunca, en el que hay pocos datos.
- La distribución del **nivel de glucosa en sangre** es normal, ya que se concentra entre 70-100 mg/dl, lo que es una concentración normal en ayunas. A partir de 100-125 mg/dl en ayunas se conoce como estado prediabético y superior a dichas cantidades sería diabético.
- En cuanto al **IMC** o **BMI** (en inglés), se observa una distribución normal con algunos outliers. Teóricamente, si es inferior a 18.5 es 'bajo peso', entre 18.5-24.9 es 'peso normal', entre 25-29.9 se considera 'sobrepeso' y superior a 30 es 'obesidad'. Entre 30-34.9 se considera 'obesidad grado I o moderada', entre 35-39.9 'obesidad grado II o severa y a partir de 40 se considera 'obesidad grado III o mórbida'.

![image](/PORTFOLIO/images/stroke-vs-categoricas.jpg)

- Las **personas casadas** sufren más accidentes cerebrovasculares que las que no se han casado.
- Las personas que **trabajan** en el sector privado tiene más posibilidades de tener accidentes cerebrovasculares.
- El lugar de **residencia** no tiene ninguna relación ya que está balanceado.
- La gente que **fuma** tiene más probabilidades de padecer accidentes cerebrovasculares.

Por otro lado, debido a la falta de datos y al desbalanceo existente en las variables de hipertensión y enfermedades del corazón  no podemos extraer conclusiones claras sobre si están relacionadas o no a la hora de tener un accidente cerebrovascular.

![image](/PORTFOLIO/images/stroke-vs-numericas.jpg)

- En la primera gráfica se puede observar que la mayoría de personas que tienen accidentes cerebrovasculares (color rojo) superan los 45-50 años.
- En las gráficas 2 y 3, se ve una distribución más repartida entre las personas que que no tienen accidentes cerebrovasculares y las que sí tienen.
- Por tanto, de estas gráficas se puede extraer que las probabilidades de sufrir un accidente cerebrovascular dependen principalmente de la edad.
- Por otro lado, se pueden apreciar posibles outliers en el **BMI** ya que encontramos bastantes valores por encima de 50, siendo éstos valores muy altos. Sin embargo, se han registrado casos de gente con valores muy altos, incluso por encima de 100, por lo que al no tener la altura y el peso de dichas personas no se pueden sacar conclusiones claras.

#### MACHINE LEARNING

Como modelos para la parte de *Machine Learning*, se han escogido un *Logistic Regression*, un *Random Forest* y un *XGBoost*. Cada uno de ellos con sus distintos hiperparámetros y se ha graficado su matriz de confusión:

**Logistic Regression**

![image](/PORTFOLIO/images/stroke-lr-matriz.jpg)

**Random Forest**

![image](/PORTFOLIO/images/stroke-rf-matriz.jpg)

**XGBoost**

![image](/PORTFOLIO/images/stroke-xgb-matriz.jpg)

#### RESULTADOS

A continuación se presenta la tabla de resultados con las diferentes métricas obtenidas:

![image](/PORTFOLIO/images/stroke-resultados.jpg)

Observando la tabla de resultados se puede apreciar que el modelo con mayor accuracy es el **XGBoost**, y si nos fijamos en su matriz de confusión vemos que está clasificando muy bien las personas sin accidentes cerebrovasculares, fallando tan solo en 3, las cuales nos predice como que sí tienen. Sin embargo, nos está clasificando mal a las personas que realmente tienen accidentes cerebrovasculares, ya que nos está diciendo que no tienen. Por estas razones no es el mejor modelo.

A la hora de elegir el mejor modelo para nuestro caso, hay que fijarse en el modelo que mejor recall tenga, ya que se centra en minimizar los FP (falsos negativos). Por lo tanto, fijándonos en la tabla de métricas, se observa claramente que en dicha métrica destaca muy por encima del resto la **Logistic Regression** con un 0.77. Además, si nos fijamos en la matriz de confusión de dicho modelo podemos observar que es el que mejor nos está prediciendo los FN, prediciendo 14 personas que tienen accidentes cerebrovasculares como que no tienen y 48 que sí tienen nos las está clasificando correctamente.

#### SOBRE EL PROYECTO

Se ha hecho uso de las librerías de `numpy` y `pandas` para el tratamiento de los datos, las librerías de `matplotlib` y `seaborn` para realizar las diferentes gráficas y la librería de `scikit-learn` para todo lo correspondiente al apartado de *Machine Learning*. 

La base de datos se ha obtenido en la web de Kaggle, desde el siguiente [enlace](https://www.kaggle.com/fedesoriano/stroke-prediction-dataset).

El código del proyecto se pueden ver accediendo a este [repositorio](https://github.com/arturogzm93/ML-Stroke-Prediction).