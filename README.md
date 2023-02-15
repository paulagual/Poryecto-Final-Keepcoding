# Proyecto Final eepconding - Glovo Women in Tech 
Sep-Feb 2023

Grupo Globo-Data: Judit Gómez, Maria Gimenez, MariaAguila, Alba Albaurrea, Paula Gual
 
## Introducción

En base al data set inicial, nuestro objetivo principal era resolver la pregunta de aquellos propietarios madrileños que quieren publicar sus inmuebles o estancias en Airbnb:
**¿Qué precio debo ponerle a mi publicación?**
Para ello, realizaremos una exploración inicial de los datos, seguida de la creación e implementación del modelo entidad-relación para elaborar el Data Warehouse. Partiendo de este punto, a través de los datos nos pusimos manos a la obra para realizar un análisis detallado centrándonos en Madrid. 
Finalmente, crearemos un modelo de predicción que permitirá fácilmente conocer el precio recomendado. Siempre teniendo en cuenta los factores estrechamente relacionados con el valor de mercado del inmueble, más allá de los precios en la ciudad. 


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

El objetivo de este apartado es realizar un dashboard que permita al anfitrión una visualización sencilla de cómo está el mercado para poder posicionarse en él, tanto en precio como en tipo de habitación que desea ofrecer al inquilino.

Para el Dashboard hemos creado diferentes vistas y filtros. En cuanto a vistas, vemos los nombres y precios de las distintas propiedades que cumplen los filtros, además de la situación en el mapa de dichos alojamientos y los tipos de propiedades de esos alojamientos. En cuanto a los filtros, podemos seleccionar el vecindario, el tipo de habitación y el rango de precios.

![Dashboard](https://github.com/paulagual/Proyecto-Final-Keepcoding/blob/main/img/Dashboard.png?raw=true)
 
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

![Residuals final model ](https://github.com/paulagual/Proyecto-Final-Keepcoding/blob/main/img/residuals-reduced-model.png?raw=true)


## Conclusiones
