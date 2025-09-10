
# Clasificación de Notas Clínicas con NLP y Enfoque Ético

## Resumen
Este proyecto aborda la clasificación automática de notas clínicas según su nivel de gravedad (leve, moderado, severo) utilizando técnicas de Procesamiento de Lenguaje Natural (NLP). El objetivo principal es doble: por un lado, desarrollar un modelo de alta precisión comparando arquitecturas clásicas y de vanguardia (Transformers); por otro, realizar un análisis crítico sobre las implicaciones éticas, los sesgos y la responsabilidad que conlleva desplegar estos sistemas en un entorno tan sensible como el de la salud.

El flujo de trabajo incluye la creación de un dataset desafiante, el preprocesamiento de texto, el entrenamiento de múltiples modelos y una evaluación rigurosa de sus resultados y limitaciones.

---

## Dataset
El proyecto se inició con un dataset de 200 notas clínicas. Para simular un escenario más realista y evitar que los modelos alcanzaran métricas "perfectas" engañosas, el conjunto de datos fue aumentado a 455 registros utilizando IA. Este nuevo dataset introdujo mayor variabilidad lingüística y ambigüedad, forzando a los modelos a desarrollar una comprensión semántica más profunda. El dataset final presenta una distribución relativamente balanceada, lo cual es fundamental para entrenar un clasificador sin sesgos hacia la clase mayoritaria.

## Preprocesamiento

 - Limpieza de caracteres especiales y puntuación.

 - Tokenización de las notas clínicas.

 - Eliminación de stopwords (palabras comunes sin valor semántico).

 - Aplicación de stemming para reducir las palabras a su raíz.

---

## Modelos Comparados
Se implementaron tres familias de modelos para evaluar la evolución de las técnicas de NLP:

**1.Modelos Clásicos (Bag-of-Words):**

 - Vectorización: TF-IDF (Term Frequency-Inverse Document Frequency).

 - Clasificadores: Naive Bayes y Random Forest. Estos modelos basan sus predicciones en la frecuencia de las palabras, sin capturar el contexto.

**2.Word Embeddings:**

 - Vectorización: Word2Vec, que crea representaciones vectoriales densas de las palabras, capturando algunas relaciones semánticas.

 - Clasificador: Random Forest.

**3.Transformers:**

 - Modelo: Fine-tuning de distilbert-base-multilingual-cased, una arquitectura de vanguardia que procesa el texto de manera contextual, entendiendo el significado de las palabras según su posición y relación en la oración.

---

## Resultados

Para un uso en producción, el modelo BERT es claramente la mejor elección por su capacidad de generalización.

<img width="830" height="138" alt="image" src="https://github.com/user-attachments/assets/eb9212fd-63a9-4958-a23d-b33c69d2d4f2" />


Los resultados demostraron una clara superioridad de la arquitectura Transformer, que fue capaz de entender los matices del lenguaje clínico que los otros modelos no pudieron capturar.

- Matriz de confusión qeu muestra las clasificaciones realizadas por el modelo.
<img width="600" height="556" alt="image" src="https://github.com/user-attachments/assets/3311755e-fd4e-4a6c-910b-4c7853b4fe73" />

**Tabla de Predicciones de Ejemplo**
 - La siguiente tabla ilustra cómo el modelo DistilBERT clasifica correctamente notas clínicas, incluso cuando la gravedad no es explícita.

<img width="600" height="248" alt="image" src="https://github.com/user-attachments/assets/1d92a7e9-d796-4813-b2bb-58075c89be76" />

---

## Conclusiones 

**Responsabilidad en el Despliegue:**

- Herramienta de Apoyo, no Oráculo: Un modelo de IA debe ser una herramienta para asistir al personal clínico, no para reemplazar su juicio. Su función es priorizar y señalar, pero la decisión final siempre debe ser humana.

- Monitorización Continua: Es crucial vigilar la calidad de los datos de entrada para evitar que sesgos demográficos o sociales (sobrerrepresentación de ciertos grupos) afecten negativamente la equidad del modelo. Un sistema sesgado puede perpetuar desigualdades en la atención sanitaria.

- En conclusión, la implementación de IA en salud exige un escepticismo crítico. La excelencia técnica debe ir siempre acompañada de un marco ético robusto que garantice la seguridad, justicia y fiabilidad del sistema.

---

## Librerías principales
  - pandas
  - numpy
  - matplotlibseabornnltk
  - re
  - scikit-learn
  - gensim
  - transformers
  - tensorflow

---
> Proyecto desarrollado como parte de portafolio de Machine Learning avanzado.
---
