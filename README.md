# Evolución Electoral en España (1977 - 2023)

![Dashboard Preview](dashboard_elecciones_files/preview.png) *(Nota: Sustituye con una imagen real del dashboard)*

Este proyecto presenta un análisis interactivo y exhaustivo de la evolución electoral en España desde las primeras elecciones democráticas en 1977 hasta las últimas en 2023. Además del análisis puramente descriptivo, el proyecto incorpora técnicas de Machine Learning para agrupar y entender los perfiles de voto de las diferentes provincias.

## 📊 Características del Dashboard

El dashboard está construido en R utilizando `plotly` y `crosstalk` para máxima interactividad, e incluye 6 paneles principales:

1. **Evolución del Voto Nacionalista**: Gráfico de líneas que muestra la fuerza del voto nacionalista e independentista sobre el total de su comunidad (Cataluña y País Vasco/Navarra).
2. **Mapa Animado del Partido Ganador**: Un mapa coroplético de España que muestra el partido ganador por provincia a lo largo del tiempo, con un slider interactivo temporal.
3. **Evolución de Partidos Nacionales**: Evolución histórica del porcentaje de voto de los principales partidos a nivel nacional (PSOE, PP, UCD/CDS, Sumar/Podemos, Vox, Ciudadanos, IU/PCE).
4. **Top 5 Partidos por Provincia**: Gráfico de barras horizontal interactivo, vinculado a controles desplegables (filtros por Año y Provincia) para ver el detalle específico de cualquier momento y lugar.
5. **Agrupación por Perfil de Voto (K-Means)**: Mapa que muestra el resultado de aplicar un algoritmo K-Means a los resultados de 2023, agrupando a las provincias en 4 clusters según su similitud en el comportamiento electoral.
6. **Ejes Políticos Subyacentes (PCA)**: Un biplot generado mediante Análisis de Componentes Principales que revela las dimensiones que más explican las variaciones de voto entre provincias.

## 🛠️ Tecnologías y Librerías

El proyecto está desarrollado completamente en **R** utilizando `RMarkdown`.

- **Datos y Limpieza**: `tidyverse`, `dplyr`, `stringr`, `readr`, `lubridate`
- **Fuente de Datos**: Paquete `infoelectoral` (datos oficiales del Ministerio del Interior)
- **Visualización Estática y Mapas**: `ggplot2`, `mapSpain`, `sf`, `scales`
- **Interactividad y Dashboard**: `plotly`, `crosstalk`, `htmltools`
- **Machine Learning**: `stats` (funciones base de R `kmeans` y `prcomp`)

## 🧹 Procesamiento de Datos

El trabajo incluye un exhaustivo proceso de ETL (Limpieza y Transformación de Datos) documentado en el código:
- Descarga programática de datos raw de 16 elecciones.
- Limpieza de cadenas de texto (acentos, signos de puntuación).
- **Unificación de Siglas**: Agrupación de cientos de micro-partidos, marcas blancas y coaliciones temporales en bloques coherentes para permitir el análisis longitudinal (ej. AP/CP/PP, IU/PCE, espacios y escisiones).

## 🚀 Cómo Ejecutar el Proyecto

### Opción 1: Ver el Dashboard (Recomendado)
Simplemente descarga o clona el repositorio y abre el archivo `dashboard_elecciones.html` en cualquier navegador web moderno. No requiere instalación de R ni de un servidor, ya que es un documento HTML estático y autocontenido.

### Opción 2: Reproducir el Análisis en R
Si deseas recompilar el código fuente o modificar el análisis:

1. Clona el repositorio.
2. Abre R o RStudio.
3. Asegúrate de tener los paquetes necesarios instalados (el script los instalará si faltan).
4. Abre `dashboard_elecciones.Rmd`.
5. Pulsa el botón **Knit** (o ejecuta `rmarkdown::render("dashboard_elecciones.Rmd")`).

> **Nota**: El proceso de descarga (`Descarga de datos`) y de generación del mapa animado pueden tardar varios minutos en ejecutarse.

## 📁 Estructura del Repositorio

- `dashboard_elecciones.Rmd`: Código fuente principal con todo el análisis de datos, Machine Learning y código de visualización.
- `dashboard_elecciones.html`: El dashboard final interactivo exportado.
- `memoria.pdf`: Memoria detallada del proyecto (contexto, metodología).
- `dashboard_tableau.twb`: Archivo complementario con visualizaciones implementadas en Tableau.
- `final_master.csv`: Dataset final limpio procesado, listo para consumir.
- `codigos_provincias.RData`: Diccionario de datos para cruces geográficos.

## 👨‍💻 Autor

*(Añade aquí tu nombre e información de contacto/LinkedIn/Portafolio)*
