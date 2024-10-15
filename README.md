# Cruso de algoritmos de agrupamiento - Joven investigador ITM 2024



<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Índice del Curso</title>
</head>
<body>
    <h1>Índice</h1>
    <ol>
        <li><a href="#1-Introducción-al-curso">Introducción al curso</a></li>
        <li>
            <a href="#2-Instalación-de-librerías-necesarias">Instalación de librerías necesarias</a>
            <ul>
                <li><a href="#Entornos-venv">Entornos venv</a></li>
                <li><a href="#Entornos-con-anaconda">Entornos con Anaconda</a></li>
                <li><a href="#Trabajar-en-colab">Trabajar en Colab</a></li>
            </ul>
        </li>
        <li>
            <a href="#3-Introducción-a-las-secciones">Introducción a las secciones</a>
            <ul>
                <li><a href="#Sección-1-Generación-de-datos">Sección 1 Generación de datos</a></li>
                <li><a href="#Sección-2-K-means">Sección 2 K-means</a></li>
                <li><a href="#Sección-3-Spectral-Clustering">Sección 3 Spectral Clustering</a></li>
                <li><a href="#Sección-4-DBSCAN">Sección 4 DBSCAN</a></li>
            </ul>
        </li>
    </ol>

</body>

# 1. Introducción al curso

El propósito de este curso es ofrecer una guía sobre algunos modelos de aprendizaje de máquinas (ML, por sus siglas en inglés), específicamente en la rama del aprendizaje no supervisado (modelos de clustering o agrupamiento). Ademas, antes de implementar estos modelos, se ensenara como implementar y crear datos que nos permitan experimentar una vez que los algoritmos tratados en este curso.

# 2 Instalación de librerías necesarias

## Entornos venv

```sh
git clone
cd Curso_joven_investigador_ITM_2024
python3 -m venv env
source env/bin/activate
pip3 install -r requirements.txt
```
## Entornos con anaconda

```sh
git clone 
cd Curso_joven_investigador_ITM_2024
conda create --name mi_entorno python=3.9
conda activate mi_entorno
pip install -r requirements.txt
```

## Trabajar en Colab

| **Notebook sección 1** | **Notebook sección 2** | **Notebook sección 3** | **Notebook sección 4** |
|-------------------------|-------------------------|-------------------------|-------------------------|
| [![Open In Colab seccion 1](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/miguel-solarte/Curso_joven_investigador_ITM_2024/blob/main/Seccion1_GeneracionSD.ipynb) | [![Open In Colab seccion 2](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/miguel-solarte/Curso_joven_investigador_ITM_2024/blob/main/Seccion2_K-means.ipynb) | [![Open In Colab seccion 3](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/miguel-solarte/Curso_joven_investigador_ITM_2024/blob/main/Seccion3_SC.ipynb) | [![Open In Colab seccion 4](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/miguel-solarte/Curso_joven_investigador_ITM_2024/blob/main/Seccion4_DBSCAN.ipynb) |



# 3. Introducción a las secciones

## Sección 1 Generación de datos

En esta sección, proporcionaremos una guía para crear datos sintéticos, desarrollando nuestro propio marco básico que utilizaremos en secciones posteriores. Además, exploraremos otro Framework especializado en ML, el cual provee clases y métodos para generar ciertos tipos de datos de prueba.

## Sección 2 K-means

En esta sección, implementaremos un algoritmo clásico de machine learning llamado K-means. Este algoritmo identifica grupos a partir de la actualización de la posición de puntos llamados centroides. La cantidad de centroides se asigna según el número de grupos que se desea identificar. Los centroides calculan las distancias entre ellos y los puntos en el espacio, actualizando su posición basándose en la media de las posiciones de los puntos más cercanos. Después de varias iteraciones, los centroides ya no modificarán su posición, y los puntos más cercanos a cada uno formarán un grupo. Finalmente, habrá tantos grupos como centroides se hayan asignado.

## Sección 3 Spectral Clustering

En la sección anterior, implementamos y probamos K-means, encontrando que este algoritmo es efectivo principalmente para agrupar datos cuando los grupos tienen formas relativamente simples. Sin embargo, su efectividad se ve limitada cuando los grupos presentan formas muy complejas, debido al uso de la distancia euclidiana para calcular las similitudes entre los centroides y los puntos en el espacio. Por lo tanto, es crucial considerar otros algoritmos para agrupar datos que presenten formas más complejas. Scikit-learn proporciona una buena descripción de cuándo utilizar el clustering espectral (Spectral clustering): este método resulta muy útil cuando la estructura de los grupos individuales es altamente no convexa o cuando la medida de centro y extensión de un grupo no es adecuada para describir el grupo completo. Esto es especialmente relevante en situaciones donde los grupos están anidados o tienen formas como círculos en un plano 2D: https://scikit-learn.org/stable/modules/generated/sklearn.cluster.SpectralClustering.html

## Sección 4 DBSCAN

Una vez analizados los algoritmos K-means, que genera grupos a partir de la distancia entre centroides y los puntos del conjunto de datos, y Spectral Clustering, que forma grupos basándose en información obtenida con vectores propios, ahora analizaremos el algoritmo de *Agrupamiento Espacial Basado en Densidad de Aplicaciones con Ruido* (DBSCAN por sus siglas en inglés) . Este algoritmo tiene un enfoque diferente para la generación de grupos, basado en la densidad.