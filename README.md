# Analisis sectorial y territorial del empleo productivo en Argentina 2021-2022


##  Introducción

   En el presente trabajo nos propusimos analizar el empleo registrado y la estructura productiva por provincia y departamento en Argentina.
El proyecto normaliza y enriquece los datos, calculando indicadores relevantes para el analisis, tales como HHI, brecha de genero, diversificación productiva y perfil exportador y genera visualizaciones y tablas listas para exportar en un visualizador de datos.

### ▬ Objetivos del proyecto

* Analizar la localización y densidad del empleo y los establecimientos productivos
* Medir y comparar la participación femenina en el aparato productivo
* Evaluar cuán diversificada o concentrada es la estructura sectorial de cada provincia
* Agrupar provincias en tipologias según sus perfiles productivos y de género

### ▬ Unidad de analisis

* Provincias y departamentos
* Agregaciones por **CLAEs** (`clae2` / `clae6`).

### ▬ Datos de entrada

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

## 🔎 Principales resultados

* Concentración del aparato productivo en la región pampeana
* Persistencia de brechas de género, más marcadas en el NEA y más acotadas en Patagonia
* Provincias diversificadas (ej. CABA, Buenos Aires) versus provincias con alta concentración (ej. Tucumán, Formosa, Tierra del Fuego)
* Tipologías productivas según diversificación y perfil exportador: **diversificadas y competitivas, especializadas y abiertas, diversificadas pero cerradas, especializadas y cerradas**

## 📄Informe completo 
Te invitamos a que veas el **PDF del informe** que armamos, donde seguimos una metodología de *storytelling* para que puedas interiorizarte un poco más sobre el proyecto.

 [Ver informe en PDF](docs/Análisis%20sectorial%20y%20territorial%20del%20empleo%20productivo%20en%20Argentina%20(2021%20-%202022).pdf)


Los gráficos y tablas se encuentran en la carpeta outputs/ y el detalle completo en el PDF

## 📊 Nuevas variables creadas en el proceso de análisis

Durante la fase de procesamiento y enriquecimiento de los datos, se generaron una serie de variables derivadas que permiten analizar la estructura productiva, la concentración económica y la equidad de género desde múltiples dimensiones.  
Estas variables no existen en los datasets originales y fueron creadas íntegramente en R.

### Variables derivadas

| **Variable** | **Descripción** | **Cálculo / Procedencia** |
|--------------|------------------|-----------------------------|
| **empleo_total** | Total de empleo registrado por provincia o departamento. | Suma de `empleo`. |
| **prop_mujeres** | Proporción promedio de mujeres empleadas. | Promedio de `proporcion_mujeres`. |
| **brecha_genero** | Medición respecto de la paridad (0.5). Valores negativos indican menor participación femenina. | `prop_mujeres - 0.5`. |
| **n_sectores** | Diversificación económica según cantidad de sectores (CLAE2). | `n_distinct(clae2)`. |
| **HHI** | Índice Herfindahl–Hirschman, que mide concentración sectorial del empleo. | Suma de participaciones sectoriales al cuadrado. |
| **sector_agregado** | Clasificación de actividades CLAE en grandes agrupamientos productivos. | Definido vía `case_when()`. |
| **n_est** | Número total de establecimientos productivos en la provincia. | Conteo de registros en `establecimientos`. |
| **porcentaje** | Participación regional sobre el total nacional de establecimientos. | `(total_region / total_nacional) * 100`. |
| **variacion_pct** | Variación porcentual del empleo entre 2021 y 2022 por gran sector. | `(empleo_2022 - empleo_2021) / empleo_2021 * 100`. |
| **prop_exportadoras** | Proporción de empresas exportadoras sobre el total. | `empresas_exportadoras / empresas_totales`. |
| **cuadrante** | Tipología productiva según diversificación (HHI) y perfil exportador. | Clasificación por mediana de HHI y exportaciones. |

Estas variables permiten construir los mapas, correlogramas, treemaps, comparativos interanuales y el modelo en estrella exportado a Power BI.

## 👥 Autores
Mariano Asorey & Victoria Michel – Universidad de Buenos Aires
