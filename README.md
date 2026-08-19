# Tecnolochicas
# 📖 Proyecto: Análisis de venta Retail en el entorno CPFR

**MODULO 2: EXPLORACIÓN DE DATOS CON PYTHON**
**MODULO 3: ANALISIS DE DATOS CON PYTHON**

## Sobre este proyecto

Este repositorio documenta el proyecto final de mi certificacion en Tecnolochicas, que integra los modulos de Procesamiento de Datos con Python y Analisis de Datos con Python.

Trabajo como analista de CPFR (Collaborative Planning, Forecasting and Replenishment) para productos hiperestacionales. Manejo informacion de aproximadamente nueve clientes, con un lead time de importacion de noventa dias, lo que significa que cualquier error en el catalogo o en la lectura de la demanda se paga caro varios meses despues. Elegi este tema para el proyecto porque me permite aplicar lo aprendido en el curso directamente a un problema real de mi trabajo, en lugar de usar un dataset generico.

Decidi documentar todo en GitHub en lugar de entregar unicamente un documento de Word, porque me parecio una buena oportunidad para empezar a trabajar con control de versiones. Esto me permitio ir guardando avances de forma progresiva, mantener un historial claro de los cambios y tener el proyecto organizado en un solo lugar, con el codigo, los datos de referencia y los graficos accesibles desde el mismo repositorio.

## El problema que busco resolver

En mi trabajo diario, la cobertura de inventario en punto de venta esta fijada en veintiocho dias para la cuenta que uso en este analisis, sin distincion entre productos de demanda estable y productos con picos marcados. Esto puede provocar dos escenarios: sobre-inventario en productos predecibles, o quiebre de stock en productos con demanda muy variable durante fechas pico.

Las preguntas que busco responder con este analisis son:

- Que productos y que tiendas concentran el mayor volumen de venta.
- En que meses o semanas se presentan los picos de demanda.
- Que tan variable es la demanda de cada SKU, y que tan predecible es cada tienda.
- Si la cobertura fija de veintiocho dias es suficiente para los productos con mayor variabilidad, o si existe riesgo de quiebre.
- Si existe una relacion de tendencia entre el tiempo y el volumen de venta que permita anticipar comportamiento futuro.

## Fuentes de datos

- Base de ventas historica de una de las cuentas que manejo (SO_SAMPLE.xmls).
- Catalogo de tiendas (Catalogo_Tienda.csv).
- Catalogo de SKUs (Catalogo-SKU.csv).

Los archivos de gran tamano (como la base de ventas completa) se excluyen del repositorio mediante .gitignore, ya que superan el limite de tamaño de GitHub. El codigo esta preparado para leerlos localmente desde la carpeta del proyecto.

## Metodologia

El analisis sigue el flujo natural de un proceso de CPFR: primero se prepara la informacion, despues se explora, se limpia, se calculan estadisticas descriptivas, se identifican patrones y finalmente se generan recomendaciones accionables.

1. Preparacion del entorno y carga de datos (CSV) desde fuentes locales.
2. Exploracion inicial de la estructura de los datos.
3. Limpieza: tratamiento de duplicados, valores nulos y formato de fechas.
4. Analisis de desempeno de productos y tiendas (top de venta, tendencia mensual, estacionalidad).
5. Consulta a base de datos relacional (MySQL) como validacion adicional de la interaccion con fuentes externas.
6. Estimaciones de locacion y variabilidad (media, mediana, moda, desviacion estandar, rango, percentiles) por SKU.
7. Identificacion de valores atipicos mediante el metodo del rango intercuartilico.
8. Clasificacion de tiendas y SKUs segun volumen y variabilidad.
9. Calculo de cobertura recomendada frente a la cobertura fija de veintiocho dias, para identificar riesgo de quiebre.
10. Correlacion y regresion lineal simple entre tiempo y volumen de venta.
11. Segmentacion de tiendas mediante un modelo de agrupamiento (K-Means).
12. Modelo de clasificacion (regresion logistica) para predecir riesgo de quiebre, evaluado con matriz de confusion.
13. Visualizaciones de apoyo para comunicar los hallazgos.

Las tecnicas de procesamiento de lenguaje natural y pruebas A/B, tambien revisadas en el curso, no se incluyeron en este proyecto porque no son pertinentes para el tipo de datos analizados, que son transaccionales y numericos. Se priorizaron en su lugar las tecnicas de correlación, regresión y clasificación, que aportan valor directo a la problematica de cobertura de inventario planteada.

## Herramientas utilizadas

- Python 3.9
- Pandas y NumPy para manipulacion de datos
- Matplotlib y Seaborn para visualizacion
- Scikit-learn para los modelos de regresion, clustering y clasificacion
- SciPy para pruebas de correlacion
- MySQL Connector para la interaccion con base de datos
- Visual Studio Code como entorno de desarrollo
- Git y GitHub para control de versiones

## Nota importante:

Este proyecto se encuentra en constante construcción, mientras mas información tenga es posible crear mejores analisis para la toma de desiciones en otros aspectos referentes al área CPFR, por lo que puede que el proyecto siga con actualización de codigo posterior a la entrega pactada.