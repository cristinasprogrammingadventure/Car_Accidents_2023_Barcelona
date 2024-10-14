# **Accidents segons causa conductor gestionats per la Guàrdia Urbana a la ciutat de Barcelona**

Este conjunto de datos proviene de Open Data BCN y el Servei de dades obertes de l’Ajuntament de Barcelona. Contiene 8897 entradas que corresponden al número de expedientes por accidentes de tráfico en el año 2023 en la ciudad de Barcelona.

## Introducción

### Descripción del Conjunto de Datos

Este conjunto de datos pertenece a la categoría de Ciutat i serveis, específicamente en el apartado de Seguretat. Incluye un listado de los accidentes gestionados por la Guàrdia Urbana en la ciudad de Barcelona. Además, incorpora información sobre el número de lesionados según la gravedad, el número de vehículos implicados y el punto exacto del accidente.

- Gerencia: Gerència d’Àrea de Seguretat, Prevenció i Convivència de la ciutat de Barcelona
- Departamento: Sistemes d’Informació i Telecomunicacions
- Fecha de Publicación: 14/02/2023
- Frecuencia de Actualización: Anual
- Acceso al Conjunto de Datos a través del siguiente enlace:
  "https://opendata-ajuntament.barcelona.cat/data/ca/dataset/accidents_causa_conductor_gu_bcn/resource/5a040155-38b3-4b19-a4b0-c84a0618d363"
- Para más información, puedes visitar el siguiente enlace:
    "http://ajuntament.barcelona.cat/guardiaurbana/ca/node"

### Variables

1. **Numero_expedient**: Número de expediente de tramitación del accidente
2. **Codi_districte**: Código del distrito de la ciudad de Barcelona donde ocurrió el accidente
3. **Nom_districte**: Nombre del distrito de la ciudad de Barcelona donde ocurrió el accidente
4. **Codi_barri**: Código del barrio
5. **Nom_barri**: Nombre del barrio
6. **Codi_carrer**: Código de la calle
7. **Nom_carrer**: Nombre de la calle
8. **Num_postal**: Número de puerta del edificio a la altura de donde se produjo un accidente
9. **Descripcio_dia_setmana**: Nombre del día de la semana, de lunes a domingo
10. **NK_Any**: Año de las observaciones, en este caso, 2023
11. **Mes_any**: Mes del año
12. **Nom_mes**: Nombre del mes
13. **Dia_mes**: Día del mes
14. **Hora_dia**: Hora del día
15. **Descripcio_torn**: Descripción del turno (mañana, tarde, noche)
16. **Descripcio_causa_mediata**: Descripción de la causa mediata
17. **Coordenada_UTM_X_ED50**: Coordenada X en formato UTM (ED50)
18. **Coordenada_UTM_Y_ED50**: Coordenada Y en formato UTM (ED50)
19. **Longitud_WGS84**: Coordenada geográfica de longitud
20. **Latitud_WGS84**: Coordenada geográfica de latitud

### Nota:

- Los datos de este conjunto complementan los de **Accidents gestionats per la Guàrdia Urbana a la ciutat de Barcelona**.
- El valor '-1' en una celda indica que no se dispone del dato.

## Proyecto de data analisis y data science 

Introducció: Presentació de los objetivos, métodología y principales observaciones
   
Depuració de dades: Descripció detallada de les tècniques de preprocessat aplicades i els criteris d’avaluació utilitzats.

Resultats: Presentació dels resultats obtinguts.

Conclusions: Principals inferències derivades dels resultats aconseguits.

## **Conclusión**

**Interpretación de las métricas obtenidas con K-Means:**

**El Silhouette Score** mide qué tan similares son los puntos dentro de un mismo clúster comparados con puntos de otros clústers.
    Valores cercanos a 1 indican que los clústers están bien definidos (los puntos están cerca de los puntos del mismo clúster y lejos de los de otros clústers).
    Valores cercanos a 0 indican que los puntos están muy cerca del límite entre clústers.
    Valores negativos significan que los puntos probablemente se han asignado a clústers incorrectos.
    **Resultado: 0.128**. Un valor de 0.128 es bajo, lo que sugiere que los clústers no están claramente separados, es decir, muchos puntos están cercanos a los bordes entre clústers o los clústers no son muy compactos.

**Davies-Bouldin Index**: El Davies-Bouldin Index (DBI) mide la calidad de los clústers basándose en la relación entre la distancia promedio entre los puntos en un clúster y la distancia entre los clústers.
    Valores cercanos a 0 indican clústers bien definidos y bien separados (menor es mejor).
    **Resultado: 1.98**. Un índice de 1.98 indica que los **clústers están razonablemente separados, pero no es excelente**. Valores bajos son mejores, y un DBI menor a 1 se considera bueno.

**¿Qué significa este resultado?**

Silhouette Score (0.128) es bajo, lo que indica que los **clústers podrían no estar bien separados o que existe cierta confusión en los bordes de los clústers**. Podría ser un indicio de que los datos no se ajustan bien al **modelo de K-Means**.
**Davies-Bouldin Index (1.98) es moderado**, lo que sugiere que los clústers tienen cierta separación, pero podría mejorar.

Tanto el Silhouette Score bajo como el DBI moderado indican que los clústers **no están claramente definidos y hay solapamiento entre ellos**. 

**Mejoras posibles**:

El número de clústers no es óptimo (probar con otros valores de k).
Los datos no están bien distribuidos para el modelo K-Means (quizás deberías probar con otros modelos como DBSCAN).
La selección de variables podría mejorar agregando o quitando columnas (como usar distritos o barrios, o explorar mejor los datos antes del clustering), experimentar con más columnas.

¿Debería haber **más columnas y más columnas dummificadas** en lugar de escaladas? Es correcto que algunas variables, como las dummies de las causas de los accidentes, ya se encuentran en formato booleano y no necesitan ser escaladas, ya que su naturaleza es binaria (0 o 1). Sin embargo, las variables como distritos, barrios, incluso días de la semana, o meses, pueden ser categóricas (las de lugar, seguro y las de tiempo me han generado dudas). Ellas son o pueden ser categóricas, podrían haberse dummificado también, en lugar de simplemente transformarlas a enteros. Esto puede ser importante para que los algoritmos de clustering interpreten correctamente estas variables, ya que los valores enteros podrían inducir una relación ordinal que en realidad no existe.
