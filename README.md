# proyecto-algoritmos-clasificacion
Proyecto desarrollado para el análisis y comparación de resultados obtenidos entre un mismo dataset aplicado a diferentes algoritmos de clasificación. Tiene como objetivo principal el análisis de los algoritmos con base a un taller base.

**Autora:** Angie Alejandra Chipatecua Zarate  
**CADI:** Introducción a Machine Learning
**Institución:** Universidad De Cundinamarca
**Fecha:** Otubre de 2026  

---

## Descripción del Proyecto

Este repositorio contiene el desarrollo técnico y analítico de un estudio comparativo de **Machine Learning Supervisado** para resolver un problema de clasificación diagnóstica utilizando el conjunto de datos *Breast Cancer Wisconsin Diagnostic* de Scikit-learn.

El objetivo del proyecto es analizar cómo varía el comportamiento predictivo de distintos clasificadores cuando se mantienen constantes las condiciones de entrenamiento y evaluación ($80\%$ entrenamiento y $20\%$ prueba con `stratify=y` y `random_state=42`). El modelo procesa 30 características clínicas numéricas para determinar si una muestra corresponde a un tumor **Maligno (1)** o **Benigno (0)**, evaluando los modelos no solo por su *Accuracy*, sino por su equilibrio de *Precision*, *Recall*, *F1-score* y el tipo de error cometido en sus matrices de confusión.

---

## Función y Estructura del Código

El cuaderno de Google Colab realiza el siguiente flujo de trabajo comparativo:

1. **Carga y Reorganización de Datos:** Importación del conjunto de datos `load_breast_cancer` en formato `DataFrame` y redefinición explícita de la clase positiva (`1 = maligno`, `0 = benigno`).
2. **División Muestral Estratificada:** Partición de datos en 80% para entrenamiento y 20% para prueba, aplicando `stratify=y` para conservar la proporción real de las clases en ambos subconjuntos.
3. **Construcción de Función de Evaluación Reutilizable:** Implementación de una función personalizada en Python para entrenar, predecir y calcular de forma estandarizada *Accuracy*, *Precision*, *Recall*, *F1-score* y la Matriz de Confusión.
4. **Implementación de los 5 Clasificadores:**
   * **Decision Tree:** Modelo interpretable limitado a profundidad máxima (`max_depth=4`).
   * **Random Forest:** Ensamble de 100 árboles de decisión (`n_estimators=100`) para reducir varianza.
   * **Support Vector Machine (SVM):** Clasificador con Kernel RBF integrado dentro de un `Pipeline` con estandarización de características (`StandardScaler`).
   * **K-Nearest Neighbors (K-NN):** Algoritmo basado en distancias (k=5) utilizando también un `Pipeline` con `StandardScaler`.
   * **Naive Bayes (GaussianNB):** Clasificador probabilístico evaluado bajo el supuesto de independencia condicional.
5. **Consolidación y Visualización de Resultados:** Generación de tablas comparativas en Pandas y graficación de las 5 matrices de confusión para facilitar la interpretación del trade-off entre Falsos Positivos y Falsos Negativos.
NOTA: Todos los algoritmos contienen las respuestas a preguntas generadas desde el taller.
---

## Cómo Abrir y Ejecutar el Código en Google Colab

Para visualizar y ejecutar el código sin necesidad de instalar entornos locales, puedes usar cualquiera de estas dos opciones:

### Opción 1: Abrir directamente en Google Colab (Recomendado)

1. Ingresa a Google Colab.
2. Inicia sesión con tu cuenta de Google.
3. En la ventana emergente, selecciona la pestaña **GitHub** o **Subir**:
   * **Desde GitHub:** Pega el enlace de este repositorio y selecciona el archivo `.ipynb`.
   * **Desde tu equipo:** Si descargaste el archivo `.ipynb`, ve a la pestaña **Subir** y arrastra el archivo.

---

### Opción 2: Abrir desde Google Drive

1. Sube el archivo con extensión `.ipynb` a tu unidad de **Google Drive**.
2. Haz clic derecho sobre el archivo subido.
3. Selecciona **Abrir con** ➔ **Google Colaboratory**.

---

## Instrucciones para Ejecutar el Cuaderno

Una vez abierto el cuaderno en Google Colab:

1. **Asegurar el entorno de ejecución:** Ve al menú superior en `Entorno de ejecución` ➔ `Cambiar tipo de entorno de ejecución` y verifica que esté seleccionado **Python 3**.
2. **Ejecutar todo el código:** Dirígete al menú `Entorno de ejecución` ➔ **Ejecutar todas**.
3. **Ejecución celda por celda:** Puedes ejecutar cada bloque individualmente haciendo clic en el botón de **Play** a la izquierda de cada celda.

> **Nota:** El código utiliza librerías estándar de Python (`pandas`, `numpy`, `matplotlib`, `scikit-learn`), las cuales vienen preinstaladas en Google Colab, por lo que **no se requiere la instalación de dependencias adicionales**.

---
## NOTA 
Este cuaderno y explicación solo aplica para entornos en línea (los más usados en Google Colab), no entornos en la nube, por lo que si lo requieres será necesario investigar.
