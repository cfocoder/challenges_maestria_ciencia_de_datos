# Challenge Avanzado - Predicción de Precios de Acciones con PySpark y PyCaret

**Autor**: Héctor Gabriel Sánchez Pérez  
**Proyecto**: Challenge Avanzado - Maestría en Ciencia de Datos

---

## 📋 Descripción General

Este proyecto presenta un **pipeline completo de Machine Learning** para **predicción de precios de acciones** utilizando datos financieros en tiempo real. Combina las capacidades de **PySpark** para procesamiento distribuido de grandes volúmenes de datos con **PyCaret** para modelado automático de aprendizaje automático.

### 🎯 Objetivo Principal

Desarrollar un modelo predictivo robusto que pueda **anticipar el precio de cierre** de acciones de Microsoft (MSFT) basándose en datos históricos intraday (minuto a minuto), utilizando técnicas avanzas de:
- **Feature Engineering** con Window Functions de Spark
- **AutoML** con PyCaret para comparación automática de múltiples algoritmos
- **Análisis de streaming** simulado para procesamiento de datos en tiempo real

---

## 🔧 Componentes Principales

### 1. **Adquisición de Datos**
- Descarga de datos financieros reales de MSFT usando la API de `yfinance`
- Rango temporal: 7 días con intervalo de 1 minuto
- Incluye variables de OHLCV (Open, High, Low, Close, Volume)

### 2. **Procesamiento Distribuido con PySpark**
- Conversión de datos a formato Spark para escalabilidad
- Persistencia en Databricks Serverless para reproducibilidad
- **Feature Engineering distribuido** usando Window Functions:
  - Promedios móviles
  - Volatilidad calculada
  - Características técnicas de series temporales

### 3. **Análisis Exploratorio de Datos (EDA)**
- Detección de outliers y patrones anómalos
- Análisis de correlaciones entre variables
- Visualización de tendencias temporales
- Estadísticas descriptivas completas

### 4. **Modelado Predictivo con PyCaret**
- Comparación automática de **15+ algoritmos de regresión**
- Selección del mejor modelo basado en métricas de rendimiento
- Evaluación exhaustiva con múltiples métricas:
  - **R²** (coeficiente de determinación)
  - **RMSE** (Root Mean Squared Error)
  - **MAE** (Mean Absolute Error)
  - **MAPE** (Mean Absolute Percentage Error)

### 5. **Spark Streaming (Simulado)**
- Procesamiento en tiempo real con ventanas deslizantes
- Agregaciones temporales de 30 minutos con desplazamiento de 10 minutos
- Visualización de métricas por ventanas de tiempo
- Simulación de datos en streaming

### 6. **Evaluación y Validación**
- Gráficas de diagnóstico (residuos, errores, importancia de features)
- Análisis de predicciones vs valores reales
- Interpretación detallada de resultados
- Validación cruzada del modelo

---

## 📊 Estructura del Notebook

1. **Inicialización de Spark Session en Databricks**
   - Conexión a Databricks Serverless
   - Manejo de errores y reconexión automática

2. **Carga y Exploración de Datos**
   - Descarga de MSFT con yfinance
   - Conversión a Spark DataFrame
   - EDA inicial

3. **Feature Engineering**
   - Creación de características con Window Functions
   - Ingeniería de características técnicas
   - Selección de features relevantes

4. **Preparación para Modelado**
   - Limpieza de datos faltantes
   - Normalización de variables
   - División train-test

5. **AutoML con PyCaret**
   - Setup de regresión
   - Comparación de modelos
   - Selección del mejor modelo
   - Tuning de hiperparámetros

6. **Análisis de Streaming**
   - Simulación de datos en tiempo real
   - Agregaciones por ventanas temporales
   - Métricas de desempeño en línea

7. **Conclusiones y Resultados**
   - Resumen de hallazgos
   - Interpretación del modelo
   - Recomendaciones prácticas

---

## 🚀 Requisitos Técnicos

### Dependencias Python
```
pyspark>=3.0.0
pycaret>=2.3.0
yfinance>=0.2.0
pandas>=1.3.0
numpy>=1.21.0
matplotlib>=3.4.0
seaborn>=0.11.0
databricks-connect>=11.0.0 (si usas localmente)
```

### Plataforma
- **Databricks Serverless** (recomendado)
- O Python 3.8+ con Spark instalado localmente

---

## 📈 Aplicación Práctica

Este notebook es relevante para:

- **Trading Algorítmico**: Predicción de precios para decisiones automáticas de compra/venta
- **Gestión de Riesgo**: Monitoreo de volatilidad y tendencias de mercado
- **Análisis Cuantitativo**: Identificación de patrones en series temporales financieras
- **Big Data en Finanzas**: Procesamiento escalable de grandes volúmenes de datos de mercado
- **Risk Management**: Cálculo de exposición a volatilidad

---

## 🎓 Conceptos Clave Implementados

### Machine Learning
- **Regresión supervisada** para predicción continua
- **Cross-validation** para evaluación robusta
- **Feature importance** para interpretabilidad
- **AutoML** para selección automática de algoritmos

### Big Data
- **Spark DataFrames** para procesamiento distribuido
- **Window Functions** para cálculos temporales
- **Streaming** para procesamiento en tiempo real

### Finanzas
- **Análisis técnico** (promedios móviles, volatilidad)
- **Series temporales** con estructura OHLCV
- **Análisis intraday** con granularidad de minuto

---

## 📝 Notas de Ejecución

### En Databricks
1. Crea un cluster en Databricks
2. Adjunta este notebook al cluster
3. Ejecuta las celdas secuencialmente
4. La sesión Spark estará disponible automáticamente

### Localmente con databricks-connect
1. Instala `databricks-connect`
2. Configura `~/.databrickscfg` con credenciales
3. Ejecuta el notebook (la primera celda establece la conexión)

### Consideraciones de Performance
- El procesamiento de datos está optimizado para clusters de Databricks
- Los Window Functions de Spark se paralelizarán automáticamente
- PyCaret comparará múltiples algoritmos (puede tomar 5-15 minutos)

---

## 📊 Salidas Esperadas

El notebook genera:
- **Modelos entrenados** con métricas de desempeño
- **Visualizaciones** de EDA y diagnósticos
- **Predicciones** sobre datos de test
- **Análisis de importancia de features**
- **Reporte completo** de resultados

---

## 🔗 Referencias

- [PySpark Documentation](https://spark.apache.org/docs/latest/api/python/)
- [PyCaret Documentation](https://pycaret.org/)
- [Databricks Connect](https://docs.databricks.com/en/dev-tools/databricks-connect/index.html)
- [yfinance Documentation](https://github.com/ranaroussi/yfinance)

---

## 📄 Archivos en la Carpeta

- `Challenge_Avanzado_Pycaret2.ipynb` - Notebook principal del proyecto
- `Challenge_Avanzado_Descripcion.md` - Descripción detallada adicional
- `pyproject.toml` - Configuración de dependencias del proyecto
- `README.md` - Este archivo

---

## ✅ Estatus del Proyecto

**Fase**: Completo  
**Última actualización**: Noviembre 2025  
**Autor**: Hector Gabriel Sánchez Pérez

---

## 📧 Contacto

Para preguntas o comentarios sobre este proyecto, por favor contacta al autor.

---

*Este proyecto es parte del programa de **Maestría en Ciencia de Datos** y demuestra la aplicación práctica de tecnologías modernas (Databricks Serverless, PySpark, AutoML) a problemas reales del mundo financiero.*
