# Poryecto Final Keep Coding
 
## Introducción
 
## Arquitectura y Validación de datos
 
## Anñalisis Exploratorio 
 
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
