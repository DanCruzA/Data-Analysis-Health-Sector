# 📊 Análisis de Operaciones Clínicas con Python & Pandas

## 🏥 Descripción del Proyecto
Este proyecto simula un flujo de trabajo de **Ciencia de Datos e Ingeniería de Datos** aplicado al sector salud. El objetivo principal es procesar un dataset de citas médicas "sucio" (con errores típicos de captura), limpiarlo mediante un proceso **ETL** y generar visualizaciones estratégicas para la toma de decisiones.

El proyecto responde a preguntas de negocio como: *"¿Qué especialidad tiene más demanda?"* y *"¿Cuál es nuestra tasa de cancelación de citas?"*.

## 🛠️ Stack Tecnológico
* **Lenguaje:** Python 3.10
* **Manipulación de Datos:** Pandas, NumPy
* **Visualización:** Matplotlib
* **Entorno:** Jupyter Notebook

## 🚀 Características y Pipeline
### 1. Ingesta y Simulación de Datos
Se generó un dataset sintético que replica problemas reales de bases de datos clínicas:
* Fechas en formatos mixtos (ISO vs Latino).
* Valores nulos (`NaN`) en edades y fechas.
* Registros inconsistentes.

### 2. Limpieza de Datos (Data Cleaning / ETL)
El núcleo del proyecto se enfoca en la calidad del dato:
* **Manejo de Fechas Mixtas:** Se implementó lógica robusta para parsear columnas con formatos `YYYY-MM-DD` y `DD/MM/YYYY` simultáneamente.
* **Imputación:** Relleno de edades faltantes con la media poblacional y corrección de fechas nulas.
* **Estandarización:** Normalización de tipos de datos para el análisis.

### 3. Business Intelligence (KPIs)
Se calcularon métricas clave para la operación clínica:
* **Tasa de Cancelación (Churn Rate):** Cálculo del porcentaje de citas canceladas para medir la ineficiencia operativa.
* **Demanda por Especialidad:** Identificación de las áreas con mayor tráfico de pacientes.

## 🔍 Desafío Técnico Resuelto
Durante el desarrollo, se identificó un problema crítico con la función `to_datetime` de Pandas al procesar fechas en formato latino (`15/01/2024`) mezcladas con formato ISO.
* **Solución:** Se implementó el parámetro `format='mixed'` y `dayfirst=True` junto con un manejo de excepciones (`try-except`) para asegurar que ninguna fecha válida fuera descartada o malinterpretada durante la transformación.

## 📈 Visualizaciones
El notebook genera:
1.  **Gráfico de Barras:** Comparativa de volumen de pacientes por especialidad.
2.  **Gráfico de Pastel (Pie Chart):** Distribución porcentual de los estados de las citas (Atendido vs Cancelado).
