# TelecomX_LATAM
Telecom X - Análisis de Evasión de Clientes Como asistente de datos en Telecom X, trabajarás en el proyecto 'Churn' para reducir cancelaciones. Analizarás datos con Python y sus bibliotecas, identificando patrones clave. Tus hallazgos ayudarán al equipo de Data Science a crear modelos predictivos y estrategias de retención.

📊 Análisis de Churn en Telecomunicaciones
Este proyecto realiza un análisis completo de la evasión de clientes (Churn) en una empresa de telecomunicaciones, identificando patrones y factores clave que influyen en la cancelación de servicios.

📌 Objetivos
Identificar variables asociadas al abandono de clientes

Analizar segmentos de clientes con mayor riesgo de Churn

Proponer estrategias para reducir la tasa de evasión

📦 Requisitos
Python 3.8+

Bibliotecas:

bash
pip install pandas numpy matplotlib seaborn requests scipy
🛠️ Estructura del Proyecto
text
telecom-churn-analysis/
├── data/
│   ├── TelecomX_Data.json              # Datos originales
│   ├── telecomx_clientes_flat.csv      # Datos normalizados
│   └── telecom_data_corregido.csv      # Datos limpios
├── notebooks/
│   └── churn_analysis.ipynb            # Análisis completo
├── reports/
│   └── informe_churn.pdf               # Reporte ejecutivo
└── README.md
🚀 Uso
Cargar y preparar datos:

python
import requests
import pandas as pd

url = "https://raw.githubusercontent.com/ingridcristh/challenge2-data-science-LATAM/main/TelecomX_Data.json"
response = requests.get(url)
data = response.json()
df = pd.json_normalize(data)
Ejecutar análisis exploratorio:

python
# Ver distribución de Churn
print(df['Churn'].value_counts(normalize=True))

# Análisis por tipo de contrato
print(df.groupby('Contract')['Churn'].value_counts(normalize=True))
Generar visualizaciones:

python
import seaborn as sns
import matplotlib.pyplot as plt

sns.countplot(data=df, x='Contract', hue='Churn')
plt.title('Churn por Tipo de Contrato')
plt.show()
🔍 Principales Hallazgos
Tasa global de Churn: 26.5%

Factores clave:

Contratos mensuales tienen 3× más Churn que anuales

Usuarios de fibra óptica presentan 42% de evasión

Clientes nuevos (<6 meses) son 4× más propensos a cancelar

📈 Visualizaciones Clave
https://images/churn_distribution.png
https://images/tenure_churn.png

📝 Recomendaciones
Fidelización: Incentivar contratos anuales con descuentos

Fibra óptica: Investigar causas de insatisfacción

Intervención temprana: Programas para clientes nuevos

📊 Métricas Clave
Métrica	Valor	Insight
Tasa Global de Churn	26.5%	Oportunidad de mejora
Churn Contrato Mensual	43%	Enfoque en conversión
Antigüedad Media (Churn)	18 meses	Clientes nuevos más vulnerables
