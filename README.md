# ######**THIS IS A WORK IN PROGRESS REPOSITORY**######

Disclaimer : This project is not finished yet (work in process). Also, there are a few issues with the Jupyter Notebook in GitHub that do not exist in the local environment and they have to be fixed: the interactive city maps generated with Folium appear in blank as GitHub does not display them automatically and very early they block the loading of the rest of the work. Solutions such as HTML, ineserting as image or creating separate links are some of the posibilities.

# **Datos de accidentes recogidos por la Guàrdia Urbana en 2023 en la ciudad de Barcelona**

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

Introducción: Presentació de los objetivos, métodología y principales observaciones.
   
Limpieza y transformación de datos: Descripción detallada de las técnicas de preprocessado aplicadas y criterios de evaluación.

Entrenamiento de modelos y resultados obtenidos: 

Conclusions: Principales inferencias derivadas de los resultados conseguidos.

## **Conclusión**

**Interpretación de las métricas obtenidas con K-Means:**

**El Silhouette Score** 

**Davies-Bouldin Index**: 

**¿Qué significa este resultado?**


**Mejoras posibles**:


