# Análisis de Series Temporales con DTW

Este proyecto implementa un análisis comparativo de trayectorias económicas de países utilizando Dynamic Time Warping (DTW) y clustering.

## Estructura del Proyecto

```
ST/
├── data/
│   ├── indicadores/          # Datos de indicadores económicos (World Bank)
│   │   └── todos_los_datos.csv
│   ├── clusters_input/       # Archivos de clustering de entrada
│   │   ├── clusters_2022_bco_mundial.csv
│   │   ├── clusters_2022_4C_gni_index.csv
│   │   └── clusters_dtw_4C.csv
│   └── outputs/
│       ├── cache/            # Matriz de distancias DTW precalculada
│       └── dtw_analysis_results/  # Resultados de análisis
├── src/
│   └── notebooks/            # Notebooks Jupyter del análisis
│       ├── 01_Generate_DTW_Cache.ipynb
│       ├── 02_analizar_dtw.ipynb
│       ├── 03_clustering_dtw.ipynb
│       └── 04_Conclusiones_Analisis_DTW.ipynb
└── requirements.txt
```

## Notebooks de Análisis

1. **01_Generate_DTW_Cache.ipynb**: Genera y cachea la matriz de distancias DTW entre países (9,870 comparaciones de 141 países)
2. **02_analizar_dtw.ipynb**: Análisis exploratorio de las distancias DTW y patrones
3. **03_clustering_dtw.ipynb**: Clustering basado en DTW con dashboard interactivo para visualizar trayectorias
4. **04_Conclusiones_Analisis_DTW.ipynb**: Análisis comparativo entre clusters del Banco Mundial y K-Means

## Configuración del Ambiente Virtual

### 1. Crear el Ambiente Virtual

Navega hasta la carpeta del proyecto:
```bash
cd /ruta/a/tu/proyecto
```

Crea el ambiente virtual:
```bash
python3 -m venv series_temporales_env
```

### 2. Activar el Ambiente Virtual

```bash
source series_temporales_env/bin/activate
```

Verifica que el ambiente está activado viendo `(series_temporales_env)` al inicio de la línea en la terminal.

### 3. Instalar Dependencias

```bash
pip install -r requirements.txt
```

### 4. Registrar el Kernel en Jupyter

```bash
pip install ipykernel
python -m ipykernel install --user --name=series_temporales_env --display-name "Python (series_temporales_env)"
```

### 5. Usar en VS Code

1. Abre VS Code y navega hasta la carpeta del proyecto
2. Abre cualquier notebook (.ipynb)
3. En la esquina superior derecha, haz clic en el selector de kernel
4. Selecciona "Python (series_temporales_env)"

### 6. Verificar la Configuración

Ejecuta en una celda del notebook:
```python
import sys
print(sys.executable)
```

Debe mostrar la ruta dentro de `series_temporales_env` del proyecto.

## Dependencias Principales

- **pandas, numpy**: Manipulación de datos
- **matplotlib, seaborn, plotly**: Visualización
- **holoviews, bokeh, panel**: Dashboards interactivos
- **tslearn, dtaidistance**: Análisis de series temporales y DTW
- **scikit-learn**: Clustering K-Means
- **statsmodels**: Análisis estadístico de series temporales
- **geopandas**: Visualización geoespacial

## Uso

1. Activa el ambiente virtual
2. Abre VS Code en la carpeta del proyecto
3. Ejecuta los notebooks en orden (01 → 02 → 03 → 04)
4. El notebook 03 incluye un dashboard interactivo para explorar trayectorias de países con opciones de filtrado y esquemas de color

## Datos

Los datos de indicadores económicos provienen del Banco Mundial. El análisis se enfoca en la trayectoria del GNI per cápita (1992-2022) de 141 países con datos completos.
