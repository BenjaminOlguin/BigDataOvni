# Informe del Proyecto GSP823: Proceso de Carga y Análisis de Datos - Avistamientos OVNI

**Integrantes:** Benjamín Olguín, Martín Quilodrán

---

##  Enlace

---

  **Página Web del Informe (GitHub Pages):**  
https://BenjaminOlguin.github.io/BigDataOvni/

---
##  Descripción General

Este proyecto fue desarrollado en el marco del laboratorio **GSP823** de Google Cloud.  
El objetivo fue llevar a cabo un proceso completo de carga, preparación, análisis y visualización de datos relacionados con avistamientos de OVNIs en Estados Unidos, utilizando herramientas avanzadas del ecosistema Google Cloud.

---

##  Proceso Paso a Paso

### 1 Creación del Bucket y Carga del Archivo a Cloud Storage

- Se creó un bucket en Google Cloud Storage con el nombre `martin_quilodran_es`.
- Se cargó el archivo CSV `ufo_sighting.csv` al bucket para su posterior análisis.

### 2 Creación del Dataset en BigQuery

- Se creó un dataset en BigQuery llamado `ovni` para organizar las tablas del análisis.

### 3 Importación y Preparación de Datos

- Se importó el archivo CSV desde Cloud Storage hacia BigQuery usando DataPrep.
- Se verificaron valores nulos y se identificaron datos incorrectos.

### 4 Transformación de la Columna `state/province`

- Se cambió el tipo de datos de la columna `state/province` a `STRING`.
- Se renombró la columna a `state_province` para evitar problemas con el caracter `/`.

### 5 Manejo de Valores Faltantes

- Se reemplazaron valores faltantes por textos personalizados como “Sin provincia” o “Sin país”.

### 6 Eliminación de Registros con Nulos Escasos

- Se eliminaron filas con valores nulos en columnas críticas donde los nulos eran escasos (por ejemplo, `ufo_shape`, `description`, `latitud`).

### 7 Cambio de Formato en la Columna `date_time`

- Se convirtió el formato de la columna `date_time` a un formato compatible con BigQuery: `yyyy-MM-dd hh:mm:ssa`.

### 8 Carga del Archivo Preparado

- Se cargó el archivo limpio desde DataPrep en la tabla `avistamientos` del dataset `ovni`.

### 9 Consultas a la Tabla `avistamientos`

Se realizaron las siguientes consultas SQL en BigQuery para extraer insights relevantes:

- **Cantidad de avistamientos por estado en EE.UU.**
- **Top 5 de las formas de OVNI más reportadas.**
- **Cantidad de avistamientos por año.**

### 10 Generación de Gráficos en Looker Studio

- Se construyeron visualizaciones en Looker Studio para representar gráficamente los resultados de las consultas, incluyendo:
    - Mapa de calor por estado.
    - Gráfico de torta de las formas más vistas.
    - Gráfico de barras por año.

---

##  Conclusión

Este proyecto permitió aplicar un flujo completo de análisis de datos usando herramientas de Google Cloud, desde la carga hasta la visualización.
Los resultados permiten explorar patrones de avistamientos OVNI en EE.UU. y entender mejor las tendencias históricas.

---



---
