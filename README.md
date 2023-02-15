# Proyecto Final eepconding - Glovo Women in Tech 
Sep-Feb 2023

Grupo Globo-Data: Judit Gómez, Maria Gimenez, MariaAguila, Alba Albaurrea, Paula Gual
 
## Introducción
 
## Arquitectura y Validación de datos
Durante la exploración inicial de los datos recabamos la información necesaria para proceder al siguiente paso y empezar a perfilar lo que será el Data Warehouse.

En la definición de atributos, decidimos desglosar la información en cuatro grupos relevantes para nuestro análisis: la propiedad, englobando toda la información directamente relacionada con ésta; el host, para poder analizar lo relativo a los propietarios y sus características; el tipo de propiedad y sus características; y la localización.

Una vez obtenido el esquema inicial nos pusimos manos a la obra para plasmarlo en la base de datos. Primero, creando las tablas que formarían el Data Warehouse tal y como estaba diseñado en el modelo. Y, posteriormente, resolviendo el escollo de la importación de datos a cada una de las tablas desde el dataset original.

![Esquema SQL](https://github.com/paulagual/Proyecto-Final-Keepcoding/blob/main/img/Esquema-SQL.png?raw=true)

## Analisis Exploratorio 

Este estudio tiene como finalidad principal realizar un análisis detallado de los alojamientos en Airbnb en la ubicación de Madrid. Se busca comprender de manera más profunda si existe alguna relación entre el precio de los alojamientos y diversos factores como, por ejemplo, la ubicación en un vecindario determinado, las características de los alojamientos, entre otros. Además, se pretende identificar patrones y tendencias en el comportamiento de los precios, para poder comprender mejor los aspectos que los influyen.

Se han limpiado los datos, y posteriormente analizado las columnas más relevantes de las que contiene el dataset. 

Además se han estudiado las diferentes palabras contenidas en los anuncios de los alojamientos, tanto las más caras, como las más baratas, lo que nos puede dar una idea de su influencia en el precio.

![Wordcloud](https://github.com/paulagual/Proyecto-Final-Keepcoding/blob/main/img/wordcloud.png?raw=true)
 
## Visualización de las métricas
 
## Preproceso y Modelado
 
### Preproceso
En el preproceso, con las variables existentes hemos creado un número de features nuevas que creemos que nos pueden ayudar en el modelado.
 
### Feature Selection
Para probar diferentes modelos, hemos creado diferentes datasets con subsets de datos. Algunos de los datasets creados son: features numericas, features numericas y categoricas, features numericas reducidas.

### Modelado

Tal y como pedía el enunciado hemos realizado un modelo con el algoritmo LinearRegression para predecir la variable Price.
Para ello, hemos probado modelos con los diferentes subsets de las features, además también hemos probado a tansformar la variable target por log(target) y finalmente hemos creado nuevas features con Polynomial Features en grado 2.

### Resultados
El modelo finalmente seleccionado en el de features solo numericas, y sólo realcionadas con el alojamiento, ya que lo que pretendemos es que los propietarios de alojamientos de AirBnb puedan estimar el precio dadas las características del alojamiento.

Cross Validation

MAE: 21,67

RMSE: 38,77

R2:0,520


## Conclusiones
