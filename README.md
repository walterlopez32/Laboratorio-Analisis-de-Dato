
Análisis de Tendencias Financieras

Este proyecto documenta el proceso completo de extracción, transformación, análisis y exploración de un dataset sobre tendencias financieras, realizado en Google Colab.
El objetivo fue preparar los datos, explorar relaciones clave y responder preguntas de negocio relevantes en el contexto financiero.

1. Proceso ETL (Extracción, Transformación y Carga)

Extracción

El dataset Finance_Trends_enriquecido.csv fue cargado desde Google Drive.
Se implementó una función de detección automática de codificación para asegurar una lectura correcta de los datos.

 Transformación

Se aplicaron múltiples pasos de limpieza y enriquecimiento:

Corrección de errores tipográficos en nombres de columnas (por ejemplo, Stock_Marktet → Stock_Market).

Traducción al español de nombres de columnas y categorías para mejorar la comprensión.

Conversión de tipos de datos:

La columna Fecha se transformó a formato datetime.

Columnas categóricas se definieron como tipo category para optimizar memoria.

Creación de variables derivadas (Feature Engineering):

Rango_Edad: clasificación por grupo etario (18–24, 25–34, 35+).

Año_Registro y Mes_Registro: extracción temporal desde la fecha.

Expectativa_rendimiento_min y Expectativa_rendimiento_max: separación de los rangos de rendimiento expresados en texto.

Riesgo_Numerico: conversión de niveles de riesgo (“Bajo”, “Medio”, “Alto”) a valores 1, 2 y 3 respectivamente.

Validación de calidad de datos:

No se encontraron duplicados.

No se detectaron valores nulos.

Carga

El DataFrame final, limpio y transformado, fue guardado como
Finance_Trends_limpio_transformado.csv en Google Drive, quedando listo para análisis posteriores.

2. Análisis Exploratorio de Datos (EDA)

El EDA tuvo como objetivo comprender la estructura de los datos, las distribuciones principales y las relaciones entre variables.

Análisis estructural

Se utilizó df.info() y df.describe() para examinar tipos de datos, conteos y estadísticas descriptivas.

Se analizaron las columnas numéricas y categóricas para verificar consistencia y valores atípicos.

Visualizaciones y relaciones

Distribución de participantes por Rango_Edad y Tipo_de_activo.

Mapa de calor de correlaciones entre variables numéricas para detectar relaciones lineales.

Boxplot de Tasa de Interés vs Nivel de Riesgo, mostrando cómo la tasa varía según el perfil de riesgo.

Promedios de tasas de interés por País y por Tipo_de_activo.

Agrupaciones adicionales:

País × Rango_Edad

Factor_influyente × Expectativa_rendimiento

Tipo_de_activo × Riesgo

Estas visualizaciones permitieron detectar patrones de comportamiento e identificar diferencias relevantes entre países, activos y perfiles de riesgo.

3. Preguntas de Negocio y Hallazgo
 Pregunta 1

¿En qué tipo de activo invierten más (en promedio) las personas de cada rango de edad?

Evidencia: tabla de promedios de inversión por grupo etario.
Hallazgo: los jóvenes (18–24) muestran mayor preferencia por activos como oro o criptomonedas, mientras que los adultos mayores (35+) tienden hacia bonos corporativos o fondos de inversión más estables.

Pregunta 2

¿Existe una diferencia clara en la tasa de interés promedio entre niveles de riesgo (Bajo, Medio y Alto)?

Evidencia: tabla estadística con promedio, mediana, mínimo, máximo y desviación estándar de la tasa de interés por nivel de riesgo.
Hallazgo: las tasas promedio aumentan con el nivel de riesgo, siendo más altas en inversiones de riesgo medio y alto. Sin embargo, también presentan mayor dispersión, lo que indica mayor volatilidad y menor previsibilidad.

 Pregunta 3

¿Cuáles son los tipos de activo más populares en cada país?

Evidencia: tabla de promedios de inversión por país.
Hallazgo: se observaron diferencias regionales:

EE. UU. y Argentina lideran con los promedios más altos (≈6.4),

Colombia presenta los valores más bajos (≈6.18).
Esto sugiere variaciones en el apetito de riesgo y estrategias de inversión entre mercados, lo que sería clave para adaptar productos financieros localmente.

Conclusión General

El análisis permitió comprender las tendencias y patrones de inversión según país, edad y nivel de riesgo.
Los resultados indican que las decisiones financieras están influenciadas por factores demográficos y geográficos, y que las tasas de interés reflejan una compensación entre riesgo y rendimiento.

Este trabajo sienta las bases para:

Crear dashboards interactivos de monitoreo financiero.

Diseñar modelos predictivos de comportamiento de inversión.

Proponer estrategias de segmentación y personalización de productos bancarios.

- Tecnologías utilizadas------

Python (Pandas, Matplotlib, Seaborn)

Google Colab

Excel / CSV como formato de intercambio

GitHub para documentación y versionado

📘 Autor

Walter López
Proyecto académico de análisis de datos financieros — 2025
Repositorio: GitHub - Finance Trends Analysis
