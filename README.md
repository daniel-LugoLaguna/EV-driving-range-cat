# EV-driving-range-cat
Analysis of shortest path and driving range for EV in Spain (Catalonia)

En este repositorio se incluyen una serie de notebooks de python con el proceso end-to-end para el cálculo de ruta óptima entre dos puntos específicos de Cataluña (España), utilizando los puntos de recarga disponibles de forma pública a fecha de Mayo de 2021, de acuerdo a los datos publicados por el Gobierno de España.

Para obtener el resultado final, la ejecución de los notebooks debe hacerse de forma ordenada, siguiendo el esquema mostrado a continuación.

![image](https://user-images.githubusercontent.com/62033937/146551025-5e1242ce-4337-42f1-99ed-ac436d894194.png)

La descripción de los distintos documentos de este repositorio, puede verse a continuación:
- *calculo_distancias.ipynb*: Este documento incluye la extracción de datos distancia y duración de trayecto a través de la API de Google Maps. También se generan las variaciones sin repetición de parejas de elementos, para de esta forma calcular todas las distancias entre todos los puntos entre sí. Se realizan las transformaciones necesarias sobre el dataset para alcanzar este objetivo.
- *calculo_ruta_optima.ipynb*: Incluye la generación del algoritmo de ruta óptima con puntos de carga intermedio. Se aplican también las hipótesis de cálculo para generar el grafo en base a las condiciones especificadas (distancia máxima de trayecto, tipología de puntos de carga, entre otros)
- *enriquecimiento_distancias.ipynb*: En este documento se procede a la carga y limpieza del dataset generado en el documento calculo_distancias.ipynb para generar el dataset final utilizado en el algoritmo de ruta mínima.
- *estimacion_consumo_energetico.ipynb*: En este documento se analizan los datos de un conjunto de trayectos realizados por 20 vehículos eléctricos del mismo modelo (Mitsubishi iMiEV, Modelo 2010) en distintos puntos de Australia, con el objetivo de estudiar el impacto de distintas características y factores externos del trayecto sobre el consumo energético de la batería.
- *mapa_puntos_carga.ipynb*: En este documento de código se describe la generación de mapas de puntos de recarga de vehículo eléctrico en Cataluña, a partir de los datos disponibles en el portal de datos abiertos del gobierno de España. Se generan también los datasets de trayectos óptimos en base al algoritmo generado en calculo_ruta_optima.ipynb.
- *random_forest_EV.zip*: Este fichero comprimido contiene el modelo Random Forest ajustado y optimizado en el documento estimacion_consumo_energetico.ipynb, que se ha utilizado para generar las predicciones de consumo energético del vehículo.
