# Analisis de Competencia del Mercado de Cursos Masivos Online(MOOC) 
</div>
Bienvenido! En esta oportunidad vamos a analizar 3 datasets de empresas importantes del mercado de MOOCs para generar una recomendación al cliente que desea sumarse al negocio. 
<div>
<img src="https://d3njjcbhbojbot.cloudfront.net/api/utilities/v1/imageproxy/https://coursera.s3.amazonaws.com/media/coursera-rebrand-logo-square.png?auto=format%2Ccompress&dpr=1"resize=100%2C720&quality=80&ssl=1" width="100px">
<img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTiFL0FeLWJE_qznLD0gBH2eyM8G5dYzdD_mRUvfggn14qvDUBsakyNxT5jAKeQdGF56P0&usqp=CAU" resize=100%2C720&quality=80&ssl=1" width="170px">
<img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcR6pnP7ogI1KRCFoUL93oXbQGOabDnIkhIxZ2lsGzdxdJ2G88dSYh8ja7gJw4j9Uhwm-Cs&usqp=CAU" resize=1000%2C720&quality=80&ssl=1" width="250px">



</div>

## Pero..¿Qué es MOOC?

MOOC es el acrónimo de ***Massive Open Online Course***, que puede traducirse al español como curso en línea masivo y abierto. Se trata de una modalidad de cursos on line con dos características principales la masividad y el acceso a los contenidos y a la realización de las actividades debe ser gratuito , aunque los servicios de consulta y certificados pueden ser pagos.
<div>
<img src="https://thumbs.dreamstime.com/z/mooc-masivo-curso-online-abierto-aprendizaje-en-l%C3%ADnea-vectores-219370657.jpg?resize=1500%2C720&quality=80&ssl=1" width="350px">
</div>

## Objetivos del proyecto

+	Explorar los datasets provenientes de tres empresas importantes del mercado de MOOCs: Coursera, EDX y Udemy.
+	Transformar los datos para hacer posible su análisis.
+	Analizar e interpretar los datos para extraer conclusiones.
+	Elaborar un dashboard interactivo con los datasets. 
+	Comunicar las conclusiones obtenidas mediante un informe. 


</div>

## Fuente de datos

Para realizar este trabajo se utlizaron cuatro archivos .csv ubicados en la carpeta [Datasets](/Datasets) o en la carpeta de de Google Drive con el nombre de [Coursera_reviews](https://drive.google.com/drive/folders/15X7M8hhcVMkZF_9uFEfB7u-nPBA5lYjY?usp=share_link) .

<div>

<img src="https://internetpasoapaso.com/wp-content/uploads/Archivo-extension-CSV.jpg?resize=600%2C720&quality=80&ssl=1" width="100px">

</div>

## Pasos a seguir:
                                                                                                                                     
![Flujo](https://github.com/JacqueDominguez/PI03-Data-Analytics/blob/main/src/assets/flujo.jpg)                                                                                                                                     
                                                                                                                                     
                                                                                                                                     
### 1- Análisis exploratorio de datos (EDA) y preprocesamiento

Para ello utilicé Python , más especificamente las librerias pandas y numpy para unificar los datasets de Coursera y realizar el análisis de los datos , podrás encontrar todo el código dentro de éste notebook [EDA](/EDA.ipynb).

Algunos de los hallazgos más destacados fueron: 

+ El dataset de Corusera posee 1.454.711 filas y 8 columnas, solo posee 140 datos nulos y una única variable numérica (rating).
+ El dataset de EDX posee 975 filas y 16 columnas, posee 777 datos nulos y todas sus variables son tipo objeto.
+ El dataset de Udemy posee 3678 filas y 12 columnas, no posee datos nulos y la mitad del dataset es de datos numéricos.
+ Completé los datos faltantes con 'Sin_Dato' o 0  segun corresponda. 
+ Analicé los valores únicos que asume cada variable. 
+ Transformé los tipos de datos de las columnas correspondientes. 
+ Apliqué la función split para extraer de las columnas tipo object los datos numéricos(duración y precio) 
+ Los duplicados eran en Coursera: 934.764, en EDX: 1, en Udemy: 6, pueden afectar el análisis por lo que se eliminan.
+ Eliminé las columnas que no son significativas para el análisis. 
+ Generé 3 archivos que me servirán de base para realizar el dashboard. 

### 2- WordCloud : realización de una nube de palabras

Para ello utilicé Python , más especificamente las librerias pandas y numpy para unificar los titulos en un único dataframe y nltk realizar limpieza de palabras con la función stopwords que elimina palabras insignificantes. Para poder convertirlo en una figura usé la librería matplotlib (podras encontrar todo el código dentro de éste notebook [nubedepalabras](/nubedepalabras.ipynb).

### 3- Dashboard con PowerBI 
 
Se incluyeron los archivos generados en el punto 1 y la nube de palabras del punto 2 en un dashboard interactivo que funciona al mismo tiempo como soporte visual de la presentación del análisis , podrás descargarlo de esta carpeta de Google Drive con el nombre de [Informe](https://drive.google.com/drive/folders/15X7M8hhcVMkZF_9uFEfB7u-nPBA5lYjY?usp=share_link).                                                                              
     
</div>

## CONCLUSIONES 

A partir del exhaustivo análisis de los datos y observando con detenimiento el dashboard interactivo podemos concluir:

+ Durante el 2020 se ***triplicaron las reseñas***.
+ Las instituciones con mejores puntajes son **Universidades** y empresas como ***Google e IBM***.
+ La ***Demanda*** valora más un curso de nivel ***Avanzado*** mientras que la ***Oferta*** de se concentra en el nivel ***Principiante***.
+ Los temas que más ingresos generan son ***Computer Science y Web Development***.
+ En niveles avanzados prefieren ***Business Finance  y Data Analysis***.
+ Los cursos ***gratuitos*** son una buena opción para atraer suscriptores. 


</div>

## Puntos de mejora del Proyecto
                                                                                                                                       
Los puntos a mejorar  de este proyecto son :
                                                                                                                                     
+ Incliur información de datasets complementarios.

</div>


## Tecnologías Utilizadas

* [Python](https://www.python.org/)
* [Pandas](https://pandas.pydata.org/)
* [PowerBI](https://powerbi.microsoft.com/es-es/)
* [Matplotlib](https://matplotlib.org/stable/index.html)
* [WordCloud](https://pypi.org/project/wordcloud/)
* [NLTK](https://www.nltk.org/)

</div>

## Para realizar este proyecto las siguientes fuentes de información fueron de gran ayuda: 

+ Las clases de los profes Cristian Castro y Juanse Parra del Módulo 5 de la carrera de Data Science de Henry.
+ https://github.com/afernandez119/wordcloud/blob/main/Wordcloud_Medium.ipynb
+ https://www.youtube.com/watch?app=desktop&v=6PtsGT0tBdg
+ https://www.youtube.com/watch?v=sjrlIAQnD8M                                                                                                                                     
                                                                                                                                     
