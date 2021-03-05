# Cells features extractor

Es necesario tener instalado python3 y la biblioteca de [scipy] o [anaconda]. Además es necesario instalar la biblioteca [spikelib] directo de su repositorio o a través de pip:

```sh

$ pip install spikelib

```
Para evitar errores con la biblioteca [neuroshare] se recomienda instalar clonando su repositorio y desde su directorio ejecutar
```sh

$ pip install .

```
El repositorio contiene dos notebooks que extraen features:
- **01 - EDA_sorting_general-view.ipynb:** Extrae spike_rates, isi, autocorrelogramas y un visualizador de crosscorrelograma del experimento completo y por intervalos de estímulo. Además de generar un rasterplot y isi_clustermap del experimento.
Es necesario crear una carpeta con el nombre del experimento en el directorio *experiments* e incorporar los archivos de sorting e intervalos de tiempo. Con el repositorio se incorpora el experimento *MR-261_t2* como ejemplo y se pueden encontrar los archivos:
	- MR-261_t2.result.hdf5
	- MR-261_t2-intervals.csv

	Además es posible incorporar el archivo *cell_index.txt* que contiene los índices de células que desean ser exploradas en particular. En caso de estar ausente las celdas de código recorrerán las células del experimento por completo.
	Las celdas de código poseen instrucciones para su ejecución. Replicar el orden de los archivos de ejemplo para no tener errores al cambiar de experimento.
	
- **02 - VIS_templates_extraction.ipynb:** Extrae forma de templates por célula en el experimento y determina puntos de interés como intensidad de los hombros del template, cruce por la mitad de intensidad y diferencias de tiempo, todo respecto al punto de máximo potencial. 
Al igual que el notebook anterior es necesario agregar el archivo de templates a la carpeta respectiva en el directorio *experiments*. En este caso el repositorio cuenta con un archivo de ejemplo para el experimento *MR-261_t2*:

	- MR-261_t2.templates.hdf5

	Las figuras de templates son almacenadas y se genera un csv con los features extarídos por célula.

Se creará la carpeta results con las figuras correspondientes además de los archivos de features extraídos. Se insta a revisar los archivos de ejemplo para el experimento *MR-261_t2* para evitar errores con otros análisis.

Los detalles de los script a ejecutar se encuentra dentro del notebook

  

[scipy]: <https://www.scipy.org/>

[anaconda]: <https://www.anaconda.com/>

[spikelib]: <https://github.com/creyesp/spikelib/>

[neuroshare]: <https://github.com/G-Node/python-neuroshare>