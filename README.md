# Analisis sectorial y territorial del empleo productivo en Argentina 2021-2022


## Introducción

   En el presente trabajo nos propusimos analizar el empleo registrado y la estructura productiva por provincia y departamento en Argentina.
El proyecto normaliza y enriquece los datos, calculando indicadores relevantes para el analisis, tales como HHI, brecha de genero, diversificación productiva y perfil exportador y genera visualizaciones y tablas listas para exportar en un visualizador de datos.

## Objetivos del proyecto

* Analizar la localización y densidad del empleo y los establecimientos productivos
* Medir y comparar la participación femenina en el aparato productivo
* Evaluar cuán diversificada o concentrada es la estructura sectorial de cada provincia
* Agrupar provincias en tipologias según sus perfiles productivos y de género

## Unidad de analisis

* Provincias y departamentos
* Agregaciones por **CLAEs** (`clae2` / `clae6`).

## Datos de entrada

- `Datos_por_departamento_y_actividad.csv`  
- `Datos_por_departamento_actividad_y_sexo.csv`  
- `distribucion_establecimientos_productivos_sexo.csv`  
- `actividades_establecimientos.csv`  
- `codigo_departamento_provincia.csv`

> Todos en codificación UTF-8. Para mayor detalle de los datasets utilizados, dirigase a la carpeta Data.

## Dependencias en R

- `tidyverse`  
- `janitor`  
- `ggcorrplot`  
- `maps`  
- `treemapify`  
- `ggrepel`  
- `scales`  
- `readr`

Instalación rápida:

```r
install.packages(c(
  "tidyverse","janitor","ggcorrplot","maps",
  "treemapify","ggrepel","scales","readr"
))
```

## Principales resultados

* Concentración del aparato productivo en la región pampeana
* Persistencia de brechas de género, más marcadas en el NEA y más acotadas en Patagonia
* Provincias diversificadas (ej. CABA, Buenos Aires) versus provincias con alta concentración (ej. Tucumán, Formosa, Tierra del Fuego)
* Tipologías productivas según diversificación y perfil exportador: **diversificadas y competitivas, especializadas y abiertas, diversificadas pero cerradas, especializadas y cerradas**

## Licencia 
Código bajo licencia MIT.
Los datos provienen de fuentes oficiales del Ministerio de Economía.

## Informe completo 
Te invitamos a que veas el **PDF del informe** que armamos, donde seguimos una metodología de *storytelling* para que puedas interiorizarte un poco más sobre el proyecto.

[docs/Analisis_sectorial.pdf](docs/Analisis%20sectorial%20y%20estructura%20productiva%20en%20Argentina.pdf)

Los gráficos y tablas se encuentran en la carpeta outputs/ y el detalle completo en el PDF

## Autores
Mariano Asorey & Victoria Michel – Universidad de Buenos Aires
