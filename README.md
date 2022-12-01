
![alt text](logo.png "logo")

# Introducción a la visión por ordenador, ejercicios

Este repositorio contiene ejercicios de código y materiales para el programa de Introducción a la Visión por Computador de IA CENTER. Consiste en cuadernos tutoriales que demuestran, o te retan a completar, varias aplicaciones y técnicas de visión por ordenador. Estos cuadernos dependen de una serie de paquetes de software para ejecutarse, por lo que le sugerimos que cree un entorno local con estas dependencias siguiendo las instrucciones que se indican a continuación.

Traducción realizada con la versión gratuita del traductor www.DeepL.com/Translator

# Configure y gestione su entorno con Anaconda

Anaconda [docs](http://conda.pydata.org/docs):

> Conda es un sistema de gestión de paquetes y de entornos de código abierto 
para instalar múltiples versiones de paquetes de software y sus dependencias y 
dependencias y cambiar fácilmente entre ellas. Funciona en Linux, OS X y Windows, y fue creado 
para programas de Python, pero puede empaquetar y distribuir cualquier software.

## Resumen
El uso de Anaconda consiste en lo siguiente:

1. Instale [`miniconda`](http://conda.pydata.org/miniconda.html) en su ordenador, seleccionando la última versión de Python para su sistema operativo. Si ya tienes instalado `conda` o `miniconda`, deberías poder saltarte este paso y pasar al paso 2.
2. Cree y active * un nuevo [entorno] `conda` (http://conda.pydata.org/docs/using/envs.html).

\* Cada vez que desee trabajar en cualquier ejercicio, active su entorno `conda`.

---

## 1. Installation
**Descargue** la última versión de `miniconda` que corresponda a su sistema.

**NOTA**: Se han reportado problemas al crear un entorno con miniconda `v4.3.13`. Si te da problemas prueba con las versiones `4.3.11` o `4.2.12` de [aquí](https://repo.continuum.io/miniconda/).

|        | Linux | Mac | Windows | 
|--------|-------|-----|---------|
| 64-bit | [64-bit (bash installer)][lin64] | [64-bit (bash installer)][mac64] | [64-bit (exe installer)][win64]
| 32-bit | [32-bit (bash installer)][lin32] |  | [32-bit (exe installer)][win32]

[win64]: https://repo.continuum.io/miniconda/Miniconda3-latest-Windows-x86_64.exe
[win32]: https://repo.continuum.io/miniconda/Miniconda3-latest-Windows-x86.exe
[mac64]: https://repo.continuum.io/miniconda/Miniconda3-latest-MacOSX-x86_64.sh
[lin64]: https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh
[lin32]: https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86.sh

**Instale** [miniconda](http://conda.pydata.org/miniconda.html) en su máquina. Instrucciones detalladas:

- **Linux:** http://conda.pydata.org/docs/install/quick.html#linux-miniconda-install
- **Mac:** http://conda.pydata.org/docs/install/quick.html#os-x-miniconda-install
- **Windows:** http://conda.pydata.org/docs/install/quick.html#windows-miniconda-install

## 2. Crear y activar el entorno

Para los usuarios de Windows, los siguientes comandos deben ser ejecutados desde el **puntero de Anaconda** en lugar de una ventana de terminal de Windows. Para Mac, una ventana de terminal normal funcionará. 

#### Git y el control de versiones
Estas instrucciones también asumen que tienes `git` instalado para trabajar con Github desde una ventana de terminal, pero si no lo tienes, puedes descargarlo primero con el comando
```
conda install git
```

Si quieres aprender más sobre el control de versiones y el uso de `git` desde la línea de comandos, echa un vistazo a nuestro [curso gratuito: Control de versiones con Git](https://www.udacity.com/course/version-control-with-git--ud123).

**Ahora, estamos listos para crear nuestro entorno local.

1. Clona el repositorio, y navega a la carpeta descargada. Esto puede tomar un minuto o dos para clonar debido a los datos de la imagen incluida.
```
git clone https://github.com/udacity/cd0360-Introduction-to-Computer-Vision.git
cd0360-Introducción a la Visión Artificial
```

2. Crea (y activa) un nuevo entorno, llamado `cv-nd` con Python 3.6. Si se le pide que proceda con la instalación `(Proceed [y]/n)` escriba y.

	- __Linux__ o __Mac__: 
	```
	conda create -n cv-nd python=3.6
	source activate cv-nd
	```
	- __Windows__: 
	```
	conda create --name cv-nd python=3.6
	activate cv-nd
	```
	
	En este punto tu línea de comandos debería ser algo así: `(cv-nd) <Usuario>:cd0360-Introducción a la Visión Artificial <usuario>$`. El `(cv-nd)` indica que su entorno ha sido activado, y puede proceder a la instalación de más paquetes.

3. Instale PyTorch y torchvision; esto debería instalar la última versión de PyTorch.
	
	- __Linux__ o __Mac__: 
	```
	conda install pytorch torchvision -c pytorch 
	```
	- Windows: 
	```
	conda install pytorch-cpu -c pytorch
	pip install torchvision
	```

6. Instalar algunos paquetes pip necesarios, que se especifican en el archivo de texto de requisitos (incluyendo OpenCV).
```
pip install -r requirements.txt
```

7. Eso es todo.

Ahora todas las librerías `cv-nd` están disponibles para ti. Asumiendo que tu entorno sigue activado, puedes navegar al repositorio de Ejercicios y empezar a mirar los cuadernos:

```
cd
cd dir 
notebook jupyter
```

Para salir del entorno cuando haya terminado su sesión de trabajo, simplemente cierre la ventana del terminal.

### Notas sobre la creación y eliminación de entornos

**Verifique** que el entorno `cv-nd` fue creado en sus entornos:

```
conda info --envs
```

**Limpiar** las bibliotecas descargadas (eliminar los tarballs, archivos zip, etc):

```
conda clean -tp
```

**Desinstalar** el entorno (si quieres); puedes eliminarlo por su nombre:

```
conda env remove -n cv-nd