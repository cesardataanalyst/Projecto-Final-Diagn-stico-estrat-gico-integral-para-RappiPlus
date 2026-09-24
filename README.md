# 📊 RappiPlus | Diagnóstico Estratégico Integral: De Datos a Decisiones de Negocio

**Projecto Final Aprobado**

**📘 Proyecto Final – Análisis Exploratorio y Desarrollo del Caso**

Este repositorio contiene el notebook correspondiente al Proyecto Final, desarrollado durante el Bootcamp. El trabajo incluye el análisis exploratorio, la limpieza de datos, la construcción de visualizaciones y la interpretación de los resultados obtenidos a partir del dataset asignado. Con análisis claro dento de **POWER BI**

## 📌 Contexto y problema de negocio
RappiPlus busca comprender el desempeño de su operación desde diferentes perspectivas: **ventas, costos, rentabilidad, marketing, conversión y retención de usuarios**.
Para apoyar la toma de decisiones basada en datos, este proyecto integra diferentes fuentes de información y aplica técnicas de análisis con Python, SQL y Power BI.

El análisis busca responder una pregunta central:
- **¿Qué muestran los datos sobre el desempeño del negocio y el comportamiento de sus usuarios, y qué oportunidades de análisis pueden apoyar las decisiones de negocio?**

El proyecto combina análisis financiero, análisis de comportamiento digital, análisis de retención y experimentación para construir una visión integral del negocio.

## 🎯 Objetivo del análisis
El objetivo es realizar un diagnóstico integral de RappiPlus, transformando diferentes fuentes de datos en indicadores, hallazgos y recomendaciones orientadas al negocio.
El análisis busca responder:
- ¿Cuál es el desempeño financiero del negocio?
- ¿Cómo se comportan los ingresos, costos y gastos de marketing?
- ¿Cuál es el nivel de rentabilidad observado?
- ¿Cómo se comportan las ventas y el ticket promedio?
- ¿Qué productos presentan mayor volumen de ventas?
- ¿En qué etapas del funnel se concentran las pérdidas de usuarios?
- ¿Qué comportamiento presenta la retención de usuarios por cohortes?
- ¿Existe evidencia estadística de un cambio en la conversión después de modificar la interfaz del checkout?
- ¿Cómo pueden comunicarse los principales indicadores mediante un dashboard de Business Intelligence?

## 📊 Origen de los datos
El proyecto integra diferentes fuentes de información:

### 🛒 Datos de pedidos
rappiplus_orders_raw.csv
Contiene información relacionada con:
- Pedidos
- Usuarios
- Fecha y hora
- País
- Dispositivo
- Fuente de referencia
- Producto
- Categoría
- Cantidad
- Precio
- Descuentos
- Monto total

### 📦 Catálogo de productos
rappiplus_catalog.csv
Contiene información sobre:-
- Productos
- Categorías
- Costos unitarios
- Proveedores

### 📢 Inversión en marketing
rappiplus_marketing_spend.csv
Contiene información sobre:
- Fecha
- País
- Campaña
- Canal
- Gasto de marketing

### 👥 Comportamiento de usuarios
Se utilizan tablas SQL relacionadas con:
- events
- users
- user_activity

Estas tablas permiten analizar el funnel de conversión y la retención de usuarios.

### 🧪 Experimento A/B
experiment_checkout_ui.csv
Contiene información sobre el experimento de la interfaz del checkout, incluyendo:
- Usuario
- Variante
- Conversión
- Dispositivo
- País
- Duración de sesión
- Fecha

## 🛠️ Herramientas utilizadas
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- SQL
- PostgreSQL
- Jupyter Notebook
- Power BI
- Análisis estadístico
- GitHub

  ## 🔎 Metodología
El proyecto sigue un flujo progresivo que conecta calidad de datos → desempeño financiero → comportamiento de usuarios → retención → experimentación → visualización ejecutiva.

## 1️⃣ Calidad y preparación de datos
Se realizó una revisión inicial de los datasets para validar:
- Estructura y tipos de datos.
- Fechas.
- Valores nulos.
- Valores numéricos.
- Valores negativos o inválidos.
- Duplicados.
- Variables categóricas.
- Consistencia de los montos.

También se realizaron transformaciones y exportaciones de los datasets preparados para las etapas posteriores.

## 2️⃣ Análisis financiero y de rentabilidad
Se calcularon indicadores relacionados con:
- Revenue.
- Costos.
- Gasto en marketing.
- Profit.
- Ticket promedio.
- Cantidad promedio de productos por orden.
- Producto más vendido.
- Gasto de marketing por canal.

El costo de los productos se obtuvo relacionando los pedidos con el catálogo mediante el producto correspondiente.

## 3️⃣ Funnel de conversión
Se utilizaron consultas SQL para analizar el recorrido de los usuarios mediante las etapas:
first_visit
     ↓
product_page
     ↓
add_to_cart
     ↓
checkout
     ↓
purchase

Se calcularon usuarios únicos por etapa y tasas de conversión entre pasos.
Esto permite identificar dónde se producen las principales pérdidas de usuarios dentro del recorrido de compra.

## 4️⃣ Retención por cohortes
Se analizaron las tablas users y user_activity para construir cohortes según el mes de registro.
La retención se evaluó durante:
- Semana 1.
- Semana 2.
- Semana 3.

La metodología permite comparar el comportamiento de diferentes cohortes y observar cómo evoluciona la actividad de los usuarios después de su registro.

## 5️⃣ Experimento A/B
Se analizó un experimento sobre una modificación de la interfaz del checkout.

Hipótesis
H₀: la nueva interfaz no cambia la tasa de conversión.
H₁: la nueva interfaz sí cambia la tasa de conversión.

Test utilizado:

Se aplicó una prueba Z de proporciones, debido a que la variable de conversión es binaria y se comparan las proporciones de dos grupos.

Nivel de significancia utilizado:

α = 0.05.

## 📈 Principales resultados
💰 Desempeño financiero

El análisis del dataset de pedidos y catálogo obtuvo los siguientes indicadores:
- Indicador	Resultado
- Revenue total	52,024,257.56
- Costos totales	43,140,620.46
- Gasto total en marketing	2,871,843.53
- Profit	6,011,793.57
- Ticket promedio	2,072.68
- Cantidad promedio de productos por orden	7.09
- Producto más vendido	Vacuum-Pro-Black

Estos resultados corresponden directamente a las salidas calculadas en el notebook.

## 📢 Marketing
El gasto registrado por canal fue:
- Canal	Gasto
- Organic	913,533.01
- Paid Search	863,088.21
- Social	918,043.21

El análisis permite comparar la distribución de la inversión entre los diferentes canales disponibles.

## 🛒 Funnel de conversión
El análisis SQL identificó:
•	7,796 usuarios en first_visit.
•	0 usuarios en product_page.
•	7,634 usuarios en add_to_cart.
•	0 usuarios en checkout.
•	6,240 usuarios en purchase.
•	Conversión final registrada: 0.80041.

El notebook muestra además que algunas etapas intermedias presentan cero usuarios, por lo que **este resultado debe interpretarse con cautela** antes de utilizarlo para tomar decisiones sobre el comportamiento real del funnel.

Este punto es especialmente importante: el resultado evidencia una **necesidad de revisar la consistencia y definición de los eventos del funnel**, ya que una secuencia de negocio esperada contiene etapas sin registros.

## 🔁 Retención por cohortes
El análisis de cohortes muestra la retención de usuarios durante las primeras tres semanas después del registro.
Para las cohortes analizadas, los porcentajes registrados fueron:
- Cohorte	Semana 1	Semana 2	Semana 3
- Enero 2025	42.84%	41.06%	40.32%
- Febrero 2025	42.31%	42.17%	43.98%
- Marzo 2025	41.38%	43.09%	42.18%
- Abril 2025	42.34%	43.40%	41.28%
- Mayo 2025	41.20%	40.07%	41.85%

Estos resultados permiten comparar el comportamiento de las cohortes y observar diferencias en la retención semanal.

## 🧪 Resultado del experimento A/B
La conversión observada fue:
- Grupo control: 15.69%
- Grupo tratamiento: 16.29%

La prueba Z de proporciones produjo:
- Estadístico Z: -0.8133
- p-value: 0.4161

Con el nivel de significancia establecido en el proyecto (α = 0.05), el resultado no proporciona evidencia estadística suficiente para concluir que la modificación de la interfaz haya cambiado la tasa de conversión.

## 📊 Dashboard y Business Intelligence
Como etapa final, los resultados fueron preparados para su comunicación mediante Power BI.
El dashboard contempla indicadores relacionados con:
- Revenue.
- Profit.
- Marketing.
- Ticket promedio.
- Productos vendidos.
- Costos.
- Conversión.
- Análisis temporal.
- Detalle de órdenes y productos.

El objetivo del dashboard es transformar los resultados analíticos en una herramienta visual para facilitar la exploración de los principales indicadores del negocio

## 💡 Conclusiones
El análisis proporciona una visión integral de RappiPlus desde diferentes dimensiones del negocio.

1. Rentabilidad
Los datos analizados permiten observar simultáneamente ingresos, costos y gasto en marketing, proporcionando una base para estudiar el desempeño económico del negocio.

2. Ventas
El análisis identifica el comportamiento del ticket promedio, la cantidad promedio de productos por orden y el producto con mayor volumen de ventas.

3. Conversión
El funnel permite estructurar el recorrido del usuario desde la primera visita hasta la compra.
Sin embargo, la presencia de etapas con cero registros evidencia la necesidad de validar la instrumentación y consistencia de los eventos antes de utilizar el funnel como base para decisiones operativas.

4. Retención
El análisis por cohortes permite observar diferencias en el comportamiento de los usuarios durante las primeras semanas posteriores al registro.

5. Experimentación
El experimento A/B permite evaluar estadísticamente una modificación del checkout en lugar de basar la interpretación únicamente en diferencias observadas entre grupos.

## 🚀 Recomendaciones de negocio
A partir de los resultados obtenidos, se plantean las siguientes líneas de acción:

### 💰 Rentabilidad
Utilizar conjuntamente revenue, costos, profit y gasto de marketing para monitorear el desempeño económico del negocio y evaluar los resultados por producto, categoría, país y canal.

### 📢 Marketing
Profundizar el análisis de los canales de marketing relacionando inversión con resultados comerciales, de manera que futuras decisiones no dependan únicamente del nivel de gasto.

### 🛒 Funnel
Revisar la instrumentación de los eventos product_page y checkout antes de utilizar las tasas del funnel para decisiones de optimización.

### 🔁 Retención
Utilizar el análisis de cohortes como una herramienta de seguimiento periódico para detectar cambios en el comportamiento de los usuarios después del registro.

### 🧪 Experimentación
Mantener un enfoque basado en pruebas estadísticas para evaluar cambios en la experiencia de usuario antes de generalizarlos.

### 📊 Business Intelligence
Utilizar el dashboard como herramienta de seguimiento de KPIs y exploración de las principales dimensiones del negocio.

## ⚠️ Limitaciones del análisis
- Los resultados dependen de la calidad y estructura de los datos disponibles.
- Las asociaciones observadas entre variables no deben interpretarse automáticamente como relaciones causales.
- El funnel presenta inconsistencias en algunas etapas que deben revisarse antes de utilizar sus tasas como indicadores operativos.
- El experimento A/B permite evaluar el resultado de la modificación analizada dentro de las condiciones del experimento, pero no sustituye un seguimiento posterior.
- Las métricas de retención corresponden al periodo y cohortes disponibles en los datos analizados.

  ## 📁 Estructura del proyecto
Projecto-Final-Diagn-stico-estrat-gico-integral-para-RappiPlus/
│
├── README.md
│
└── S12 Estudiante_Proyecto_Final.ipynb

## ▶️ Cómo reproducir el análisis
1.	Clonar o descargar el repositorio.
2.	Abrir S12 Estudiante_Proyecto_Final.ipynb.
3.	Ejecutar las etapas del notebook en orden.
4.	Verificar la disponibilidad de los datasets utilizados.
5.	Revisar los resultados de Python y SQL.
6.	Consultar las visualizaciones y el dashboard de Power BI para complementar la interpretación.

## 📌 Key Takeaway
Este proyecto integra Python, SQL, análisis estadístico y Power BI para desarrollar un diagnóstico integral de un negocio digital.
El trabajo conecta diferentes dimensiones del negocio —rentabilidad, ventas, marketing, conversión, retención y experimentación— y transforma los resultados en indicadores y recomendaciones orientadas a la toma de decisiones.
Más que limitarse a describir los datos, el proyecto busca responder qué está ocurriendo, dónde existen puntos de atención y qué análisis o acciones pueden realizarse a partir de la evidencia disponible

👤 Autor
Cesar Palacio  
Data Analyst – Proyecto Final
