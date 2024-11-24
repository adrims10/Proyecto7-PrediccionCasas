# Proyecto7-PrediccionCasas
![casa](https://github.com/user-attachments/assets/cc64f4e9-190a-41a0-b4db-dea25427da44)

¡Bienvenidos!
Es un placer recibirlos en este nuevo proyecto.

📝 ¿En qué consiste?

Introducción
La predicción de precios de bienes inmuebles es un área clave en la intersección de los negocios y la ciencia de datos. En este proyecto, abordarás el desafío de estimar el precio de las casas. Trabajaras con un conjunto de datos real, que contiene información detallada sobre propiedades en Madrid, como su tamaño, ubicación, número de habitaciones, tipo de propiedad, y más. El objetivo principal del proyecto es predecir el precio de una casa,

Contexto del Problema
El mercado inmobiliario es dinámico y está influenciado por múltiples variables, como la ubicación, las características de la propiedad y las condiciones económicas. Un modelo predictivo preciso puede ser una herramienta poderosa para agentes inmobiliarios, compradores y vendedores. Este proyecto te sumergirá en la complejidad de estos factores y te enseñará cómo transformarlos en conocimiento útil para la toma de decisiones.

🗂️ Estructura del Proyecto
Hemos creado un entorno de trabajo estructurado de la siguiente manera:


├── notebooks/           # Notebooks de Jupyter donde podemos encontrar el tratado de datos y el modelo                                          ├── src/                 # Scripts de procesamiento, modelado y predicción
├── datos/                # Archivos CSV y otros datos recopilados
├── README.md            # Descripción del proyecto en español
├── Archivo presentacion resultados    #Descripción y conclusiones del modelo

🛠️ Instalación y Requisitos
Este proyecto utiliza Python 3.12.6. Aquí tienes las bibliotecas necesarias:

python
pip install beautifulsoup4 requests pandas numpy selenium webdriver_manager
BeautifulSoup: Para el web scraping.

Requests: Para hacer solicitudes HTTP.

Pandas: Para manipulación y análisis de datos.

Numpy: Para operaciones numéricas.

Selenium y WebDriver Manager: Para automatización de navegadores web.


Resultados y Conclusiones   

**Columnas del conjunto eliminadas:**

operation: Esta columna podría contener información sobre el tipo de operación (alquiler). 

parkingSpace:  Porcentaje muy alto de nulos. 

detailedType: Esta columna tienes  detalles más específicos del tipo de propiedad que ya están cubiertos por otras columnas más generales. 

hasPlan: Información sobre si hay planos disponibles puede no ser relevante para el análisis de precios. 

address: Las direcciones específicas pueden no ser necesarias si ya tienes información suficiente sobre la ubicación a nivel de barrio o distrito. 

suggestedTexts: Esta columna podría contener textos sugeridos que no son necesarios para tu análisis. 

newDevelopmentFinished: Esta columna tiene detalles más específicos del tipo de propiedad que ya están cubiertos por otras columnas más generales. 

labels: Etiquetas adicionales que pueden no añadir valor a tu análisis actual. 

province: estamos analizando solo madrid 

country: Estamos analizando solo España 

propertyCode: Los códigos únicos de propiedad pueden no ser útiles para el análisis estadístico. 

numPhotos: El número de fotos podría no influir en el análisis de precios y por lo tanto ser innecesario. 

latitude y longitude: Las coordenadas específicas pueden no ser necesarias si ya tienes datos de ubicación categórica como barrio o distrito. 

description: Descripciones textuales pueden no ser útiles para el análisis cuantitativo. 

hasVideo: Información sobre la disponibilidad de videos podría no ser relevante para el análisis de precios. 

has3DTour: Similar a hasVideo, si los tours en 3D no son relevantes para tu análisis, esta columna puede ser eliminada. 

has360: Si la disponibilidad de vistas en 360 grados no es relevante para tu análisis, puedes eliminar esta columna. 

hasStaging: Información sobre la puesta en escena puede no ser relevante para el análisis de precios. 

superTopHighlight: Indicadores de destacados especiales pueden no ser útiles para el análisis de precios. 

topNewDevelopment: Si la condición de desarrollo nuevo superior no es relevante, esta columna puede ser eliminada. 

externalReference: Referencias externas pueden no añadir valor a tu análisis estadístico. 

**Tratamiento de duplicados:**
Con respecto a los 8 unicos valores que teniamos duplicados, lo hemos borrado.

**Tratamiento de duplicados:**
Con respecto a los 8 unicos valores que teniamos duplicados, lo hemos borrado.

**Gestion de nulos:**
Vamos a reemplazar categoricas por  valor desconocido.
Vamos a reemplazar las variables numericas con el método 

**Gestion de outlaiiers:**
La cantidad de outliers que tenemos para la columna SIZE es 175
La cantidad de outliers que tenemos para la columna ROOMS es 107
La cantidad de outliers que tenemos para la columna BATHROOMS es 220
La cantidad de outliers que tenemos para la columna PRICEBYAREA_KNN es 134
La cantidad de outliers que tenemos para la columna PARKINGSPACEPRICE_KNN es 130

Hemos gestionado los outlaiers mediante un imputador por la mediana.


**Preprocesamiento:**

Las variables categóricas fueron codificadas mediante un TargetEncoder, mientras que las variables numéricas se escalaron con 
un StandardScaler.

## Resultado Modelo 1:

1. División de datos:
a. Los datos se dividieron en conjuntos de entrenamiento y prueba con un 
tamaño del 70% para entrenamiento y el 30% para prueba.

2. Modelo de predicción:
a. Se utilizó un modelo de Random Forest Regressor con una semilla fija 
para garantizar la reproducibilidad.

b. El modelo fue entrenado con el conjunto de datos preprocesados.

4. Evaluación del modelo:
   
a. La métrica principal utilizada fue el Error Cuadrático Medio (RMSE), que 
resultó ser de 12.44. Este valor indica una baja desviación entre las 
predicciones y los valores reales, sugiriendo un modelo robusto para 
este conjunto de datos.

b. Ejemplos de predicción mostraron un alto grado de precisión, con 
predicciones muy cercanas a los valores reales:

i. Precio real: 720.00, Predicción: 720.02
ii. Precio real: 699.00, Predicción: 699.12

## Resultado Modelo 2:

1. División de datos:
   
a. Los datos se dividieron en conjuntos de entrenamiento y prueba con un 
tamaño del 80% para entrenamiento y el 20% para prueba.

2. Modelo de predicción:
a. Se utilizó un modelo de Decision Tree Regresor con una semilla fija para 
garantizar la reproducibilidad.

b. El modelo fue entrenado con el conjunto de datos preprocesados.

3. Evaluación del modelo:

a. La métrica principal utilizada fue el Error Cuadrático Medio (RMSE), que 
resultó ser de 14.53. Este valor indica una baja desviación entre las 
predicciones y los valores reales, sugiriendo un modelo robusto para 
este conjunto de datos.

b. Ejemplos de predicción mostraron un alto grado de precisión, con 
predicciones muy cercanas a los valores reales:

i. Precio real: 720.00, Predicción: 718.00
ii. Precio real: 699.00, Predicción: 699.00

## Resultado Modelo 3:

1. División de datos:
   
a. Los datos se dividieron en conjuntos de entrenamiento y prueba con un tamaño del 70% para
entrenamiento y el 30% para prueba.

2. Modelo de predicción:
   
a. Se utilizó un modelo de Gradient Boosting Regressor con una tasa de aprendizaje de 0.1 y 100
estimadores, asegurando un balance entre complejidad y precisión.

b. El modelo fue entrenado con el conjunto de datos preprocesados.

3. Evaluación del modelo:
   
a. La métrica principal utilizada fue el Error Cuadrático Medio (RMSE), que resultó ser de 8.67. Este
valor indica una excelente precisión y baja desviación entre las predicciones y los valores reales,
sugiriendo un modelo altamente robusto para este conjunto de datos.

b. Ejemplos de predicción mostraron un alto grado de precisión, con predicciones muy cercanas a
los valores reales:

Proceso y conclusiones modelo
 i. Precio real: 720.00, Predicción: 719.85
 ii. Precio real: 699.00, Predicción: 699.12


Próximos Pasos
📈 Después de recopilar y analizar los datos actuales, el próximo paso es implementar técnicas de paralelización y asincronía para mejorar la eficiencia del scraping y el procesamiento de datos.

Seguir entrenando el modelo predictivo.
Abarcar mas zonas geograficas.


🏍️ 🌟
![OIP](https://github.com/user-attachments/assets/a3261f22-9193-45df-bf33-14a396dfd988)
