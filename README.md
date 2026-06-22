# TP_2_Diplomatura_IA_UP
## 🎯 Descripción del Proyecto
Este proyecto desarrolla un modelo de aprendizaje automático diseñado para identificar fumadores a partir de datos clínicos y fisiológicos. El objetivo es alcanzar la máxima capacidad predictiva, optimizando la métrica **F1-Score** para la clase positiva (fumadores), garantizando un modelo robusto, ético y libre de sesgos.

## 🚀 Metodología y Bitácora de Procesamiento
Para asegurar la calidad y reproducibilidad del modelo, se siguió el siguiente protocolo técnico:

1. **Limpieza y Preprocesamiento:**
   - **Eliminación de Constantes:** Se eliminaron variables con varianza cero (`nunique <= 1`) para reducir ruido.
   - **Ingeniería de Características:** Conversión rigurosa de todas las variables tipo `object` (como `oral`, `tartar`, etc.) a formato `integer` para habilitar el procesamiento numérico.
   - **Gestión de Sesgos:** Se realizó un `drop` explícito de la columna `ID` en todas las etapas para prevenir la fuga de información (data leakage).

2. **Entrenamiento y Modelado:**
   - Se compararon múltiples arquitecturas (Random Forest, XGBoost, Gradient Boosting).
   - **Arquitectura Final (Stacking):** Implementamos un modelo de ensamble (*StackingClassifier*) utilizando modelos de Nivel 0 (RF, XGB, GB) y un meta-modelo de Regresión Logística (Nivel 1).

3. **Análisis de Equidad (Fairness):**
   - Se evaluó el desempeño del modelo segmentando la muestra por **género**, garantizando que la capacidad predictiva sea consistente para hombres y mujeres y descartando sesgos demográficos.

## 📊 Resultados Alcanzados
- **Métrica principal:** F1-Score (target=1) de **0.7325**.
- **AUC-ROC:** **0.89**, lo cual confirma una excelente capacidad de discriminación del modelo.
- **Robustez:** La validación cruzada y el análisis de importancia de variables confirmaron que el modelo se fundamenta exclusivamente en marcadores clínicos.
