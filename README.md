# 🎟️ Optimización de gastos de marketing para Showz

## 📌 Descripción del proyecto

Showz es una plataforma de venta de entradas para eventos que busca optimizar su inversión en marketing.

El objetivo de este proyecto fue analizar el comportamiento de los usuarios desde su primera visita hasta la compra, evaluar cuánto valor generan a lo largo del tiempo y determinar qué fuentes de adquisición presentan una mejor relación entre inversión y retorno.

El análisis se enfocó en responder tres preguntas principales:

- ¿Cómo utilizan los usuarios la plataforma y con qué frecuencia regresan?
- ¿Cuándo comienzan a comprar y cuánto valor generan?
- ¿Qué fuentes de adquisición presentan mejores resultados en términos de **CAC, LTV y ROMI**?

---

# 1. 🎯 Objetivo / problema de negocio

El objetivo principal fue identificar **qué fuentes de marketing generan mayor valor para Showz** y determinar dónde sería más conveniente concentrar el presupuesto publicitario.

Para ello, se analizaron métricas relacionadas con:

- comportamiento de usuarios;
- frecuencia de uso;
- conversión;
- número y valor de pedidos;
- retención;
- **Lifetime Value (LTV)**;
- **Customer Acquisition Cost (CAC)**;
- **Return on Marketing Investment (ROMI)**.

---

# 2. 📂 Datos

El análisis se realizó utilizando tres datasets correspondientes aproximadamente al periodo **junio de 2017 – mayo de 2018**.

## `visits_log_us.csv` — Visitas al sitio

Contiene información sobre las sesiones realizadas por los usuarios.

**Variables principales:**

- `Uid`: identificador único del usuario.
- `Device`: dispositivo utilizado.
- `Start Ts`: fecha y hora de inicio de sesión.
- `End Ts`: fecha y hora de finalización de sesión.
- `Source Id`: fuente de adquisición del usuario.

## `orders_log_us.csv` — Pedidos

Contiene información sobre las compras realizadas.

**Variables principales:**

- `Uid`: identificador único del cliente.
- `Buy Ts`: fecha y hora de compra.
- `Revenue`: ingreso generado por el pedido.

## `costs_us.csv` — Gastos de marketing

Contiene la inversión realizada en cada fuente publicitaria.

**Variables principales:**

- `source_id`: identificador de la fuente de adquisición.
- `dt`: fecha del gasto.
- `costs`: inversión publicitaria realizada ese día.

## Volumen de datos

El análisis incluyó aproximadamente:

- **359,400 sesiones**
- **50,415 pedidos**
- **2,542 registros de inversión publicitaria**

---

# 3. 🛠️ Herramientas y tecnologías

- **Python**
- **Pandas**
- **NumPy**
- **Matplotlib**
- **Seaborn**
- **Jupyter Notebook**
- **Análisis exploratorio de datos (EDA)**
- **Análisis de cohortes**
- **KPIs de marketing**
- **LTV**
- **CAC**
- **ROMI**

---

# 4. 🔎 Proceso de análisis

## 4.1 Preparación de los datos

Se cargaron y revisaron los tres datasets para comprobar:

- tipos de datos;
- valores ausentes;
- registros duplicados;
- estructura de las variables;
- consistencia de las fechas.

Las columnas temporales fueron convertidas a formato `datetime` para permitir análisis por día, semana, mes y cohortes.

También se generaron nuevas variables como:

- fecha de sesión;
- mes de sesión;
- duración de sesión;
- primera sesión del usuario;
- primera compra;
- tiempo hasta conversión;
- mes de adquisición;
- edad de cohorte.

---

## 4.2 Análisis de comportamiento de usuarios

Se calcularon métricas relacionadas con el uso de la plataforma:

- **DAU** — usuarios activos diarios;
- **WAU** — usuarios activos semanales;
- **MAU** — usuarios activos mensuales;
- sesiones por día;
- duración promedio de sesión;
- frecuencia de retorno de los usuarios.

---

## 4.3 Análisis de ventas y conversión

Se estudió el comportamiento de compra mediante:

- tiempo entre la primera visita y la primera compra;
- número de pedidos;
- pedidos por usuario;
- ticket promedio;
- ingresos acumulados por cliente.

---

## 4.4 Análisis de cohortes

Los usuarios fueron agrupados según su primera sesión y primera compra.

El objetivo fue analizar:

- retención;
- comportamiento a lo largo del ciclo de vida;
- evolución de los ingresos;
- **LTV acumulado por cohorte**.

---

## 4.5 Análisis de marketing

Se analizaron los gastos publicitarios desde diferentes perspectivas:

- gasto total;
- gasto por fuente de adquisición;
- evolución del gasto en el tiempo;
- **CAC por fuente**;
- **LTV por cohorte**;
- **ROMI por fuente de adquisición**.

Finalmente, se compararon las distintas fuentes para identificar cuáles presentaban mejores resultados y cuáles concentraban altos niveles de inversión sin generar un retorno proporcional.

---

# 5. 📊 Hallazgos principales

### 🔹 Retorno de usuarios

Aproximadamente **22.8% de los usuarios realizaron más de una sesión**, lo que indica una frecuencia de retorno relativamente baja.

### 🔹 Duración de las sesiones

La duración promedio de una sesión fue de aproximadamente **10.7 minutos**.

Sin embargo, debido a sesiones excepcionalmente largas, la distribución estaba sesgada.

La mediana fue aproximadamente de:

**5 minutos**

lo que representa mejor la duración típica de una sesión.

### 🔹 Conversión

La mayor parte de las conversiones ocurrió poco tiempo después de la primera visita.

Aproximadamente:

- **72% de los compradores realizaron su primera compra el mismo día**.
- Cerca de **76% compraron dentro de los primeros dos días**.

Esto indica que la mayor probabilidad de conversión ocurre durante las primeras horas o días después de la adquisición.

### 🔹 Valor de los clientes

El valor promedio acumulado por cliente fue aproximadamente:

**$6.90**

Mientras que la mediana fue aproximadamente:

**$3.05**

Esto indica una distribución desigual, donde un grupo relativamente pequeño de clientes genera ingresos significativamente mayores.

### 🔹 Inversión en marketing

El gasto total en marketing durante el periodo analizado fue aproximadamente:

**$329,132**

La **fuente 3** concentró la mayor inversión publicitaria:

**≈ $141,322**

Sin embargo, su rendimiento no fue proporcional al nivel de inversión realizado.

### 🔹 Rendimiento por fuente

Las fuentes de adquisición **1 y 2** destacaron por presentar una relación más favorable entre:

- inversión;
- ingresos;
- CAC;
- LTV;
- ROMI.

### 🔹 Retención por cohortes

El análisis mostró una fuerte concentración del valor generado durante los primeros meses después de la adquisición.

Después de este periodo, la actividad de los usuarios disminuyó considerablemente.

---

# 6. 💡 Conclusiones y recomendaciones

El análisis muestra que Showz no debería distribuir su presupuesto de marketing únicamente considerando el volumen de usuarios adquiridos.

Para evaluar correctamente el rendimiento de los canales, es necesario analizar conjuntamente:

> **CAC + LTV + ROMI + Retención**

## Recomendaciones principales

### ✅ Priorizar las fuentes 1 y 2

Estas fuentes mostraron una relación más favorable entre inversión y retorno, por lo que representan las principales candidatas para recibir una mayor proporción del presupuesto.

### ⚠️ Revisar la inversión en la fuente 3

La fuente 3 recibió la mayor inversión total, pero no produjo un retorno proporcional.

Antes de aumentar nuevamente el gasto en este canal sería recomendable revisar:

- segmentación;
- estrategia publicitaria;
- calidad del tráfico;
- costo de adquisición;
- comportamiento posterior de los usuarios.

### 🔄 Mejorar la retención

La baja frecuencia de retorno muestra que existe una oportunidad importante más allá de la adquisición.

Parte del crecimiento podría provenir de estrategias destinadas a:

- recuperar usuarios;
- aumentar compras recurrentes;
- mejorar la experiencia posterior a la primera compra;
- incrementar el valor de vida del cliente.

Por lo tanto, Showz debería combinar estrategias de **adquisición eficiente** con iniciativas enfocadas en **retención y recurrencia**.

---

# 7. 📈 Visualizaciones principales

Las visualizaciones más relevantes del proyecto fueron:

## ROMI por fuente de adquisición

Permite comparar rápidamente la eficiencia de las diferentes fuentes publicitarias y detectar cuáles recuperan mejor la inversión realizada.

## Retención por cohortes

Muestra cómo evoluciona la actividad de los usuarios durante los meses posteriores a su adquisición.

## LTV por cohorte

Permite identificar cuánto valor generan los clientes y cómo evoluciona dicho valor con el paso del tiempo.

## Tiempo hasta la primera compra

Permite visualizar qué tan rápido ocurre la conversión después de la primera visita.

---

# 8. 📁 Estructura del proyecto

```text
Showz-Marketing-Analysis/
│
├── notebook.ipynb
│
├── visits_log_us.csv
├── orders_log_us.csv
├── costs_us.csv
│
└── README.md
