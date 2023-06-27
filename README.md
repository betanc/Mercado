# Mercado
Challenge mercado libre
A continuación el detalle de las respuestas al Challenge de Mercadolibre

● Código fuente de la aplicación (Repositorio Github)
R/ En el presente repositorio

● Instrucciones para la ejecución de la aplicación (incluida cualquier aplicación o librería a
instalar para el correcto funcionamiento del programa).

R/ 
1. Se requiere tener previamente instalado, docker, github y python 3.XXX
2. Clonar de github el repositorio "Mercado"
3. Ejecutar docker-compose build
4. Ejecutar docker-compose up
5. Todas las librearias adicionales se instalaran a través de docker mediante el archivo requirements.txt.
6. Ejecutar el archivo Mercadolibre.py
7. Consultar el api a través de localhost:80


● Descripción de la aplicación realizada, supuestos, problemas y soluciones con los que se
encontró al realizar la misma con evidencias en png.

R/
Descripción de la aplicación:
1. Se toma los datos remotamente de monkapi a través de consumirserv.py y se llevana a un archivo datos.json.
2. Se ejecuta el escript parselscript.py que lo que hace es mapear los datos del archivo datos.json y organizarlos de tal forma que se puedan almacenar en un archivo data.sql para que sean incluidos y almacenados en una base de datos.

La aplicación esta desarrollada para uso en docker compose, a tracves del archivo docker compose se crean dos contenedores
1. Base de datos postgres dónde se lee el archvio data.sql con los datos organizados y se crea una base de datos llamada clientes la cual consta de dos tablas una con los  gerenales del cliente y otra con los datos de las tarjetas de crédido  las cuales se enlazan mediante una llave foranea (numero de cuenta).
2. Por otro lado se crea un contenedor que pondra en línea el api de consulta de los datos (app)

![image](https://github.com/betanc/Mercado/assets/48939055/216fb095-91f5-4110-b6c5-36ae9727e38c)


● Análisis de riesgo de la solución planteada.

