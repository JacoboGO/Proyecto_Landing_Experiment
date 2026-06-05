# 📊 Optimización de Tasa de Conversión en Landing Page mediante Experimentación A/B

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![SQL](https://img.shields.io/badge/SQL-Análisis_de_Datos-orange.svg)](https://en.wikipedia.org/wiki/SQL)
[![Data-Driven Decisions](https://img.shields.io/badge/Decisiones-Basadas_en_Datos-green.svg)](https://en.wikipedia.org/wiki/A/B_testing)

## 📑 Tabla de Contenidos
1. [🧠 Contexto de Negocio](#-contexto-de-negocio)
2. [🎯 Objetivos](#-objetivos)
3. [🛠️ Stack Tecnológico](#️-stack-tecnológico)
4. [🔄 Flujo del Proyecto (Pipeline)](#-flujo-del-proyecto-pipeline)
5. [📁 Estructura de Archivos](#-estructura-de-archivos)
6. [🚀 Reproducibilidad](#-reproducibilidad)
7. [📈 Resultados e Insights Clave](#-resultados-e-insights-clave)
8. [💻 Buenas Prácticas Aplicadas](#-buenas-prácticas-aplicadas)
9. [🔮 Mejoras Futuras](#-mejoras-futuras)
10. [👤 Autor y Contacto](#-autor-contacto)

---

## 🧠 Contexto de Negocio
En el entorno digital, el rendimiento de la página de inicio (*landing page*) es un factor crítico que impacta directamente en el costo de adquisición de clientes (CAC) y en la rentabilidad general de la empresa. Este proyecto evalúa un **experimento A/B** implementado en dos versiones de la página de inicio (versión **A** y versión **B**) para mitigar fugas de tráfico, optimizar presupuestos de marketing y maximizar el retorno de inversión (ROI) mediante un enfoque riguroso de ingeniería y análisis estadístico de datos. Tomar una decisión basada en intuiciones en lugar de datos validados podría traducirse en pérdidas financieras severas o en una disminución del volumen de ingresos proyectados.

---

## 🎯 Objetivos
* **Explorar y validar los datos** garantizando su integridad y la ausencia de anomalías o duplicados perjudiciales para los modelos de contraste estadístico.
* **Evaluar el rendimiento financiero** comparando el gasto promedio por usuario entre la versión A y la versión B.
* **Medir la efectividad relativa** comparando analíticamente la tasa de conversión entre ambas variantes de diseño.
* **Analizar el comportamiento demográfico y de adquisición** determinando el impacto de la fuente de tráfico y el tipo de usuario sobre la tasa de conversión final.

---

## 🛠️ Stack Tecnológico
| Tecnología | Uso en el Proyecto |
| :--- | :--- |
| **Python** | Limpieza de datos, análisis exploratorio (EDA), pruebas estadísticas robustas y visualización. |
| **Pandas** | Carga, manipulación de tipos de datos (`datetime`) y estructuración de tablas agregadas. |
| **SciPy & Statsmodels** | Ejecución de pruebas estadísticas avanzadas (`ttest_ind`, `proportions_ztest`, `chi2_contingency`). |
| **Seaborn & Matplotlib** | Construcción de gráficos de distribución y barras normalizadas de conversión para la toma de decisiones de negocio. |

---

## 🔄 Flujo del Proyecto (Pipeline)
```text
Data Extraction (.csv) ➔ Data Validation & Cleaning (Python/Pandas) ➔ Statistical Testing (SciPy) ➔ Business Insights & Visualization (Seaborn)
📁 Estructura de ArchivosPlaintext├── data/
│   └── landing_experiment.csv     # Conjunto de datos con 40,000 registros de usuarios.
├── notebooks/
│   └── Landing_Experiment.ipynb   # Jupyter Notebook con el análisis y pruebas estadísticas.
└── README.md                      # Documentación ejecutiva del proyecto (este archivo).
🚀 ReproducibilidadClonar el repositorio:Bashgit clone [https://github.com/JacoboGO/Proyecto_Landing_Experiment.git](https://github.com/JacoboGO/Proyecto_Landing_Experiment.git)
cd Proyecto_Landing_Experiment
Crear e instalar el entorno virtual (venv):Bashpython -m venv venv
source venv/bin/activate  # En Windows usar: venv\Scripts\activate
Instalar las dependencias del proyecto:Bashpip install -r requirements.txt
(Nota: Asegurar la instalación de pandas, scipy, statsmodels, seaborn y matplotlib en tu archivo de requerimientos).📈 Resultados e Insights ClaveCalidad de los Datos: El dataset cuenta con 40,000 observaciones sin registros duplicados en la variable user_id, lo que valida los criterios de independencia indispensables para la aplicación de pruebas paramétricas y no paramétricas. El rango temporal analizado comprende del 1 de enero al 28 de enero de 2026.Rendimiento de Conversión por Canales (Prueba Chi-Cuadrado): Se aplicó un test de independencia de Chi-cuadrado para correlacionar la conversión con las fuentes de tráfico (traffic_source), obteniendo un estadístico de 8.662 y un p-valor de 0.034. Al ser inferior a nuestro nivel de significancia ($\alpha = 0.05$), rechazamos la hipótesis nula, demostrando una relación estadísticamente significativa. Los canales de Email (14.99%) y Ads (14.74%) mostraron una eficiencia de conversión superior frente a los canales orgánicos.Segmentación por Tipo de Usuario (Prueba Z-Test): La evaluación del comportamiento entre usuarios nuevos y recurrentes mediante un Z-test para proporciones dio un estadístico Z de 0.731 y un p-valor de 0.464. Esto indica que no hay evidencia estadística suficiente para afirmar que la veteranía del usuario afecte las tasas de conversión, por lo que esta variable se descarta como foco estratégico actual.💻 Buenas Prácticas AplicadasControl de Versiones: Uso continuo de Git Bash para la gestión de ramas, confirmación de cambios (commits) seguros y mantenimiento del código fuente en entornos remotos.Legibilidad y Estructura: Aplicación de buenas prácticas bajo estándares PEP 8, modularizando el código con funciones genéricas reutilizables y estructurando el notebook mediante bloques metodológicos limpios y autodocumentados.🔮 Mejoras FuturasAutomatización del Pipeline: Configuración de un script automatizado para la re-evaluación estadística de nuevas cohortes de tráfico semanal de forma dinámica.Modelado Predictivo: Incorporar algoritmos de clasificación (ej., Regresión Logística o Random Forest) para predecir la probabilidad de conversión y el valor de vida del cliente (CLV) en base a su región, dispositivo y canal de entrada de procedencia.👤 Autor y ContactoNombre: Jacobo Galindo OrtízPerfil: Ingeniero Químico & Analista de Datos IndustrialLinkedIn: linkedin.com/in/jacobo-galindo-ortizCorreo Profesional: ing_j_g_ortiz@hotmail.comPortafolio: github.com/JacoboGO

