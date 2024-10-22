# Pneumonia-Detection-CNN
Repositorio del código para el TFM sobre la detección de neumonía en radiografías de tórax usando redes neuronales convolucionales (CNN). El proyecto incluye técnicas de clasificación de imágenes y segmentación para el diagnóstico automático de neumonía

##Resumen
La neumonía es una infección respiratoria aguda que afecta a los pulmones, causando inflamación y dificultades para respirar. Cada año, la neumonía afecta a millones de personas en todo el mundo y es una de las principales causas de muerte a nivel global. La detección temprana de la enfermedad es crucial para asegurar el éxito del tratamiento. Las radiografías de tórax son el método más comúnmente utilizado para diagnosticar neumonía. En una radiografía, la neumonía aparece como áreas blancas o grises, pero su identificación visual puede ser desafiante debido a la variabilidad en su manifestación, la superposición de estructuras anatómicas y la presencia de otras anomalías pulmonares no relacionadas.
En este estudio, se desarrolla un sistema de diagnóstico automatizado de neumonía a partir de radiografías torácicas mediante modelos de aprendizaje profundo. El trabajo abarca todos los pasos, desde la obtención de los datos brutos hasta la realización de experimentos con diferentes arquitecturas de redes neuronales y la evaluación del modelo final. Se implementan modelos de clasificación y modelos mixtos (clasificación y segmentación), utilizando desde cero, transfer learning y fine tuning, con enfoques de entrada múltiple (imágenes y datos numéricos) y salida múltiple (máscara y clase), con y sin bloques residuales.
El modelo final es un modelo mixto basado en la arquitectura U-Net, con entrada múltiple y salida múltiple. Tiene una profundidad de 4 bloques convolucionales, prioriza el entrenamiento en un 90% para la segmentación y un 10% para la clasificación, utiliza bloques residuales y activación LeakyReLU. Además, emplea fusión tardía para integrar las variables numéricas con la salida de U-Net para la máscara y la clasificación. El enfoque propuesto se evalúa en dos conjuntos de datos disponibles públicamente, proporcionados por RSNA y Kermany et al. El modelo alcanza una precisión (accuracy) del 78.98% y del 90% en los conjuntos de prueba. Comparado con el modelo de referencia propuesto por Kundu et al. (2021), que utiliza un ensamblaje de 3 modelos y alcanza una precisión del 86.85% y 98.8%, el modelo propuesto muestra resultados prometedores y deja espacio para trabajo futuro. A continuación, se presenta un resumen gráfico del modelo final.

## Resumen gráfico
![Modelo Final](images/modelo_final.png)

## Estructura del repositorio:
#### 01_EDA.ipynb:
Exploratory Data Analysis (EDA) del dataset. Incluye un análisis descriptivo de las imágenes, distribución de las clases y variables numéricas como la edad, el sexo y la posición de las radiografías.

#### 02_Preprocessing.ipynb:
Proceso de preprocesamiento de los datos, que abarca la normalización de las imágenes, la gestión de valores atípicos y nulos, así como la transformación de las imágenes y las máscaras para su uso en los modelos de aprendizaje profundo.

#### 03_Classification_Models.ipynb:
Implementación de modelos de clasificación usando redes neuronales convolucionales para predecir la presencia de neumonía en las radiografías. Se incluyen las métricas utilizadas para evaluar los modelos, como accuracy, recall, y f1-score.

#### 04_Mixed_Models.ipynb:
Modelos mixtos que combinan segmentación y clasificación. Se incluye un enfoque donde se predice tanto la presencia de neumonía como la región afectada dentro del pulmón.

#### 05_Kermany_Testing.ipynb:
Pruebas realizadas con el dataset de Kermany para comparar los resultados de los modelos y validar su desempeño en un conjunto de datos diferente.

