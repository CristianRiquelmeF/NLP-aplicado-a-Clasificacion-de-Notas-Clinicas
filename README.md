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
