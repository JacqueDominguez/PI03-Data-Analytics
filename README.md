# Analisis de Competencia del Mercado de Cursos Masivos Online(MOOC) 
</div>
Bienvenido! En esta oportunidad vamos a analizar 3 datasets de empresas importantes del mercado de MOOCs para generar una recomendación al cliente que desea sumarse al negocio. 
<div>
<img src="https://thumbs.dreamstime.com/z/mooc-masivo-curso-online-abierto-aprendizaje-en-l%C3%ADnea-vectores-219370657.jpg?resize=1500%2C720&quality=80&ssl=1" width="250px">
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/97/Coursera-Logo_600x600.svg/1200px-Coursera-Logo_600x600.svg.png" resize=1000%2C720&quality=80&ssl=1" width="130px">
<img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTiFL0FeLWJE_qznLD0gBH2eyM8G5dYzdD_mRUvfggn14qvDUBsakyNxT5jAKeQdGF56P0&usqp=CAU" resize=1000%2C720&quality=80&ssl=1" width="200px">
<img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcR6pnP7ogI1KRCFoUL93oXbQGOabDnIkhIxZ2lsGzdxdJ2G88dSYh8ja7gJw4j9Uhwm-Cs&usqp=CAU" resize=1500%2C720&quality=80&ssl=1" width="250px">



</div>

## Pero..¿Qué es MOOC?

MOOC es el acrónimo de ***Massive Open Online Course***, que puede traducirse al español como curso en línea masivo y abierto. Se trata de una modalidad de cursos on line con dos características principales la masividad y el acceso a los contenidos y a la realización de las actividades debe ser gratuito , aunque los servicios de consulta y certificados pueden ser pagos.

</div>

## Objetivos del proyecto

+	Explorar los datasets provenientes de tres empresas importantes del mercado de MOOCs: Coursera, EDX y Udemy.
+	Transformar los datos para hacer posible su análisis.
+	Analizar e interpretar los datos para extraer conclusiones.
+	Elaborar un dashboard interactivo con los datasets. 
+	Comunicar las conclusiones obtenidas mediante un informe. 


</div>

## Fuente de datos

Para realizar este trabajo se utlizaron cuatro archivos .csv ubicados en la carpeta [Datasets](/Datasets).

<div>

<img src="https://internetpasoapaso.com/wp-content/uploads/Archivo-extension-CSV.jpg?resize=600%2C720&quality=80&ssl=1" width="100px">
<img src="https://cloudfront-us-east-1.images.arcpublishing.com/infobae/CHKO7CX4ZBFNBM765KEEGTBHJ4.jpg" width="200px">

</div>

## Pasos a seguir:

### 1- Extraccion y Análisis exploratorio de datos (EDA) en el dataset de Train:

Para ello utilicé Python , más especificamente las librerias pandas y numpy para el análisis de los datos y matplotlib y seaborn para las representaciones gráficas (podras encontrar todo el código dentro del notebook [EDA.ipynb](/EDA.ipynb).

Algunos de los hallazgos más destacados fueron: 

+ El dataset posee 346479 filas y 22 columnas, solo posee nulos en 4 columnas y solo en una (parking_options) los nulos superan el 25% de los datos.
+ Errores en los datos de latitud y longitud , los valores fuera del rango esperado son menores al 1% (no significativos)
+ Filas duplicadas: existen y representan mas del 20% del dataset por lo que consideramos que se deben eliminar. 
+ Tipo de dato incorrecto: la columna baths tiene un tipo de dato float que debe corregirse a entero. 
+ Valores Atipicos o Outliers: analizando las columnas bath y beds vemos que hay valores extraños (>10) .Para el caso de Price y Sqfeet no solo hay grandes outliers sino también valores iguales a cero. 
+ Variables Categóricas: solo hicimos hincapié en su composición. 

### 2- Preprocesamiento y transformación del dataset de Train:

Para ello utilicé Python , más especificamente las librerias pandas y numpy y sklearn para la transformación de los datos y matplotlib y seaborn para las representaciones gráficas (podrás encontrar todo el código dentro del notebook [PreprocesamientoTrain.ipynb](/PreprocesamientoTrain.ipynb).

Este es un resumen del paso a paso:

+ Completar valores nulos de laundry_options y parking_options con la moda por tipo de propiedad. 
+ Completar los valores de latitud y longitud . 
+ Realizar las correcciones de tipo de dato y valores atípicos declaradas en el punto anterior. 
+ Crear la columna que representa la variable objetivo a partir de la columna precio. 
+ Eliminar las columnas que no utilizaremos en el modelo.

### 3- Definir el modelo y entrenarlo

Teniendo en cuenta que nuestra variable objetivo es categórica decidimos ,en primer lugar, utilizar un modelo de aprendizaje supervisado , es decir le mostramos al modelo el resultado que esperamos de la variable objetivo, para ello utilizamos Arbol de Decisión , por ser uno de los mas simples y fáciles de entender, todo lo desarrollamos en python con ayuda de la libreria scikit-learn. 

El desarrollo del modelo podra encontrarlo aquí [Modelo01.py](/Modelo01.py) .

Este es un resumen del paso a paso:

+ Extraer los datos del dataset.
+ Separar los datos en train y test.
+ Entrenar el modelo. 
+ Realizar la predicción.
+ Evaluar el modelo , en este caso tenemos un ***Accuracy:  0.9088 y un Recall:  0.883***

</div>

## 4-Transformación del Test. 

Para ello utilicé Python , más especificamente las librerias pandas y numpy y sklearn para la transformación de los datos y matplotlib y seaborn para las representaciones gráficas (podras encontrar todo el código dentro del notebook [PreprocesamientoTest.ipynb](/PreprocesamientoTest.ipynb). ***Aclaración: debe tener la misma cantidad de columnas que el dataset train***

Este es un resumen del paso a paso:

+ Completar valores nulos de laundry_options y parking_options con la moda por tipo de propiedad. 
+ Completar los valores de latitud y longitud . 
+ Eliminar las columnas que no utilizaremos en el modelo.
+ Agregar las columnas que le faltan. 

</div>

## 4- Predecir los valores del dataset de testeo. 

Corremos nuestro modelo en el dataset [df_test_final.py](/df_test_final.py).

El desarrollo del modelo podra encontrarlo aquí [ModeloTest.py](/ModeloTest.py) .

Este es un resumen del paso a paso:

+ Extraer los datos de ambos dataset.
+ Separar los datos en entrenamiento y testeo.
+ Entrenar el modelo. 
+ Enviar la [prediccion](/JacqueDominguez.csv) para su evaluación.
+ Resultados Obtenidos : ***Accuracy:  0.928 y un Recall:  0.922***

</div>

## CONCLUSIONES 

A partir del exhaustivo análisis de los datos y observando esta [imagen](https://drive.google.com/file/d/1sXDBy_M6Krmea51ccPdIxXrCrLK8a3WD/view?usp=share_link) podemos concluir:

+ Que la variable más imortante para definir el precio en el mercado inmobiliario analizado es el tamaño de la propiedad. 
+ Que la segunda variable de más importancia es la ubicación. 
+ Recomendación: Si se encuentra ante la decisión de invertir en una proiedad esos dos atributos deben ser los de mayor peso en su análisis comparativo. 

</div>

## Puntos de mejora
Los puntos a mejorar  de este proyecto son :
+ Realizar un modelo de aprendizaje no supervisado.
+ Implementar un analisis de PCA para reducir la cantidad de variables.
+ Avanzar hacia un modelo de aprendizaje supervisado mas complejo.
+ Implementar piplines.

</div>


## Tecnologías Utilizadas

* [Python](https://www.python.org/)
* [Pandas](https://pandas.pydata.org/)
* [Scikit-learn.](https://scikit-learn.org/stable/)
* [Matplotlib](https://matplotlib.org/stable/index.html)
* [Seaborn](https://seaborn.pydata.org//)
* [Colab](https://colab.research.google.com/?hl=es)

</div>

## Para realizar este proyecto las siguientes fuentes de información fueron de gran ayuda: 

+ Los cuadernos del Módulo 6 de la carrera de Data Science de Henry.
+ Las clases de los profes Pablo Romero y Juanse Parra del Módulo 6 de la carrera de Data Science de Henry.
+ https://deepnote.com/@mazzaroli/Analisis-exploratorio-de-datos-caba7762-e435-481e-9060-523263a820b1
