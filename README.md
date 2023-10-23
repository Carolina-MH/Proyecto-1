# Global Shark Attacks 

## Introducción

![encabezado](https://github.com/Carolina-MH/Proyecto-1/blob/main/img/encabezado.png)

La finalidad de este proyecto es poner en práctica el proceso completo del análisis de datos: desde la limpieza y exploración inicial de los datos, hasta la presentación de las conclusiones fundamentadas.

A lo largo de este análisis se abordarán desafíos comunes como la gestión de datos faltantes, la visualización y el descubrimiento de patrones en los datos.

A medida que avancemos, se aplicarán técnicas analíticas para extraer información significativa de los datos disponibles.

## Objetivos

El objetivo principal de este análisis de datos es explorar y comprender los patrones y tendencias relacionados con los ataques de tiburones en un conjunto de datos específico. Para ser más concretos, el objetivo del análisis es:

🦈 `Identificar las ubicaciones más peligrosas en término de ataques de tiburones.

🦈 Determinar si ciertas actividades están relacionadas con un mayor riesgo de ataques.

🦈 Evaluar la proporción de ataques fatales en comparación con los no fatales.`

Estos objetivos nos ayudarán a comprender mejor los factores que contribuyen a la seguridad en las actividades acuáticas y proporcionarán información útil para la toma de decisiones y medidas de prevención en áreas propensas a los ataques.

## Exploración y limpieza de datos

Durante el proceso, uno de los pasos cruciales es la limpieza de datos. Esto implica la identificación y correción de errores, así como la eliminación de valores nulos o inconsistencias que pueden afectar la calidad de los resultados.

La limpieza de datos la llevé a cabo en cada una de las columnas donde identifiqué valores nulos, incoherencias o datos no válidos para dejarlas preparadas y así poder abordar los objetivos de mi análisis.

🦈 `Columna 'type'`: en esta columna decidí eliminar las filas 'invalid' y 'questionable' ya que estos valores son ambiguos y no aportan información útil para mi análsiis.

A continuación, comparé los valores nulos en la columna "type" con las columnas 'activity' y 'species_' para obtener una mejor comprensión de cómo llenar esos valores nulos.

Una vez hecho esto, identifiqué que los valores nulos en la columna 'type' coincidían con 'species_' por lo que consideré que mi estrategia fuera llenar esos nulos con una estiqueta denomida 'desconocido'.

🦈`Columna 'country'`: una vez estandarizadas todas las filas de esta columna, la comparé con otras columnas interesantes ('area','location','activity' y 'type') para valorar como sobrescribir esos valores nulos.

Haciendo esto, llegué a la conclusión de que no disponía de información en ninguna de las dos columnas 'country' y area' y esto provocaba que fuera complicado inferir la ubicación geográfica del incidente. Por lo que, en lugar de llenar los valores nulos con información potencialmente incorrecta o desconocida, opté por eliminarlas, así no me llevaría a conclusiones erróneas.

Por otro lado, observé que en el resto de columnas como 'country' y 'location' contenidan información útiles y relevante, por lo que esos valores nulos los sobrescribí como 'desconocido' en lugar de eliminarlas por completo.

🦈`Columna 'area'`: en esta columna seleccioné las filas donde 'area' fuera nulo pero tuviera información en las columnas 'country' y 'location'.

Como en mi análisis las columnas 'type', 'country', 'activity', 'fatal_(y/n)', y 'species_' eran cruciales opté por sobrescribir los valores nulos en la columna 'area' con 'desconocido'.

🦈`Columna 'activity'`: comparé esta columna con 'type' para verificar si había correlaciones entre ambas y así poder decidir cómo llenar los valores nulos. Para ello, realicé una tabla cruzada entre 'activity' y 'type' y luego calculé la proporción de actividades para cada tipo de ataque.

En las filas donde coincidía el valor de'type' pero no de 'activity' lo sobrescribí con 'desconocido' para no perder información importante. En cambio, en las filas donde no tenía información las eliminé.


🦈`Columna 'fatal_(y/n)'`: esta columna es para indenticar si un ataque fue fatal o no, por lo que, opté por mantener únicamente las filas con valores válidos ('N' o 'Y') así me permitiría realizar el análisis más preciso y evitaría cualquier distorsión en mis resultados.

Eliminé las filas con datos incorrectos como 'M' y '2017' ya que son errores de entrada de datos.

🦈`Columna 'species_'`: explorando esta columna identifiqué que tenía muchos valores nulos y su limpieza podría ser compleja debido a la falta de información.

Mi estrategia fué llenar esos valores nulos con la etiqueta de 'desconocido'. En el análisis posterior lo tuve en cuenta para explorar la relación entre la especie de tiburón y otros factores como la ubicación geográfica y el tipo de actividad.


## Análisis

Para lograr mi objetivo, he seleccionado varias columnas clave del conjunto de datos que contienen información sobre los ataques de tiburones: 'type' (tipo de ataque), 'country' (país), 'area' (área geográfica), 'activity' (actividad 961) realizada por la víctima), 'fatal_(y/n)' (si el ataque fue fatal) y 'species_' (especie de tiburón involucrada).

Una vez organizada la tabla para estudiar mejor los datos en mi análisis. Exploré los países y áreas con el mayor número de ataques y así indentifiqué las ubicaciones más peligrosas.

![paises_con_mas_ataques_de_tiburones](https://github.com/Carolina-MH/Proyecto-1/blob/main/img/paises_con_mas_ataques_de_tiburones.png)
![areas_con_mas_ataques_de_tiburones](https://github.com/Carolina-MH/Proyecto-1/blob/main/img/areas_con_mas_ataques_de_tiburones.png)

Observando las dos gráficas 'contry' y 'area' , he llegado a la conclusión de que USA es el país con más ataques de tiburones (2025), y dentro de USA, el área de Florida tiene la mayor cantidad de ataques (961).

Una vez establecido el país y el área que esta más afectado por ataques de tiburones, continué explorando la columna 'type' para el área de Florida. Así indentifiqué qué tipos de ataques son más comunes en esa región específica y, por lo tanto, obtuve una comprensión más detallada de la peligrosidad de las actividades en esa área.

![tipo_de_ataques](https://github.com/Carolina-MH/Proyecto-1/blob/main/img/tipo_de_ataques.png)

En Florida, el tipo de ataque de tiburón más común es el no provocado, con 858 casos registrados.

Una vez en este punto, exploré la relación entre los tipos de ataques no provocados en Florida y las actividades involucradas.

![ataques_por_actividad](https://github.com/Carolina-MH/Proyecto-1/blob/main/img/ataques_por_actividad.png)

Esta gráfica demuestra que, en Florida, los ataques de tiburones bajo la categoría 'Unprovoked' ocurren con mayor frecuencia surfeando, destacando la importancia de la prevención y la seguridad para los surfistas en esa área.

A continuación, estudié las especies que fueran más comunes en los ataques en Florida, practicando surf y a su vez no provocados.

![especie_de_tiburones](https://github.com/Carolina-MH/Proyecto-1/blob/main/img/especie_de_tiburones.png)

La alta presencia de 'desconocido' en la columna 'species_' sugiere que la identificación de la especie del tiburón en muchos casos es difícil o imposible de determinar, lo que puede deberse a la falta de información o a la complejidad de identificar con precisión la especie en situaciones de ataques de tiburones.

'White Shark' se posiciona como la segunda especie más común en los ataques de tiburones en Florida y 'Unprovoked' indica que los tiburones blancos podrían ser responsables de varios de esos ataques.

Por último, exploré si eran mortales o no hacer al hacer surf en Florida(USA), sumando también que no fueran provocados y además que las especies fueran desconocidas o tiburones blancos.

![ataques_fatales](https://github.com/Carolina-MH/Proyecto-1/blob/main/img/ataques_fatales.png)

## Conclusión

Después de analizar los datos de ataques de tiburones en Florida, específicamente los de tipo 'unprovoked' con especies 'desconocido' o 'White Shark', encontramos que la actividad más frecuente es 'surfing'. La mayoría de los ataques no son fatales, lo que sugiere que, aunque los ataques de tiburones son relativamente comunes en esta área, la probabilidad de un resultado fatal es baja.

![felisidá](https://github.com/Carolina-MH/Proyecto-1/blob/main/img/felisida.gif)

