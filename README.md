# 📰 Clasificación de Noticias con Word2Vec: Interpretación del Lenguaje Humano

[![Python](https://img.shields.io/badge/Python-3670A0?style=flat&logo=python&logoColor=ffdd54)](https://www.python.org/)
[![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat&logo=numpy&logoColor=white)](https://numpy.org/)
[![Scikit-learn](https://img.shields.io/badge/Scikit--learn-F7931E?style=flat&logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)

Este proyecto desarrolla un **Clasificador de Noticias** para la *start-up* **Alura Latam News** utilizando técnicas de **Word Embedding** y **Procesamiento de Lenguaje Natural (NLP)**. El objetivo es transformar los titulares de noticias en vectores numéricos (embeddings) para automatizar su clasificación en categorías temáticas.

---

## 🚀 Metodología del Proyecto

El flujo de trabajo se centra en el uso del modelo **Word2Vec** para la vectorización del lenguaje, seguido por el entrenamiento de un modelo de clasificación tradicional.

### 1. Preparación y Carga de Datos
* **Datasets:** Se utilizan los archivos `noticias_entrenamiento.csv` y `noticias_prueba.csv`.
* **Contenido:** Los datos incluyen el `titulo` de la noticia y su `categoria` (ej.: `deportes`, `ciencia y tecnología`, `economía`, `política`, etc.).
* **Vectorización Base:** El proceso comienza entendiendo la representación simple como **ONE-HOT-ENCODING** antes de la aplicación de Word Embedding.

### 2. Word Embedding (Vectorización Semántica)
* **Modelo Utilizado:** Se cargó el modelo pre-entrenado para español **`SBW-vectors-300-min5.bin.gz`** (ya que otra fuente resultó no funcional).
* **Proceso:**
    1.  **Tokenización** de los titulares de las noticias.
    2.  Generación del vector de *embedding* para cada titular mediante la **suma de los vectores** de las palabras que lo componen.
    3.  Creación de una matriz de textos utilizando **NumPy** a partir de estos vectores para el entrenamiento.

### 3. Entrenamiento y Clasificación
* **Baseline:** Inicialmente, se entrena un **`DummyClassifier`** (provisto por **Scikit-learn**) para establecer un punto de referencia de rendimiento.
* **Modelo Final:** La clasificación se realiza con un modelo de **Regresión Logística** (provisto por **Scikit-learn**) entrenado sobre la matriz de *embeddings* generada.

---

## 🛠️ Tecnologías Clave

| Herramienta | Uso Principal |
| :--- | :--- |
| **Python** | Lenguaje de programación. |
| **Word2Vec** | Modelo de Word Embedding. |
| **NumPy** | Creación y manipulación de matrices de texto (vectores). |
| **Scikit-learn** | Provee los clasificadores **Regresión Logística** y **DummyClassifier**. |

---

## 💡 Conclusiones del Aprendizaje

1.  **Necesidad de Datos Masivos:** La **generalización del modelo mejora significativamente con el volumen de datos**. Se resalta que el *dataset* utilizado (alrededor de **120,000 noticias**) es relativamente pequeño y se recomienda trabajar con volúmenes de datos mucho mayores.
2.  **Límite en Castellano:** Aún existe un gran potencial de desarrollo en el área de Word Embedding para el **idioma castellano**, siendo la disponibilidad de modelos y recursos pre-entrenados un factor que limita el desarrollo de arquitecturas más complejas.
