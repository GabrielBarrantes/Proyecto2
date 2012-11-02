Estructuras de Datos Proyecto #2
----------------------------------
Gabriel Barrantes Rodas  201265033 &
Michael Montano Bermudez 2012
Grupo#1

----------------------------------
Introducción 
----------------------------------
  En siguiente proyecto se trata de dado un archivo de tipo kml, de la ciudad de San Jose se obtendrá de el toda la información de las calles, creando a su vez un grafo en el que cada vértice sera representado por cada intersección de carreteras en la ciudad, ademas se realizara un algoritmo para calcular el camino mas corto entre los puntos seleccionados por el usuario. Esta tarea sera implementada en el lenguaje C++, utilizando ademas el paquete FLTK para Dev-C++.

Descripción del problema 
---------------
Para la implementacion de esta tarea se presentan los siguientes problemas 

  - Lectura y Parseo del archivo KML
  - Definición de los vértices en el grafo según el KML
  - Calculo del camino mas corto 

Para la lectura del archivo KML fue utilizada una librería del lenguaje C++ que facilito leer y organizar los datos.

Para la definición de los vértices es necesario determinar cuales son los puntos en el mapa que se repiten y ademas determinar cuales puntos son adyacentes a el.

Y finalmente para el calculo del camino es necesario la implementacion de un algoritmo para el calculo del camino mas corto.

Explicación de clases y rutinas principales
--------------------------------------------
Para el desarrollo de esta tarea se ha utilizado tres componentes principares, el parseador del xml, la estructura de grafo y el algoritmo para el camino mas corto explicados mas adelante.

Parser
---------
El parser extrae las coordenadas del cuerpo del kml, primero entra a los linestrings y extrae las coordenadas, después entra a cada uno de los linestrings de las coordenadas multigeometry y agrega todas las coordenadas en un vector predefinido, luego se realiza un recorrido en el vector para determinar los vértices repetidos y adyacentes.

Estructura de Grafo utilizado
---------
La estructura utilizada fue la de matrices de adyacencia, esta implementacion tiene la limitación de no permitir una cantidad de vértices dinamica,pero fue considerada como adecuada debido a que luego de la lectura del archivo KML se conoce la cantidad de vértices de forma exacta y se sabe que la cantidad no aumentara. Ademas permite el uso del algoritmo de Floy Warshall de una forma mas efectiva.

Algoritmo de Floyd Warshall
---------------------------
Para el calculo del camino mas corto se utilizo este algoritmo, que permite el calculo el camino de todos los vértices hacia todos los vértices, dando la solución a el problema de determinar el camino mas corto.
Este algoritmo se basa en la búsqueda de distancias mas cortas por medio de tres iteradores sobre la matriz de adyacencia, ademas de crear paralelamente la matriz de distancias mínimas y la matriz de caminos mas cortos para almacenar los caminos mínimos, el primer iterador representa a todos los vértices y los otros dos representan todos los posibles caminos (los indices i,j), el algoritmo compara en cada iteracion por vértice todos los caminos posibles que puedan mejorar las distancias actuales en la matriz de distancias.

Corridas ejemplo
----------------------
 ![Ejemplo de la aplicación luego de buscar un camino](http://subir.cc/images/datos.png "")

 ![Ejemplo de camino mas corto](http://subir.cc/images/datos2.png "")

 ![Entrada de los puntos deseados](http://subir.cc/images/datos1.png "")

 ![Acercamiento de camino mas corto](http://subir.cc/images/datos3.png "")

Manual de Usuario
------------------
1- Al iniciar la aplicación se puede apreciar un menú con dos opciones, la primera permite seleccionar el archivo kml de alguna ruta del disco duro etc. en la computadora del usuario, el segundo botón permite calcular el camino mas corto una ves este cargado el kml y se hayan ingresado los puntos respectivos

2- Para su funcionamiento se cargara un kml desde el menú con el botón archivo, abrir, luego en las entradas habilitadas se ingresara el numero de punto deseado, en el espacio disponible de arriba se ingresa el punto de partida y en el segundo espacio el punto de llegada.

3- Una vez se han ingresado los dos puntos requeridos se procede a dar click en el botón Camino y la aplicación calculara y desplegara el camino deseado.


Análisis de resultados 
----------------------
Los resultados obtenidos en esta tarea fueron buenos, se implementaron casi todas las funcionalidades esperadas en la especificación, ademas se logro un manejo optimo de la estructura del grafo así como del algoritmo para la búsqueda del camino mas corto. Se consiguió un correcto uso y lectura de información del KML, lo que permitió la creación de la interfaz gráfica.

En resumen los aspectos logrados fueron el correcto uso del grafo y su algoritmo de caminos mas corto, parseo del KML y dibujo parcial de la interfaz gráfica en pantalla.

Entre los aspectos no implementados esta el zoom a la hora de visualizar el mapa y ademas de el corrimiento de la ventana (osea subir o bajar al mapa o mover lo hacia la izquierda o derecha).

Para la implementacion de estos requerimientos faltan tes es necesario una planificación mas adecuada del tiempo así como un uso mas eficiente del lenguaje de programación.

Conclusiones 
--------------
Como aspectos positivos de la realización de este proyecto están 

  - Un mejor manejo del lenguaje de programación C++ 
  - Un manejo de las estructuras de grafos ademas de algoritmos para la búsqueda del camino mas corto en los mismos
  -Un conocimiento de como manejar el DOM
  -Conocimiento en el manejo de interfaces gráficas en el lenguaje C++

Como aspectos negativos no hay ninguno destaca ble 

