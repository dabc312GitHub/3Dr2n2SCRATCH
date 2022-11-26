# Implementación del paper 3D-R2N2 para la Reconstrucción 3D con Voxeles
- Esta implementación fue realizada con pytorch basada en el paper: ["3D-R2N2: A Unified Approach for Single and Multi-view 3D Object Reconstruction"](http://arxiv.org/abs/1604.00449) by Choy et al. 
- Para esta implementación se tiene por input una o multiples vistas de imágenes de un objeto para que la red neuronal proceda a desarrollar la reconstrucción 3D voxelizada.  
- La implemetación base se tiene desde el siguiente repositorio del paper: ["chrischoy/3D-R2N2"](http://github.com/chrischoy/3D-R2N2), esta implementación del paper fue desarrollado con la librería Theano.

## Instalación y configuración inicial
El siguiente código fue desarrollado bajo las siguientes características:
- Ubuntu 18.04.6 LTS
- Intel® Core™ i5-10400F CPU @ 2.90GHz × 12 
- GPU NVIDIA GeForce RTX 3060/PCIe/SSE2
- RAM 16 GB
- Python 3.6 en Conda  

### 1. Descargar el repositorio
```bash
git clone https://github.com/dabc312GitHub/3Dr2n2SCRATCH.git
```

### 2. Instalar requisitos
```bash
cd 3Dr2n2SCRATCH
conda create -n 3dr2n2Torch python=3.6
source activate 3dr2n2Torch
```

Para instalar desde conda se requiere lo siguiente que se encuentra en search Anaconda
```bash
conda install -c intel numpy
conda install -c cctbx202008 pillow
conda install -c scw tensorboardx
```

Para instalar pytorch se requiere saber la arquitectura NVIDIA con la cual se trabaja, en mi caso es suficiente la versión 10 de cudatoolkit
```bash
conda install pytorch==1.1.0 torchvision==0.3.0 cudatoolkit=10.0 -c pytorch
```

### 3. Descargar la Dataset   
```bash
mkdir ShapeNet/
wget http://cvgl.stanford.edu/data2/ShapeNetRendering.tgz
wget http://cvgl.stanford.edu/data2/ShapeNetVox32.tgz
tar -xzf ShapeNetRendering.tgz -C ShapeNet/
tar -xzf ShapeNetVox32.tgz -C ShapeNet/
```

### 4. Configurar los parámetros y entrenar la Red Neuronal
Crear o modificar el archivo `config.ini` para que al ejecutar el archivo `train.py` 
pueda ser llevado de la siguiente manera:
```bash
python train.py --cfg=config.ini
```

### 5. Probar la red neuronal entrenada
Crear o modificar el archivo `config.ini` para que al ejecutar el archivo `test.py` 
pueda ser llevado de la siguiente manera:
```bash
python test.py --cfg=config.ini
```
