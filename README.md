# Predicción de la Demanda Energética del SADI

Proyecto desarrollado en el marco de la materia **Minería de Datos** de la Especialización en Ciencia de Datos (**UNLaM**), durante el primer cuatrimestre de 2025, con el objetivo de predecir la demanda energética del Sistema Argentino de Interconexión (**SADI**).

## 📌 Descripción del proyecto
Este proyecto se enmarca en el análisis y predicción de la demanda energética del SADI, utilizando datos históricos proporcionados por la Compañía Administradora del Mercado Mayorista Eléctrico (**CAMMESA**). El objetivo principal fue desarrollar modelos descriptivos y predictivos que permitan comprender el comportamiento de la demanda y anticipar su valor máximo diario (potencia pico), con aplicaciones directas en la planificación y operación del sistema eléctrico nacional. Para ello, se aplicaron técnicas de minería de datos utilizando la herramienta KNIME, abarcando desde análisis exploratorio hasta regresión, clasificación y descubrimiento de patrones.

### Datos Utilizados
- Fuente: CAMMESA 
- Período analizado: Enero 2007 - Febrero 2025
- Frecuencia: Diaria
- Variables originales: N° MES, VERANO / INVIERNO, SEMANA, FECHA, TIPO DIA, DIA, N° DIA, Energía SADI (GWh), Potencia Pico SADI (MW), Hora Potencia Pico, Temperatura Media Diaria GBA  (°C), Estado del Tiempo [Claro/Nublado/Seminublado].

## 📊 Proceso de Minería de Datos
El desarrollo siguió de manera implicita el enfoque CRISP-DM y se implementó utilizando KNIME Analytics Platform. Las etapas abordadas fueron: 
- Comprensión del negocio y de los datos
- Preparación de los datos
- Modelado
- Evaluación
- Despliegue (limitado a la documentación y visualización de resultados)


## 🛠️ Herramientas utilizadas

- KNIME Analytics Platform, esencial para la implementación de las etapas de preparación de datos, modelado y evaluación.
- Word (documentación del proyecto)
- Dataset descargado desde la web de CAMMESA, disponible [aquí](https://cammesaweb.cammesa.com/2023/03/14/maximos-historicos-deenergia-y-potencia-estacionales/).

## 📂 Estructura

- `docs/`: informe y diapositivas de la presentación final en formato PDF.
- `flujo_knime/`: capturas del workflow en KNIME 
- `workflow/`: contiene el archivo del workflow en formato `.knwf` para importar desde KNIME.

## 📈 Resultados

#### Modelado Predictivo
* **Modelos de regresión**: La Regresión Lineal mostró buen poder explicativo (R² > 0,96). La normalización redujo errores absolutos, mientras que el modelo sin normalizar logró mejor MAPE. Gradient Boosted Trees fue el modelo más preciso y robusto, con un error máximo de -6,91%.

* **Complejidad vs. desempeño**: Modelos complejos como la Regresión Polinómica de grado 10 presentaron sobreajuste. Modelos intermedios (grado 4) lograron buen equilibrio entre sesgo y varianza.

* **Modelos de clasificación**: Para clasificar niveles de demanda (baja/media/alta), Random Forest superó a Naive Bayes (85,8% vs. 66,9% de exactitud), sin necesidad de técnicas de balanceo como SMOTE.

* **Variables clave**: Las principales variables predictivas fueron: temperatura media diaria, energía diaria, tipo de día, estación y número de semana.

* **Impacto operativo**: El modelo final, Gradient Boosted Trees, permite predecir la potencia pico con un margen de error controlado (±7%), lo cual optimiza el proceso de despacho de energía y contribuye a la reducción de costos operativos, mejorando la eficiencia del sistema.

#### Análisis Descriptivo
* **Clustering (K-means)**: Se identificaron 4 clústeres con buena separación según el nivel de potencia, aunque con baja homogeneidad interna debido a la complejidad del fenómeno energético.

* **Análisis de Componentes Principales (PCA)**: Se redujo la dimensionalidad a 4 componentes principales, explicando el 92,3% de la varianza y revelando patrones estacionales y de tipo de día.

* **Reglas de asociación**: Se detectaron combinaciones relevantes de variables categóricas. Una regla destacada (67,8% confianza, lift 2,796) asocia días hábiles, altas temperaturas y verano con alta demanda, aportando valor operativo.

## 👥 Equipo

Proyecto realizado por:
- Barvagelata, Julián Mariano
- Fica Millán, Yesica Verónica
- González De Rose, Franco Ezequiel
- Gotte, Joaquín Ezequiel
- Miranda Quisbert, Brian Alex
- Petraroia, Franco Albano

Con la guía de la profesora Lorena Matteo.

## 📌 Notas

Este repositorio tiene fines académicos y demostrativos. Los datos utilizados provienen de fuentes oficiales y se usaron exclusivamente con fines educativos.
