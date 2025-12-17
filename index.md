<img src="logo_UCO.png" style="width:10.0%" /> DIVERSIDAD DE MALAS
HIERBAS EN CAMPOS AGRÍCOLAS EUROPEOS
<img src="Logotipo_FC.png" style="width:10.0%" />

================
Lorena Jiménez Jiménez, Francisco Solano Jurado Molina y Julia Lázaro
Zapata
2025-12-17

<!-- Configuramos las opciones globales y cargamos las librerías -->

# <span style="color: darkred;">INTRODUCCIÓN</span>

Existe gran diversidad de malas hierbas en los sistemas agrícolas
europeos, lo cual ofrece un escenario ideal para comprender tanto el
funcionamiento de los agroecosistemas como los desafíos de la
conservación de la biodiversidad vegetal. Aunque estas especies suelen
considerarse problemáticas desde un punto de vista productivo, su
presencia, distribución y estado de conservación están estrechamente
ligados a muchos factores distintos, (ecológicos, climáticos y
territoriales) lo que las convierte en un objeto de estudio relevante
desde una perspectiva ambiental.

Por tanto, este trabajo consiste en el análisis de un conjunto de datos
de carácter taxonómico y ecológico que recoge información sobre especies
de malas hierbas registradas en Francia. A partir de este dataset, se
pretende obtener una visión general de la composición de las especies y
su procedencia biogeográfica, así como su estado de conservación,
sentando las bases para un análisis descriptivo y estadístico que
permita explorar posibles patrones y diferencias entre regiones.

<!-- Para pegar una foto y que este alineada usamos ese código -->
<p align="center">

<img src="cultivo.jpg" width="70%"/>

</p>

## Los datos

<!-- Carga del archivo CSV -->

El conjunto de datos utilizado en este proyecto procede de
[**Kaggle**](https://www.kaggle.com/datasets/thedevastator/weed-plant-taxonomy-in-france-and-uk?resource=download),
donde se recopila **información taxonómica** y de **conservación de
especies** de malas hierbas registradas en Francia y Reino Unido. El
dataset original fue generado a partir de bases de datos botánicas
oficiales y contiene listados de especies, clasificación taxonómica,
región biogeográfica a la que pertenecen, y su categoría de conservación
en ambos países.

Este tipo de información resulta **especialmente valiosa** para estudios
ecológicos, ya que permite **comparar** patrones de biodiversidad,
**analizar** las diferencias en la gestión ambiental entre regiones y
**detectar** posibles riesgos para la conservación de especies
vegetales.

<!-- Para obtener una primera visión del dataset mostramos las primeras observaciones -->

<div style="border: 1px solid #ddd; padding: 0px; overflow-y: scroll; height:450px; overflow-x: scroll; width:900px; ">

<table class="table" style="color: black; width: auto !important; margin-left: auto; margin-right: auto;">
<caption>
Vista inicial de las primeras 6 filas del dataset
</caption>
<thead>
<tr>
<th style="text-align:center;position: sticky; top:0; background-color: #FFFFFF;">
taxref10.CD_REF
</th>
<th style="text-align:center;position: sticky; top:0; background-color: #FFFFFF;">
binome.discoweed
</th>
<th style="text-align:center;position: sticky; top:0; background-color: #FFFFFF;">
family
</th>
<th style="text-align:center;position: sticky; top:0; background-color: #FFFFFF;">
taxo
</th>
<th style="text-align:center;position: sticky; top:0; background-color: #FFFFFF;">
binome.discoweed.noinfra
</th>
<th style="text-align:center;position: sticky; top:0; background-color: #FFFFFF;">
taxref10.CD_REF.infra
</th>
<th style="text-align:center;position: sticky; top:0; background-color: #FFFFFF;">
jauzein
</th>
<th style="text-align:center;position: sticky; top:0; background-color: #FFFFFF;">
za
</th>
<th style="text-align:center;position: sticky; top:0; background-color: #FFFFFF;">
biovigilance
</th>
<th style="text-align:center;position: sticky; top:0; background-color: #FFFFFF;">
fse
</th>
<th style="text-align:center;position: sticky; top:0; background-color: #FFFFFF;">
farmbio
</th>
<th style="text-align:center;position: sticky; top:0; background-color: #FFFFFF;">
cambecedes
</th>
<th style="text-align:center;position: sticky; top:0; background-color: #FFFFFF;">
lifeform
</th>
<th style="text-align:center;position: sticky; top:0; background-color: #FFFFFF;">
biogeo
</th>
<th style="text-align:center;position: sticky; top:0; background-color: #FFFFFF;">
red.FR
</th>
<th style="text-align:center;position: sticky; top:0; background-color: #FFFFFF;">
red.UK
</th>
<th style="text-align:center;position: sticky; top:0; background-color: #FFFFFF;">
module
</th>
<th style="text-align:center;position: sticky; top:0; background-color: #FFFFFF;">
c
</th>
<th style="text-align:center;position: sticky; top:0; background-color: #FFFFFF;">
z
</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:center;">
79684
</td>
<td style="text-align:center;">
ABUTILON THEOPHRASTI
</td>
<td style="text-align:center;">
Malvaceae
</td>
<td style="text-align:center;">
binome
</td>
<td style="text-align:center;">
ABUTILON THEOPHRASTI
</td>
<td style="text-align:center;">
79684
</td>
<td style="text-align:center;">
1
</td>
<td style="text-align:center;">
0
</td>
<td style="text-align:center;">
1
</td>
<td style="text-align:center;">
0
</td>
<td style="text-align:center;">
0
</td>
<td style="text-align:center;">
0
</td>
<td style="text-align:center;">
therophyte
</td>
<td style="text-align:center;">
Eurasian
</td>
<td style="text-align:center;">
NA
</td>
<td style="text-align:center;">
NA
</td>
<td style="text-align:center;">
NA
</td>
<td style="text-align:center;">
NA
</td>
<td style="text-align:center;">
NA
</td>
</tr>
<tr>
<td style="text-align:center;">
79734
</td>
<td style="text-align:center;">
ACER CAMPESTRE
</td>
<td style="text-align:center;">
Sapindaceae
</td>
<td style="text-align:center;">
binome
</td>
<td style="text-align:center;">
ACER CAMPESTRE
</td>
<td style="text-align:center;">
79734
</td>
<td style="text-align:center;">
0
</td>
<td style="text-align:center;">
0
</td>
<td style="text-align:center;">
0
</td>
<td style="text-align:center;">
1
</td>
<td style="text-align:center;">
1
</td>
<td style="text-align:center;">
0
</td>
<td style="text-align:center;">
phanaerophyte
</td>
<td style="text-align:center;">
Eurasian(meridional)
</td>
<td style="text-align:center;">
NA
</td>
<td style="text-align:center;">
LC
</td>
<td style="text-align:center;">
1
</td>
<td style="text-align:center;">
0.35529
</td>
<td style="text-align:center;">
3.16480
</td>
</tr>
<tr>
<td style="text-align:center;">
79783
</td>
<td style="text-align:center;">
ACER PSEUDOPLATANUS
</td>
<td style="text-align:center;">
Sapindaceae
</td>
<td style="text-align:center;">
binome
</td>
<td style="text-align:center;">
ACER PSEUDOPLATANUS
</td>
<td style="text-align:center;">
79783
</td>
<td style="text-align:center;">
0
</td>
<td style="text-align:center;">
0
</td>
<td style="text-align:center;">
1
</td>
<td style="text-align:center;">
1
</td>
<td style="text-align:center;">
1
</td>
<td style="text-align:center;">
0
</td>
<td style="text-align:center;">
phanaerophyte
</td>
<td style="text-align:center;">
European
</td>
<td style="text-align:center;">
NA
</td>
<td style="text-align:center;">
NA
</td>
<td style="text-align:center;">
99
</td>
<td style="text-align:center;">
0.74492
</td>
<td style="text-align:center;">
2.09450
</td>
</tr>
<tr>
<td style="text-align:center;">
79908
</td>
<td style="text-align:center;">
ACHILLEA MILLEFOLIUM
</td>
<td style="text-align:center;">
Asteraceae
</td>
<td style="text-align:center;">
binome
</td>
<td style="text-align:center;">
ACHILLEA MILLEFOLIUM
</td>
<td style="text-align:center;">
79908
</td>
<td style="text-align:center;">
1
</td>
<td style="text-align:center;">
1
</td>
<td style="text-align:center;">
1
</td>
<td style="text-align:center;">
1
</td>
<td style="text-align:center;">
0
</td>
<td style="text-align:center;">
0
</td>
<td style="text-align:center;">
hemicryptophyte
</td>
<td style="text-align:center;">
Eurasian
</td>
<td style="text-align:center;">
NA
</td>
<td style="text-align:center;">
LC
</td>
<td style="text-align:center;">
3
</td>
<td style="text-align:center;">
0.66284
</td>
<td style="text-align:center;">
22.87600
</td>
</tr>
<tr>
<td style="text-align:center;">
80211
</td>
<td style="text-align:center;">
ADONIS AESTIVALIS
</td>
<td style="text-align:center;">
Ranunculaceae
</td>
<td style="text-align:center;">
binome
</td>
<td style="text-align:center;">
ADONIS AESTIVALIS
</td>
<td style="text-align:center;">
80211
</td>
<td style="text-align:center;">
1
</td>
<td style="text-align:center;">
0
</td>
<td style="text-align:center;">
1
</td>
<td style="text-align:center;">
0
</td>
<td style="text-align:center;">
0
</td>
<td style="text-align:center;">
1
</td>
<td style="text-align:center;">
therophyte
</td>
<td style="text-align:center;">
Eurasian
</td>
<td style="text-align:center;">
NA
</td>
<td style="text-align:center;">
NA
</td>
<td style="text-align:center;">
1
</td>
<td style="text-align:center;">
0.59375
</td>
<td style="text-align:center;">
-0.17226
</td>
</tr>
<tr>
<td style="text-align:center;">
80212
</td>
<td style="text-align:center;">
ADONIS ANNUA
</td>
<td style="text-align:center;">
Ranunculaceae
</td>
<td style="text-align:center;">
binome
</td>
<td style="text-align:center;">
ADONIS ANNUA
</td>
<td style="text-align:center;">
80212
</td>
<td style="text-align:center;">
1
</td>
<td style="text-align:center;">
1
</td>
<td style="text-align:center;">
0
</td>
<td style="text-align:center;">
0
</td>
<td style="text-align:center;">
0
</td>
<td style="text-align:center;">
1
</td>
<td style="text-align:center;">
therophyte
</td>
<td style="text-align:center;">
Eurasian
</td>
<td style="text-align:center;">
NA
</td>
<td style="text-align:center;">
EN
</td>
<td style="text-align:center;">
5
</td>
<td style="text-align:center;">
0.00000
</td>
<td style="text-align:center;">
-0.25147
</td>
</tr>
</tbody>
</table>

</div>

La tabla contiene 1577 filas y 19 columnas.

Esto significa que disponemos de **1577 observaciones** sobre las cuales
se pueden analizar el comportamiento de las **19** variables
registradas.

## Descripción de las variables

A continuación se presenta una descripción resumida de todas las
variables incluidas en el conjunto de datos. Se indica el tipo y el
significado ecológico o taxonómico de cada una [^1].

<!-- Definimos un tibble mediante tribble con la descripción de todas las variables (manualmente) -->
<!-- Se muestra el tibble `Variables` como una tabla desplazable (scroll_box) para facilitar su lectura en el HTML -->

<div style="border: 1px solid #ddd; padding: 0px; overflow-y: scroll; height:450px; overflow-x: scroll; width:900px; ">

<table class="table" style="color: black; width: auto !important; margin-left: auto; margin-right: auto;">
<caption>
Descripción de variables del dataset
</caption>
<thead>
<tr>
<th style="text-align:left;position: sticky; top:0; background-color: #FFFFFF;">
Variable
</th>
<th style="text-align:left;position: sticky; top:0; background-color: #FFFFFF;">
Tipo
</th>
<th style="text-align:left;position: sticky; top:0; background-color: #FFFFFF;">
Descripcion
</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:left;">
taxref10.CD_REF
</td>
<td style="text-align:left;">
Integer
</td>
<td style="text-align:left;">
Código de referencia taxonómica (TAXREF) de la especie.
</td>
</tr>
<tr>
<td style="text-align:left;">
binome.discoweed
</td>
<td style="text-align:left;">
String
</td>
<td style="text-align:left;">
Nombre binomial de la especie (género + especie).
</td>
</tr>
<tr>
<td style="text-align:left;">
family
</td>
<td style="text-align:left;">
String
</td>
<td style="text-align:left;">
Familia botánica de la especie.
</td>
</tr>
<tr>
<td style="text-align:left;">
taxo
</td>
<td style="text-align:left;">
String
</td>
<td style="text-align:left;">
Rango taxonómico registrado (p. ej: especie, subespecie, etc.).
</td>
</tr>
<tr>
<td style="text-align:left;">
binome.discoweed.noinfra
</td>
<td style="text-align:left;">
String
</td>
<td style="text-align:left;">
Nombre binomial sin rango infraespecífico.
</td>
</tr>
<tr>
<td style="text-align:left;">
taxref10.CD_REF.infra
</td>
<td style="text-align:left;">
Integer
</td>
<td style="text-align:left;">
Código TAXREF con rango infraespecífico.
</td>
</tr>
<tr>
<td style="text-align:left;">
jauzein
</td>
<td style="text-align:left;">
Boolean
</td>
<td style="text-align:left;">
Presencia en la base de datos Jauzein (TRUE/FALSE).
</td>
</tr>
<tr>
<td style="text-align:left;">
za
</td>
<td style="text-align:left;">
Boolean
</td>
<td style="text-align:left;">
Presencia en la base de datos ZA (TRUE/FALSE).
</td>
</tr>
<tr>
<td style="text-align:left;">
biovigilance
</td>
<td style="text-align:left;">
Boolean
</td>
<td style="text-align:left;">
Presencia en la base de datos Biovigilance (TRUE/FALSE).
</td>
</tr>
<tr>
<td style="text-align:left;">
fse
</td>
<td style="text-align:left;">
Boolean
</td>
<td style="text-align:left;">
Presencia en la base de datos FSE (TRUE/FALSE).
</td>
</tr>
<tr>
<td style="text-align:left;">
farmbio
</td>
<td style="text-align:left;">
Boolean
</td>
<td style="text-align:left;">
Presencia en la base de datos Farmbio (TRUE/FALSE).
</td>
</tr>
<tr>
<td style="text-align:left;">
cambecedes
</td>
<td style="text-align:left;">
Boolean
</td>
<td style="text-align:left;">
Presencia en la base de datos Cambecedes (TRUE/FALSE).
</td>
</tr>
<tr>
<td style="text-align:left;">
lifeform
</td>
<td style="text-align:left;">
String
</td>
<td style="text-align:left;">
Forma de vida (característica ecológica).
</td>
</tr>
<tr>
<td style="text-align:left;">
biogeo
</td>
<td style="text-align:left;">
String
</td>
<td style="text-align:left;">
Zona biogeográfica asignada a la especie.
</td>
</tr>
<tr>
<td style="text-align:left;">
red.FR
</td>
<td style="text-align:left;">
String
</td>
<td style="text-align:left;">
Estado/categoría en la Lista Roja para Francia.
</td>
</tr>
<tr>
<td style="text-align:left;">
red.UK
</td>
<td style="text-align:left;">
String
</td>
<td style="text-align:left;">
Estado/categoría en la Lista Roja para Reino Unido.
</td>
</tr>
<tr>
<td style="text-align:left;">
module
</td>
<td style="text-align:left;">
Integer
</td>
<td style="text-align:left;">
Grado dentro del módulo (within-module degree) en la red/estructura del
dataset.
</td>
</tr>
</tbody>
</table>

</div>

Para el trabajo hemos usado los paquetes : ggplot2([Wickham
2016](#ref-ggplot22016)), knitr ([Xie 2015](#ref-knitr2015)) y dplyr
([Wickham et al. 2023](#ref-R-dplyr)).

# <span style="color: darkred;">OBJETIVO DEL TRABAJO</span>

El objetivo general de este trabajo es **analizar el conjunto de datos
sobre malas hierbas registradas en Francia**, con el fin de obtener una
visión estructurada de su composición taxonómica, ecológica y de
conservación, así como **explorar posibles relaciones** entre la
procedencia biogeográfica de las especies y su **estado de
conservación**.

Para alcanzar este objetivo general, se plantean los siguientes
**objetivos específicos**:

- **Familiarizarnos con el dataset**, sus variables y su estructura.

- **Realizar una descripción general** de las especies de malas hierbas
  en Francia.

- **Examinar la distribución de las especies según sus zonas
  biogeográficas**, sin asumir aún ninguna relación.

- **Analizar gráficamente** la distribución de las categorías de
  conservación.

- **Aplicar técnicas estadísticas** para comprobar si existe relación
  entre biogeografía y estado de conservación.

- **Interpretar los resultados**.

# <span style="color: darkred;">HIPÓTESIS</span>

En este trabajo analizamos si el estado de conservación de las especies
de malas hierbas varía en función de su procedencia biogeográfica. Para
ello planteamos la siguiente hipótesis:

**Hipótesis nula: El estado de conservación de las especies de malas
hierbas en Francia no está asociado a su zona biogeográfica.**

**Hipótesis alternativa: El estado de conservación de las especies de
malas hierbas en Francia está asociado a su zona biogeográfica.**

Esta hipótesis es relevante desde una **perspectiva ecológica**, ya que
las distintas zonas biogeográficas presentan condiciones climáticas,
agrícolas y de manejo del territorio diferentes, lo que podría influir
en la vulnerabilidad de las especies dentro del contexto francés.

<!-- Para pegar una foto y que este alineada usamos ese codigo -->
<p align="center">

<img src="mapa europa.png" width="70%"/>

</p>

# <span style="color: darkred;">ANALISIS ESTADÍSTICO</span>

<!-- Seleccionamos las variables relevantes y filtramos los datos eliminando valores para el análisis estadístico -->

Para llevar a cabo el análisis estadístico, se realizó una **selección
de las variables relevantes** del conjunto de datos original [^2]. Este
proceso nos permitió **reducir la complejidad del dataset** y centrarnos
únicamente en aquellas variables directamente relacionadas con los
objetivos y la hipótesis planteada.

Se seleccionaron las variables necesarias para **analizar la relación
entre la zona biogeográfica de las especies y su estado de
conservación** en Francia.

A continuación, se muestra una tabla con las variables seleccionadas que
se utilizarán en el análisis estadístico.

<table class="table" style="color: black; margin-left: auto; margin-right: auto;">
<caption>
Tabla 1. Variables seleccionadas para el análisis estadístico
</caption>
<thead>
<tr>
<th style="text-align:left;">
Variable
</th>
<th style="text-align:left;">
Descripcion
</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:left;">
binome.discoweed
</td>
<td style="text-align:left;">
Nombre binomial de la especie.
</td>
</tr>
<tr>
<td style="text-align:left;">
family
</td>
<td style="text-align:left;">
Familia botánica a la que pertenece la especie.
</td>
</tr>
<tr>
<td style="text-align:left;">
lifeform
</td>
<td style="text-align:left;">
Forma de vida de la especie (característica ecológica).
</td>
</tr>
<tr>
<td style="text-align:left;">
biogeo
</td>
<td style="text-align:left;">
Zona biogeográfica de procedencia de la especie.
</td>
</tr>
<tr>
<td style="text-align:left;">
red.FR
</td>
<td style="text-align:left;">
Estado de conservación de la especie en Francia.
</td>
</tr>
</tbody>
</table>

## Análisis descriptivo

El **análisis descriptivo** nos permitió caracterizar el conjunto de
especies estudiadas y obtener una primera visión general de su
composición.

En este apartado se describen las especies en función de su *familia
botánica*, *forma de vida*, *zona biogeográfica* y *estado de
conservación* en Francia.

Esto nos permite describir la situación general de conservación de las
especies incluidas en el estudio, sin evaluar su relación con otras
variables.

**Composición general**

En primer lugar, analizamos el número total de especies consideradas en
el análisis y su diversidad taxonómica básica atendiendo al número de
familias botánicas y zonas biogeográficas representadas.

<!-- Calculamos un resumen general del dataset, obteniendo el número de especies, familias botánicas y zonas biogeográficas -->
<table class="table" style="color: black; width: auto !important; margin-left: auto; margin-right: auto;">
<caption>
Tabla 2.Resumen general del conjunto de datos
</caption>
<thead>
<tr>
<th style="text-align:right;">
numero_especies
</th>
<th style="text-align:right;">
numero_familias
</th>
<th style="text-align:right;">
numero_zonas_biogeo
</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:right;">
137
</td>
<td style="text-align:right;">
29
</td>
<td style="text-align:right;">
27
</td>
</tr>
</tbody>
</table>

Este resumen muestra que el conjunto de datos incluye un elevado número
de especies pertenecientes a múltiples familias botánicas y procedentes
de diversas zonas biogeográficas, lo que refleja una alta diversidad
taxonómica dentro del grupo de malas hierbas consideradas en el estudio.

**Distribución por familias**

A continuación, examinamos la distribución de las especies según su
familia botánica con el objetivo de identificar aquellas con mayor
representación en el conjunto de datos.

<table class="table" style="color: black; margin-left: auto; margin-right: auto;">
<caption>
Tabla 3. Diez familias más representadas
</caption>
<thead>
<tr>
<th style="text-align:left;">
family
</th>
<th style="text-align:right;">
n
</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:left;">
Fabaceae
</td>
<td style="text-align:right;">
34
</td>
</tr>
<tr>
<td style="text-align:left;">
Asteraceae
</td>
<td style="text-align:right;">
12
</td>
</tr>
<tr>
<td style="text-align:left;">
Liliaceae
</td>
<td style="text-align:right;">
11
</td>
</tr>
<tr>
<td style="text-align:left;">
Poaceae
</td>
<td style="text-align:right;">
11
</td>
</tr>
<tr>
<td style="text-align:left;">
Caryophyllaceae
</td>
<td style="text-align:right;">
9
</td>
</tr>
<tr>
<td style="text-align:left;">
Papaveraceae
</td>
<td style="text-align:right;">
8
</td>
</tr>
<tr>
<td style="text-align:left;">
Apiaceae
</td>
<td style="text-align:right;">
5
</td>
</tr>
<tr>
<td style="text-align:left;">
Ranunculaceae
</td>
<td style="text-align:right;">
5
</td>
</tr>
<tr>
<td style="text-align:left;">
Asparagaceae
</td>
<td style="text-align:right;">
4
</td>
</tr>
<tr>
<td style="text-align:left;">
Amaranthaceae
</td>
<td style="text-align:right;">
3
</td>
</tr>
</tbody>
</table>

Observamos que unas pocas familias concentran la mayor proporción de
especies, un patrón habitual dado que ciertas familias presentan una
mayor capacidad de adaptación a ambientes agrícolas.

**Forma de vida de las especies**

La forma de vida es una característica clave para entender la estrategia
de supervivencia de las especies en sistemas agrícolas.

<table class="table" style="color: black; margin-left: auto; margin-right: auto;">
<caption>
Tabla 4. Distribución de especies según su forma de vida
</caption>
<thead>
<tr>
<th style="text-align:left;">
lifeform
</th>
<th style="text-align:right;">
n
</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:left;">
therophyte
</td>
<td style="text-align:right;">
102
</td>
</tr>
<tr>
<td style="text-align:left;">
geophyte
</td>
<td style="text-align:right;">
23
</td>
</tr>
<tr>
<td style="text-align:left;">
hemicryptophyte
</td>
<td style="text-align:right;">
9
</td>
</tr>
<tr>
<td style="text-align:left;">
liana
</td>
<td style="text-align:right;">
2
</td>
</tr>
<tr>
<td style="text-align:left;">
phanaerophyte
</td>
<td style="text-align:right;">
1
</td>
</tr>
</tbody>
</table>

La tabla muestra que predominan determinadas formas de vida típicas de
**ambientes modificados**.

**Distribución por zonas biogeográficas**

Analizamos la procedencia biogeográfica de las especies incluidas en el
estudio.

<table class="table" style="color: black; margin-left: auto; margin-right: auto;">
<caption>
Tabla 5. Distribución de especies por zona biogeográfica
</caption>
<thead>
<tr>
<th style="text-align:left;">
biogeo
</th>
<th style="text-align:right;">
n
</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:left;">
Mediterranean
</td>
<td style="text-align:right;">
63
</td>
</tr>
<tr>
<td style="text-align:left;">
Mediterranean(western)
</td>
<td style="text-align:right;">
17
</td>
</tr>
<tr>
<td style="text-align:left;">
European(meridional)
</td>
<td style="text-align:right;">
13
</td>
</tr>
<tr>
<td style="text-align:left;">
Mediterranean(eury)
</td>
<td style="text-align:right;">
7
</td>
</tr>
<tr>
<td style="text-align:left;">
orophyte(Alp)
</td>
<td style="text-align:right;">
7
</td>
</tr>
<tr>
<td style="text-align:left;">
Eurasian
</td>
<td style="text-align:right;">
6
</td>
</tr>
<tr>
<td style="text-align:left;">
Mediterranean(central)
</td>
<td style="text-align:right;">
3
</td>
</tr>
<tr>
<td style="text-align:left;">
European(central)
</td>
<td style="text-align:right;">
2
</td>
</tr>
</tbody>
</table>

Esto nos permitió conocer cómo se distribuyen las especies entre las
distintas regiones biogeográficas consideradas, aportando un contexto
general para el análisis posterior.

**Estado de conservación en Francia**

Por último, se describió la distribución de las especies según su estado
de conservación en cada país.

<table class="table" style="color: black; margin-left: auto; margin-right: auto;">
<caption>
Tabla 6. Estado de conservación de las especies en Francia
</caption>
<thead>
<tr>
<th style="text-align:left;">
red.FR
</th>
<th style="text-align:right;">
n
</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:left;">
VU
</td>
<td style="text-align:right;">
50
</td>
</tr>
<tr>
<td style="text-align:left;">
LC
</td>
<td style="text-align:right;">
22
</td>
</tr>
<tr>
<td style="text-align:left;">
DD
</td>
<td style="text-align:right;">
19
</td>
</tr>
<tr>
<td style="text-align:left;">
EN
</td>
<td style="text-align:right;">
14
</td>
</tr>
<tr>
<td style="text-align:left;">
CR
</td>
<td style="text-align:right;">
13
</td>
</tr>
<tr>
<td style="text-align:left;">
NT
</td>
<td style="text-align:right;">
9
</td>
</tr>
<tr>
<td style="text-align:left;">
RE
</td>
<td style="text-align:right;">
6
</td>
</tr>
<tr>
<td style="text-align:left;">
EW
</td>
<td style="text-align:right;">
3
</td>
</tr>
<tr>
<td style="text-align:left;">
EX
</td>
<td style="text-align:right;">
1
</td>
</tr>
</tbody>
</table>

## Análisis inferencial y gráfico

Con el objetivo de contrastar la hipótesis planteada, evaluamos si
existe una correlación significativa entre la zona biogeográfica de las
especies y su estado de conservación en Francia.

### Test Chi-Cuadrado

Dado que ambas variables (*red.FR* y *biogeo*) son de carácter
cualitativo, se aplicó un test *Chi-cuadrado de independencia*.

<!-- table crea una tabla de contingencia con la zona biogeográfica y el estado de conservación. Esta es necesaria para poder aplicar el test chi-cuadrado -->
<!-- Aplicamos el test Chi-cuadrado de independencia para evaluar la relación entre la zona biogeográfica y el estado de conservación -->
<!-- Extraemos y mostramos de forma ordenada los resultados del test Chi-cuadrado utilizando el paquete broom -->

| statistic | parameter | p.value |
|:---------:|:---------:|:-------:|
| 278.2845  |    208    |  8e-04  |

Tabla 7. Resultados del test Chi-cuadrado de independencia

El p-valor es mucho menor que 0.05, así que el resultado es
significativo.

El test Chi-cuadrado de independencia muestra una correlación
significativa entre la zona biogeográfica y el estado de conservación de
las especies en Francia.

Por tanto, estos resultados indican que el estado de conservación de las
especies varía en función de su procedencia biogeográfica, apoyando la
hipótesis alternativa planteada anteriormente y rechazando la hipótesis
nula.

### Análisis Gráfico

<!-- Insertamos los chunks correspondientes para filtrar las variables en el dataset y crear una gráfica de barras-->
<!-- Representamos mediante un gráfico de barras la distribución del estado de conservación de las especies según su zona biogeográfica -->

![](Diversidad-Malas-Hierbas_files/figure-gfm/grafico_top8-1.png)<!-- -->

<!-- Hacemos de forma manual una tabla usando el paquete knitr para explicar las siglas-->

| Sigla | Significado                  |
|:------|:-----------------------------|
| CR    | Peligro Crítico.             |
| EN    | En Peligro.                  |
| VU    | Vulnerable.                  |
| NT    | Casi Amenazada.              |
| LC    | Preocupación Menor.          |
| DD    | Datos Insuficientes.         |
| EX    | Extinta.                     |
| EW    | Extinta en Estado Silvestre. |
| RE    | Extinta Regionalmente.       |

Significado de las siglas de los estados de conservación

En el gráfico podemos observar cómo la mayor parte de especies se
concentran en la zona mediterránea y oeste europeo, mientras que
encontramos menos en la zona central. La alta variación en la cantidad
de especies presentes en cada zona respalda la idea de que este factor
influye en la distribucion de las mismas. Además se puede observar como
en cada zona se encuentra una proporcion distinta de estados de
conservacion. Por ejemplo, podemos observar que en la zona europea
meridional la proporción de especies en *preocupación menor* es mayor
que en la zona mediterránea central, o como en la zona europea central
hay especies extintas mientras que en la zona mediterránea del oeste no
las hay.

En definitiva, el gráfico refleja que los estados de conservación de las
especies disponibles y el número de estas varía ampliamente según la
zona en la que nos encontramos.

# <span style="color: darkred;">CONCLUSIÓN</span>

Los datos analizados a lo largo del trabajo apoyan la hipótesis
alternativa formulada al inicio de este: **Hipótesis alternativa: El
estado de conservación de las especies de malas hierbas en Francia está
asociado a su zona biogeográfica.**

Por tanto, los resultados obtenidos demuestran que las zonas
biogeográficas en las que están ubicadas las especies de malas hierbas
tienen una implicación directa en su distribución y estado de
conservación en grandes territorios como el país de Francia.
Posiblemente esto sea debido al cambio del conjunto de factores
ambientales que se produce en cada zona, como cambios de temperatura,
humedad o altura.

Además, se debe tener en cuenta que en países grandes, cada zona
biogegráfica presenta un distinto grado de modificación del medio
natural, como producto de la distinta actividad agrícola que se ejerce
en cada región. Esto afectaría tambien a la distribución y estado de las
poblaciones de estas especies.

Esto es una muestra más de como la actividad tanto humana como ambiental
puede modificar el estado de las poblaciones de plantas en cada zona
según su actividad, pudiendo ser por considerarse estas perjudiciales
para los cultivos o porque el cambio pase desapercibido en un primer
momento.

Este estudio muestra como estas situaciones pueden ser aprovechadas para
ampliar el conocimiento sobre las dinámicas poblacionales de plantas y
como el ambiente y contexto en el que se encuentra cada población
influyen en su conservación a futuro.

# <span style="color: darkred;">Información de la sesión y bibliografía</span>

<!-- Para asegurar la reproducibilidad de los resultados se proporciona información sobre el sistema operativo y la version de software y paquetes -->

    ## R version 4.4.3 (2025-02-28 ucrt)
    ## Platform: x86_64-w64-mingw32/x64
    ## Running under: Windows 11 x64 (build 26100)
    ## 
    ## Matrix products: default
    ## 
    ## 
    ## locale:
    ## [1] LC_COLLATE=Spanish_Spain.utf8  LC_CTYPE=Spanish_Spain.utf8   
    ## [3] LC_MONETARY=Spanish_Spain.utf8 LC_NUMERIC=C                  
    ## [5] LC_TIME=Spanish_Spain.utf8    
    ## 
    ## time zone: Europe/Paris
    ## tzcode source: internal
    ## 
    ## attached base packages:
    ## [1] stats     graphics  grDevices utils     datasets  methods   base     
    ## 
    ## other attached packages:
    ## [1] broom_1.0.11     readr_2.1.6      kableExtra_1.4.0 knitr_1.50      
    ## [5] ggplot2_3.5.1    dplyr_1.1.4     
    ## 
    ## loaded via a namespace (and not attached):
    ##  [1] gtable_0.3.6      compiler_4.4.3    tidyselect_1.2.1  xml2_1.5.1       
    ##  [5] stringr_1.6.0     tidyr_1.3.1       systemfonts_1.3.1 scales_1.3.0     
    ##  [9] textshaping_1.0.4 yaml_2.3.10       fastmap_1.2.0     R6_2.6.1         
    ## [13] labeling_0.4.3    generics_0.1.4    backports_1.5.0   tibble_3.2.1     
    ## [17] munsell_0.5.1     svglite_2.2.2     pillar_1.10.1     tzdb_0.5.0       
    ## [21] rlang_1.1.5       stringi_1.8.7     xfun_0.54         viridisLite_0.4.2
    ## [25] cli_3.6.4         withr_3.0.2       magrittr_2.0.3    digest_0.6.37    
    ## [29] grid_4.4.3        rstudioapi_0.17.1 hms_1.1.4         lifecycle_1.0.4  
    ## [33] vctrs_0.6.5       evaluate_1.0.5    glue_1.8.0        farver_2.1.2     
    ## [37] colorspace_2.1-1  purrr_1.2.0       rmarkdown_2.30    tools_4.4.3      
    ## [41] pkgconfig_2.0.3   htmltools_0.5.8.1

## Bibliografía

1.  Munoz, F., Fried, G., Armengot, L., Bourgeois, B., Bretagnolle, V.,
    Chadoeuf, J., … & Gaba, S. (2017). Database of weeds in cultivation
    fields of France and UK, with ecological and biogeographical
    information.

2.  Whittaker, R. J., Araújo, M. B., Jepson, P., Ladle, R. J.,
    Watson, J. E. M., & Willis, K. J. (2005). Conservation biogeography:
    Assessment and prospect. Diversity and Distributions, 11(1), 3–23.

Paquetes:

<div id="refs" class="references csl-bib-body hanging-indent"
entry-spacing="0">

<div id="ref-ggplot22016" class="csl-entry">

Wickham, Hadley. 2016. *Ggplot2: Elegant Graphics for Data Analysis*.
Springer-Verlag New York. <https://ggplot2.tidyverse.org>.

</div>

<div id="ref-R-dplyr" class="csl-entry">

Wickham, Hadley, Romain François, Lionel Henry, Kirill Müller, and Davis
Vaughan. 2023. *Dplyr: A Grammar of Data Manipulation*.
<https://dplyr.tidyverse.org>.

</div>

<div id="ref-knitr2015" class="csl-entry">

Xie, Yihui. 2015. *Dynamic Documents with R and Knitr*. 2nd ed. Boca
Raton, Florida: Chapman; Hall/CRC. <https://yihui.org/knitr/>.

</div>

</div>

[^1]: <https://www.kaggle.com/datasets/thedevastator/weed-plant-taxonomy-in-france-and-uk?resource=download>

[^2]: Munoz, F., Fried, G., Armengot, L., Bourgeois, B., Bretagnolle,
    V., Chadoeuf, J., … & Gaba, S. (2017). Database of weeds in
    cultivation fields of France and UK, with ecological and
    biogeographical information.
