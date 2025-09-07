# #Namasdata_Challenge

Repositorio del **Summer Namasdata Power BI Challenge 2025**, donde la instructora **Sara Lozano** planteó una serie de retos de Power BI en los que los datos estaban incompletos, mal modelados o requerían un parámetro especial para ser visualizados correctamente.  

*This documentation is bilingual. Español primero, English below each section.*

---

## Índice
1. [Reto 1: Productos más vendidos / 1st Challenge: Best-Selling Products](#1st-challenge-best-selling-products)  
2. [Reto 2: Ventas vs Promedio mensual / 2nd Challenge: Selling vs Monthly Average](#2nd-challenge-selling-vs-monthly-average)  
3. [Reto 3: Ventas vs Presupuesto / 3rd Challenge: Selling vs Budget](#3rd-challenge-selling-vs-budget)  
4. [Reto 4: Reuniones / 4th Challenge: Meetings](#4th-challenge-meetings)  


## 1st Challenge: Best-Selling Products  
### Reto 1: Productos más vendidos  

**ESPAÑOL**  
Una empresa quiere saber cuáles son sus productos más vendidos y cuáles están al final de la lista. Necesitan un gráfico de columnas que muestre las ventas de cada producto, filtrado por año y mes, para analizar su evolución en el tiempo.  
El reto es: descargar el dataset, analizar el contexto y construir una visualización que muestre claramente tanto los productos más exitosos como los menos vendidos.  

#### Pasos:
- Analizar e interpretar la estructura de los datos en el modelo.  
- Crear una relación 1:* desde DimProductos a FactVentas a través de IdProducto.  
- Crear una tabla de calendario y establecer inteligencia de tiempo entre DimCalendar y FactVentas.  
- Añadir dos segmentadores: uno para año y otro para mes.  
- Crear una tabla de medidas con los siguientes cálculos:  
  - Ventas: ventas totales  
  - Formato_color: formato condicional que resalta los productos más vendidos, los menos vendidos y el resto  
  - Máx, Mín y Promedio  
- Crear un gráfico de columnas con Productos en el eje Y y la medida Ventas en el eje X.  
- En la sección de color de columna (panel de formato), aplicar la medida Formato_color para resaltar los productos más y menos vendidos.  

**ENGLISH**  
A company wants to know which are its best-selling products and which ones are at the bottom of the list. They need a column chart showing the sales of each product, filtered by year and month, in order to analyze their evolution over time.  
The challenge is: download the dataset, analyze the context, and build a visualization that clearly shows both the top performers and the stragglers.  

#### Steps:
- Analyze and interpret the data structure in the model.  
- Set a 1:* relationship from DimProductos to FactVentas through IdProducto.  
- Create a calendar table and establish time intelligence between DimCalendar and FactVentas.  
- Add two slicers: one for year and another for month.  
- Create a measures table with the following calculations:  
  - Sales: Total sales  
  - Formato_color: Conditional formatting that highlights the best-selling products, the worst-selling products, and the rest  
  - Max, Min, and Average  
- Create a column chart with Products on the Y-axis and the Sales measure on the X-axis.  
- In the Column color section (Format pane), apply the Formato_color measure so that it highlights the top and bottom sellers.  



## 2nd Challenge: Selling vs Monthly Average  
### Reto 2: Ventas vs Promedio mensual  

**ESPAÑOL**  
Una empresa necesita comparar sus ventas mensuales con el promedio de ventas. El objetivo es identificar qué meses superan la media y cuáles no, para poder diseñar una estrategia de marketing para los meses con menor rendimiento.  

#### Pasos:
- Analizar e interpretar la estructura de los datos en el modelo.  
- Crear una tabla de calendario y establecer inteligencia de tiempo entre Calendar y FactVentas.  
- Crear una tabla de medidas con los siguientes cálculos:  
  - TotalVentas: todas las ventas  
  - TotalMeses: número de meses con ventas (excluyendo años)  
  - MediaVentas: promedio de ventas, filtrado por año  
  - DebajoMedia: ventas por debajo del promedio  
  - EncimaMedia: ventas por encima del promedio  
- Añadir un segmentador para la selección de año.  
- Crear un gráfico de columnas apiladas con Meses en el eje Y y las medidas DebajoMedia y EncimaMedia en el eje X, donde DebajoMedia representa ventas por debajo del promedio y EncimaMedia ventas por encima.  
- Añadir una línea de referencia usando la medida MediaVentas para mostrar la línea promedio a lo largo de los meses.  

**ENGLISH**  
A company needs to compare its monthly sales with its average sales. The goal is to identify which months surpass the average and which ones don't, so they can design a marketing strategy for the lowest-performing months.  

#### Steps:
- Analyze and interpret the data structure in the model.  
- Create a calendar table and establish time intelligence between Calendar and FactVentas.  
- Create a measures table with the following calculations:  
  - TotalVentas: All selling  
  - TotalMeses: Count of selling months, excluding years  
  - MediaVentas: Average sales, filtered by year  
  - DebajoMedia: Sales below the average  
  - EncimaMedia: Sales above the average  
- Add a slicer for year selection.  
- Create a stacked column chart with Months on the Y-axis and the measures DebajoMedia and EncimaMedia on the X-axis, so that DebajoMedia represents sales below the average and EncimaMedia represents sales above the average.  
- Add a reference line using the MediaVentas measure to display the average line across the months.  


## 3rd Challenge: Selling vs Budget  
### Reto 3: Ventas vs Presupuesto  

**ESPAÑOL**  
Una empresa quiere comparar sus ventas con el presupuesto esperado, para comprobar rápidamente qué meses alcanzaron los objetivos y cuáles no.  
El reto adicional es que el presupuesto solo está registrado por mes (no por fecha completa), lo que añade dificultad a la integración en el modelo de datos. El objetivo es unir ambas fuentes en el mismo modelo.  

#### Pasos:
- Analizar e interpretar la estructura de los datos en el modelo.  
- Crear una tabla de calendario y establecer inteligencia de tiempo entre Calendar y Real a través de la fecha.  
- Crear una tabla de medidas con los siguientes cálculos:  
  - Ventas: ventas totales  
  - Presupuesto ajustado: esta medida aplicará el filtrado, actuando como si estuviera vinculada a otra tabla usando TREATAS  
- Crear un gráfico de columnas agrupadas con Ventas en el eje Y y Fecha en el eje X.  
- Añadir dos segmentadores: ciudad y año.  
- Con la función TREATAS no es necesario crear relaciones en la vista de modelo, ya que TREATAS funciona como una simulación de relación.  

**ENGLISH**  
A company wants to compare its sales with the expected budget, so they can quickly check which months have reached the goals and which have not.  
But there's an extra challenge: the budget is registered only by month, not by full dates. This adds difficulty to the integration in the data model. The goal of this challenge is to join both sources in the same data model.  

#### Steps:
- Analyze and interpret the data structure in the model.  
- Create a calendar table and establish time intelligence between Calendar and Real through the date.  
- Create a measures table with the following calculations:  
  - Ventas: total sales  
  - Presupuesto ajustado: this measure will apply the slicing, acting as if it were linked to another table using TREATAS  
- Set a Grouped Column Chart with Ventas on the Y-axis and Date on the X-axis.  
- Set two slicers: city and year.  
- With the TREATAS function, it is not necessary to create relationships in the model view. TREATAS works as a simulation of a relationship.  



## 4th Challenge: Meetings  
### Reto 4: Reuniones  

**ESPAÑOL**  
Una empresa quiere analizar la cantidad de reuniones de sus empleados para optimizar el tiempo y ser más eficiente.  
Necesitan visualizar, en un mismo dashboard, 3 métricas clave:  
- Número de reuniones  
- Total de horas de reuniones  
- Número de asistentes  

El reto consiste en analizar estas métricas en 4 dimensiones (fecha, departamento, país y oficina) sin sobrecargar el dashboard.  

#### Pasos:
- Analizar e interpretar la estructura de los datos en el modelo.  
- Crear una tabla de medidas con los siguientes cálculos:  
  - Asistentes: total de asistentes  
  - Total Horas: la duración de las reuniones está en segundos, por lo que se debe convertir a horas  
- Crear un nuevo parámetro para filtrar entre Ciudad, País y Departamento. Esto generará una tabla dinámica que cambia según el filtro elegido.  
- Crear tres gráficos de cintas (Ribbon Charts) con Año, Mes y Fecha en el eje X, y Asistentes, Total Horas y Meetings en el eje Y (uno para cada métrica).  
- Crear tres gráficos de columnas con el parámetro creado previamente en el eje X, y Asistentes, Total Horas y Meetings en el eje Y (uno para cada métrica).  

**ENGLISH**  
A company wants to analyze the number of meetings of its employees in order to optimize time and become more efficient.  
They need to visualize, in the same dashboard, 3 key metrics:  
- Number of meetings  
- Total hours of meetings  
- Number of attendees  

The challenge consists in analyzing the metrics across 4 dimensions (date, department, country, and office) without overloading the dashboard.  

#### Steps:
- Analyze and interpret the data structure in the model.  
- Create a measures table with the following calculations:  
  - Asistentes: total attendees  
  - Total Horas: the duration of the meetings is in seconds, so we need to convert the data to hours  
- Create a New Parameter to filter between City, Country, and Department. This will create a dynamic table that changes its parameter with the chosen filter.  
- Set three Ribbon Charts with Year, Month, and Date on the X-axis, and Asistentes, Total Horas, and Meetings on the Y-axis (one chart for each metric).  
- Set three Column Charts with the Parameter you created beforehand on the X-axis, and Asistentes, Total Horas, and Meetings on the Y-axis (one chart for each metric).  
