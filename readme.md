📊 Taller SaaS Ecommerce – Análisis de Datos🚉


Proyecto práctico de análisis, limpieza, procesamiento, visualización y segmentación de datos para validar información relacionada con un producto SaaS para comercio electrónico.


El proyecto fue desarrollado en Python utilizando Google Colab, trabajando con datos provenientes de un archivo Excel y aplicando técnicas de análisis exploratorio, estadística descriptiva, KPIs, visualización y segmentación de clientes.


---


🚀 Tecnologías utilizadas

- 🐍 Python
- ☁️ Google Colab
- 🐼 Pandas
- 🔢 NumPy
- 📊 Matplotlib
- 📈 Seaborn
- 📑 OpenPyXL
- 📄 Excel / CSV


---


📁 Estructura del proyecto


Taller-SaaS-Ecommerce/
│
├── 📓 Taller_SaaS_Ecommerce.ipynb
│
├── 📊 Validacion_SaaS_Ecommerce_Dashboard.xlsx
│
├── 📄 resumen_analisis_saas.csv
│
├── 📈 grafica1_barras.png
├── 📊 grafica2_pie.png
├── 📉 grafica3_histograma.png
├── 🔥 grafica4_heatmap.png
│
└── 📖 README.md


---


🎯 Objetivo


Analizar las respuestas de una encuesta realizada a comercios para identificar información relevante sobre:


- Sectores comerciales.
- Canales de venta.
- Métodos de pago.
- Problemas de inventario.
- Impacto del pago en un clic.
- Problemas de overselling.
- Disposición de pago por un sistema SaaS.
- Funcionalidades de upselling.
- Temores técnicos.
- Tiempo de actualización del inventario.
- Segmentación de clientes potenciales.


—
Nota: 
👍Los problemas de overselling ocurren cuando muchos clientes usan esos recursos al mismo tiempo y el sistema colapsa 


📥 Datos de entrada


El análisis utiliza el archivo:


Validacion_SaaS_Ecommerce_Dashboard.xlsx


La hoja utilizada para el análisis es:


Respuestas_Encuesta


El archivo se carga en Pandas y se transforma en un DataFrame para facilitar su procesamiento.


---


🧹 1. Limpieza e inspección de datos


Antes de realizar el análisis se verifica la calidad de los datos.


Se revisan:


- Primeras filas del DataFrame.
- Tipos de datos.
- Valores nulos.
- Filas duplicadas.
- Espacios innecesarios en textos.


También se realiza limpieza de las columnas de tipo texto mediante "strip()" para eliminar espacios al inicio y al final de las respuestas.


Ejemplo:


columnas_texto = df.select_dtypes(include='object').columns


for columna in columnas_texto:
    df[columna] = df[columna].astype(str).str.strip()


---


📊 2. Análisis estadístico


El proyecto desarrolla diferentes análisis descriptivos.


Distribución por sector


Se calcula la cantidad y porcentaje de comercios pertenecientes a cada sector:


tabla_sector = pd.DataFrame({
    'Cantidad': df['Categoría / Sector'].value_counts(),
    'Porcentaje (%)':
        (df['Categoría / Sector'].value_counts(normalize=True) * 100).round(2)
})


Tabla cruzada


Se analiza la relación entre:


Sector ↔ Precio del SaaS


mediante "pd.crosstab()".


KPIs
Un KPI significa Key Performance Indicator en inglés, y su traducción en español es indicador clave de desempeño o indicador clave de rendimiento 


Se calculan indicadores relacionados con:


- Impacto del pago en 1 clic.
- Frecuencia de problemas de overselling.


Número de canales


Las respuestas de texto se convierten a valores numéricos para calcular:


- Promedio.
- Mediana.


Método de pago


Se identifica el método de pago más utilizado por cada sector.


Comisión


Se analiza la disposición de los comercios a pagar una comisión adicional del 0,5 %.


---


📈 3. Visualización de datos


El proyecto genera diferentes tipos de gráficos para facilitar la interpretación de los resultados.


📊 Gráfico de barras


Analiza las funcionalidades de upselling más demandadas.


🥧 Gráfico circular


Representa la distribución de precios que los comercios están dispuestos a pagar.


📉 Histograma / distribución


Analiza el tiempo que tardan los comercios en actualizar su inventario.


🔥 Heatmap


Permite analizar la relación entre:


Sector ↔ Temor técnico principal


Las visualizaciones utilizan principalmente Matplotlib y Seaborn.


---


🎯 4. Segmentación de clientes


Una de las partes principales del proyecto consiste en identificar un segmento de clientes ideales para el SaaS.


El filtro considera comercios que cumplen simultáneamente con:


- Inventario mediano o grande.
- Venta en 3 o más canales.
- Disposición a pagar más de aproximadamente $100 USD mensuales.


El resultado permite conocer cuántos registros cumplen estas condiciones y visualizar información básica de esos comercios.


---


📄 5. Exportación de resultados


El proyecto genera un resumen agrupado por sector y lo exporta a formato CSV:


resumen_analisis_saas.csv


El archivo contiene información como:


- Total de comercios.
- Precio predominante.


---


📌 6. Conclusiones


El notebook genera automáticamente un resumen de los principales hallazgos del análisis, incluyendo:


- Impacto del pago en 1 clic.
- Problemas de overselling.
- Rango de precios utilizado en las conclusiones del taller.
- Cantidad y porcentaje de clientes que cumplen los criterios de segmentación.


---


▶️ Cómo ejecutar el proyecto


Opción 1 — Google Colab


1. Abrir Google Colab.
2. Crear un nuevo Notebook.
3. Subir:


Taller_SaaS_Ecommerce.ipynb


4. Subir el archivo:


Validacion_SaaS_Ecommerce_Dashboard.xlsx


5. Ejecutar las celdas del Notebook en orden.


Google Colab permite ejecutar Python desde el navegador sin necesidad de instalar Python localmente.


Carga del Excel


El Notebook utiliza:


from google.colab import files


uploaded = files.upload()


Posteriormente se selecciona el archivo Excel correspondiente.


---


📤 Archivos generados


Al finalizar el análisis se pueden obtener:


resumen_analisis_saas.csv
grafica1_barras.png
grafica2_pie.png
grafica3_histograma.png
grafica4_heatmap.png


Estos archivos pueden descargarse desde Google Colab.


---


🧠 Competencias desarrolladas


Este proyecto permite practicar:


- Análisis exploratorio de datos.
- Limpieza de datos.
- Manipulación de DataFrames.
- Estadística descriptiva.
- Cálculo de indicadores KPI.
- Transformación de datos.
- Tablas cruzadas.
- Visualización de información.
- Segmentación de clientes.
- Exportación de resultados.
- Análisis orientado a decisiones de negocio.


---


📚 Flujo del proyecto


📥 Datos Excel
      ↓
🧹 Limpieza
      ↓
🔍 Inspección
      ↓
📊 Análisis estadístico
      ↓
📌 Cálculo de KPIs
      ↓
📈 Visualización
      ↓
🎯 Segmentación
      ↓
📄 Exportación CSV
      ↓
💡 Conclusiones


---


👩‍💻 Autor


Lilliana Uribe González


Proyecto académico/práctico de análisis de datos aplicado a un escenario SaaS para comercio electrónico.


---


📄 Licencia


Este proyecto se presenta con fines educativos y de aprendizaje.Este README está pensado para que el repositorio se vea profesional en GitHub, pero conservando exactamente el enfoque y los contenidos del tutorial original.tytytyutyup_counts




