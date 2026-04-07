# Evolución Electoral en España (1977 – 2023)

> Dashboard interactivo que analiza más de 45 años de historia electoral española, desde las primeras elecciones democráticas hasta las de 2023.

## Características del Dashboard

El dashboard está construido en **R** utilizando `plotly` y `crosstalk` para máxima interactividad, e incluye **4 paneles principales**:

| Panel | Descripción |
|-------|-------------|
| **Evolución del Voto Nacionalista** | Fuerza del voto nacionalista e independentista sobre el total de su comunidad (Cataluña y País Vasco/Navarra). |
| **Mapa Animado del Partido Ganador** | Mapa coroplético de España con slider temporal que muestra el partido ganador por provincia en cada elección. |
| **Evolución de Partidos Nacionales** | Tendencia histórica del porcentaje de voto de los principales partidos (PSOE, PP, UCD/CDS, Sumar/Podemos, Vox, Ciudadanos, IU/PCE). |
| **Top 5 Partidos por Provincia** | Gráfico de barras interactivo con filtros desplegables por año y provincia. |


## 🛠️ Tecnologías y Librerías

| Área | Herramientas |
|------|-------------|
| **Datos y Limpieza** | `tidyverse`, `dplyr`, `stringr`, `readr`, `lubridate` |
| **Fuente de Datos** | Paquete `infoelectoral` (datos oficiales del Ministerio del Interior) |
| **Visualización y Mapas** | `ggplot2`, `plotly`, `mapSpain`, `sf`, `scales` |
| **Interactividad** | `plotly`, `crosstalk`, `htmltools` |


## 🧹 Procesamiento de Datos (ETL)

El proyecto incluye un exhaustivo proceso de limpieza y transformación:

- **Descarga programática** de datos raw de 16 elecciones generales vía API del Ministerio del Interior.
- **Limpieza de cadenas de texto**: normalización de acentos, signos de puntuación y codificación.
- **Unificación de siglas**: agrupación de cientos de micro-partidos, marcas blancas y coaliciones temporales en bloques coherentes para permitir el análisis longitudinal (ej. AP/CP/PP, IU/PCE, espacios y escisiones).

## Cómo utilizar el proyecto

### Opción 1: Ver el Dashboard (Recomendado)

Descarga o clona el repositorio y abre `dashboard_elecciones.html` en cualquier navegador moderno. No requiere instalación de R ni servidor — es un documento HTML estático y autocontenido.

### Opción 2: Reproducir el análisis en R

1. Clona el repositorio.
2. Abre R o RStudio.
3. Abre `dashboard_elecciones.Rmd` y pulsa **Knit** (o ejecuta `rmarkdown::render("dashboard_elecciones.Rmd")`).

> **Nota**: La descarga de datos y la generación del mapa animado pueden tardar varios minutos.

## 📁 Estructura del Repositorio

```
├── dashboard_elecciones.Rmd            # Código fuente (ETL + visualización)
├── dashboard_elecciones.html           # Dashboard interactivo exportado
├── elecciones_espana_1977_2023.csv     # Dataset limpio y procesado
├── dashboard_tableau.twb               # Visualizaciones complementarias en Tableau
├── codigos_provincias.RData            # Diccionario de datos para cruces geográficos
└── README.md
```
