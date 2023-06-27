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

![image](https://github.com/betanc/Mercado/assets/48939055/e5b66ead-20d1-47ea-abc8-5cc3e766dc3e)


● Análisis de riesgo de la solución planteada.




<meta http-equiv="Content-Type" content="text/html; charset=utf-8"><link type="text/css" rel="stylesheet" href="resources/sheet.css" >

<div class="ritz grid-container" dir="ltr"><table class="waffle" cellspacing="0" cellpadding="0"><thead><tr><th class="row-header freezebar-origin-ltr"></th><th id="2109673975C0" style="width:100px;" class="column-headers-background">A</th><th id="2109673975C1" style="width:254px;" class="column-headers-background">B</th><th id="2109673975C2" style="width:432px;" class="column-headers-background">C</th><th id="2109673975C4" style="width:437px;" class="column-headers-background">E</th><th id="2109673975C13" style="width:100px;" class="column-headers-background">N</th><th id="2109673975C14" style="width:100px;" class="column-headers-background">O</th><th id="2109673975C15" style="width:100px;" class="column-headers-background">P</th></tr></thead><tbody><tr style="height: 20px"><th id="2109673975R0" style="height: 20px;" class="row-headers-background"><div class="row-header-wrapper" style="line-height: 20px">1</div></th><td class="s0" dir="ltr" rowspan="2">ID</td><td class="s1" rowspan="2">Risk</td><td class="s1" rowspan="2">Description</td><td class="s1" rowspan="2">Recommendations</td><td class="s2" dir="ltr" colspan="3">Evaluation</td></tr><tr style="height: 20px"><th id="2109673975R1" style="height: 20px;" class="row-headers-background"><div class="row-header-wrapper" style="line-height: 20px">2</div></th><td class="s2">PROB</td><td class="s2">IMP</td><td class="s2">WM</td></tr><tr style="height: 20px"><th id="2109673975R2" style="height: 20px;" class="row-headers-background"><div class="row-header-wrapper" style="line-height: 20px">3</div></th><td class="s3" dir="ltr">R1</td><td class="s4" dir="ltr">Confidencialidad de la información (externo)</td><td class="s4" dir="ltr">Los datos se entregan en texto claro a través de internet (monkapi)</td><td class="s4" dir="ltr">Usar una Api local que permita extraer los datos y tratarlos brindandoles seguridad</td><td class="s5" dir="ltr">H</td><td class="s5" dir="ltr">M-H</td><td class="s6" dir="ltr">H M-H</td></tr><tr style="height: 20px"><th id="2109673975R3" style="height: 20px;" class="row-headers-background"><div class="row-header-wrapper" style="line-height: 20px">4</div></th><td class="s3" dir="ltr">R2</td><td class="s4" dir="ltr">Confidencialidad de la información </td><td class="s4" dir="ltr">Los datos de los usuarios como identificaciones y cuentas, compras y datos financieros se entregan en un mismo contexto</td><td class="s4" dir="ltr">Segregar el acceso<br>Cifrar datos financieros<br>Separar los datos de acuerdo a los roles y perfiles que consultan los datos y las necesidades</td><td class="s5" dir="ltr">H</td><td class="s5" dir="ltr">M-H</td><td class="s6" dir="ltr">H M-H</td></tr><tr style="height: 20px"><th id="2109673975R4" style="height: 20px;" class="row-headers-background"><div class="row-header-wrapper" style="line-height: 20px">5</div></th><td class="s3" dir="ltr">R3</td><td class="s4" dir="ltr">Confidencialidad e integridad de los datos en base de datos</td><td class="s4" dir="ltr">Los datos que se consumen desde el api no se encuetran estrucuturados y con control de acceso, roles y perfiles.</td><td class="s4" dir="ltr">Mantener el control de quienes y para que accesden a la información, llevar roles y pefiles de aplicación y base de datos</td><td class="s7" dir="ltr">L-M</td><td class="s7" dir="ltr">L-M</td><td class="s8" dir="ltr">L-M L-M</td></tr><tr style="height: 20px"><th id="2109673975R5" style="height: 20px;" class="row-headers-background"><div class="row-header-wrapper" style="line-height: 20px">6</div></th><td class="s3" dir="ltr">R4</td><td class="s4" dir="ltr">Disponibilidad y confidencialidad de la información de Consumo del api y base de datos</td><td class="s4" dir="ltr">No se tiene claramente definido quienes y para que usan los datos tanto externa como internamente </td><td class="s4" dir="ltr">Crear un módulo adicional de roles y perfiles</td><td class="s5" dir="ltr">M-H</td><td class="s5" dir="ltr">M-H</td><td class="s9" dir="ltr">M-H M-H</td></tr><tr style="height: 20px"><th id="2109673975R6" style="height: 20px;" class="row-headers-background"><div class="row-header-wrapper" style="line-height: 20px">7</div></th><td class="s3" dir="ltr">R5</td><td class="s4" dir="ltr">Confidencialidad y Disponibilidad de los datos</td><td class="s4" dir="ltr">Almacenamiento persistente de los datos y consulta de datos</td><td class="s4" dir="ltr">Mantener copia de los datos entregados por el api externa.</td><td class="s7" dir="ltr">L-M</td><td class="s7" dir="ltr">L-M</td><td class="s8" dir="ltr">L-M L-M</td></tr><tr style="height: 20px"><th id="2109673975R7" style="height: 20px;" class="row-headers-background"><div class="row-header-wrapper" style="line-height: 20px">8</div></th><td class="s3" dir="ltr">R6</td><td class="s4" dir="ltr"></td><td class="s4" dir="ltr"></td><td class="s4"></td><td class="s7" dir="ltr">M-H</td><td class="s7" dir="ltr">M-H</td><td class="s9" dir="ltr">M-H M-H</td></tr><tr style="height: 20px"><th id="2109673975R8" style="height: 20px;" class="row-headers-background"><div class="row-header-wrapper" style="line-height: 20px">9</div></th><td class="s3" dir="ltr">R7</td><td class="s4" dir="ltr"></td><td class="s4" dir="ltr"></td><td class="s4" dir="ltr"></td><td class="s10" dir="ltr">L</td><td class="s10" dir="ltr">H</td><td class="s9" dir="ltr">L H</td></tr><tr style="height: 20px"><th id="2109673975R9" style="height: 20px;" class="row-headers-background"><div class="row-header-wrapper" style="line-height: 20px">10</div></th><td class="s3" dir="ltr">R10</td><td class="s4" dir="ltr"></td><td class="s4" dir="ltr"></td><td class="s4" dir="ltr"></td><td class="s7" dir="ltr">H</td><td class="s7" dir="ltr">H</td><td class="s6" dir="ltr">H H</td></tr></tbody></table></div>
