# Análisis de la Global Terrorism Database con PySpark y Koalas

Este proyecto muestra un análisis exploratorio de la base de datos Global Terrorism Database (GTD) usando PySpark y la API de Koalas (pandas-on-Spark) en Databricks.

## Pasos realizados

1. **Carga de datos**: Se importó el archivo CSV de GTD a Databricks y se cargó como un DataFrame de Spark.
2. **Conversión a Koalas**: Se utilizó la API de Koalas para trabajar con sintaxis similar a pandas, pero sobre Spark.
3. **Análisis exploratorio**: Se realizaron estadísticas descriptivas para conocer la estructura y características generales del dataset.
4. **Enfoque en United Kingdom**:
    - Se identificó que el Reino Unido (United Kingdom) tenía un número significativo de incidentes.
    - Se filtraron los datos para analizar únicamente los incidentes ocurridos en UK.
    - Se observó que el tipo de ataque más común era "Bombing/Explosion".
5. **Análisis en Belfast**:
    - Se detectó que la mayoría de los incidentes de "Bombing/Explosion" en UK ocurrieron en la ciudad de Belfast.
    - Se analizaron las tendencias anuales de este tipo de ataque en UK y se graficaron los incidentes por ciudad.
    - Se extrajeron y visualizaron los incidentes en Belfast entre 1990 y 1993, mostrando el tipo de objetivo atacado.

## Requisitos
- Databricks Free Edition
- PySpark y Koalas (pandas-on-Spark)
- Matplotlib para visualizaciones

## Ejecución
1. Sube el notebook a tu entorno de Databricks.
2. Ejecuta las celdas en orden para reproducir el análisis y las visualizaciones.

## Notas
- El análisis se puede extender a otros países, ciudades o tipos de ataque según el interés.
- El notebook está listo para ser ejecutado en Databricks y puede adaptarse fácilmente a otros entornos Spark.

## Global Terrorism Database (Kaggle)
https://www.kaggle.com/datasets/START-UMD/gtd


---

**Autor:** Héctor Sánchez
**Fecha:** Octubre 2025
