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
   - Selección de Modelo: Se seleccionó XGBoost como modelo principal debido a su equilibrio óptimo entre alta capacidad predictiva y una brecha de generalización mínima (estabilidad)

3. **Análisis de Equidad (Fairness):**
   - Se evaluó el desempeño del modelo segmentando la muestra por **género**, garantizando que la capacidad predictiva sea consistente para hombres y mujeres y descartando sesgos demográficos.

## 📊 Resultados Alcanzados
Métrica principal: F1-Score (Test) de 0.6922 (Modelo: XGBoost).
Estabilidad (Brecha de Generalización): 0.0196, lo que demuestra una alta capacidad del modelo para generalizar ante datos no vistos.
Capacidad de discriminación: El modelo muestra un rendimiento sólido y consistente, superando a arquitecturas más complejas (como el Stacking), lo cual confirma que la arquitectura seleccionada es la más eficiente para la estructura tabular del dataset.
