# Guía de trabajo e Instrucciones de Instalación
Como ya hemos comentado, este primer módulo lo dedicaremos a la puesta a punto de los programas que vamos a usar durante el curso. En primer lugar, veremos las posibilidades de la plataforma GitHub para la gestión del trabajo en grupo. Posteriormente, instalaremos las aplicaciones intérpretes de Python y una vez configurado, crearemos el entorno de trabajo local para cada uno de nosotros, en el que será libre de probar el código que quiera.

## Introducción a GitHub
Os he hecho haceros la cuenta en GitHub por una razón muy sencilla: facilitarnos el trabajo a todos y qu tengáis disponible la totalidad del curso cuando queráis con el plus de poder probar el código facilitado que cada uno quiera y crear el suyo propio en su entorno de trabajo.
Para ello vamos a necesitar instalar el siguiente programa, cuyo enlace aparece debajo de la siguiente imagen:

<p align = "center">
<img src = "https://user-images.githubusercontent.com/88738496/186197265-554893e2-2862-4152-b8a5-58bd19fe299e.png">
</p>
<p align = "center">
<strong>Fig.1 - GitBash Logo </strong>
</p>

Git para Windows se enfoca en ofrecer un conjunto de herramientas nativas y livianas que brindan el conjunto completo de funciones de Git SCM a Windows al mismo tiempo que proporciona interfaces de usuario adecuadas para usuarios de Git experimentados y novatos por igual. Git para Windows proporciona una emulación de BASH que se usa para ejecutar Git desde la línea de comandos y desde la cual "descargaremos" y "subiremos" nuestro contenido a la plataforma.

Cuando lo hayamos instalado, siguiendo las opciones por defecto, iniciamos la Aplicación GitBash y encontramos algo como esto:

<p align = "center">
<img src = "https://user-images.githubusercontent.com/88738496/186214955-0a9b3300-7d9f-4662-8914-55f371a7355b.JPG" width="600" height"400">
</p>
<p align = "center">
<strong>Fig.2 - GitBash Prompt </strong>
</p>

Ahora es el momento de configurar nuestro usuario GitHub en GitBash para poder hacer las comunicaciones de la plataforma con nuestro ordenador. Dentro de la terminal de GitBash, introducimos en siguiente código:

Primero el nombre de usuario de GitHub:

```
git config --global user.name "NombreDeUsuarioDeGitHub"
```
Y ahora el e-mail de la cuenta:
```
git config --global user.email "TuEmail@example.com"
```
Si queremos comprobar que todo está correctamente ejecutado, basta con poner

```
git config user.name 
```
Y debe aparecer tu nombre de usuario de GitHub, y lo mismo con el email:
```
git config user.email 
```
Para más seguridad en el trabajo, vamos a crear una clave SSH, única para el ordenador en el que se esté trabajando que permitirá subir y descargar archivos solo a nuestro dispositivo. La clave SSH consiste en la generación de un par de claves que proporcionan dos largas cadenas de caracteres (una pública y una privada). La clave pública se instala en cualquier servidor y luego se desbloquea mediante la conexión con un cliente SSH que hace uso de la clave privada. Escribe lo siguiente en la terminal de gitbash:
```
ssh-keygen -t rsa -C "youremail@ajsnd.com"
```

- **ssh-keygen**: La herramienta de línea de comandos utilizada para crear un nuevo par de claves SSH. Puedes ver sus banderas con `ssh-keygen` help.
- **t rsa**: La bandera -t se utiliza para indicar el algoritmo utilizado para crear la firma digital del par de claves. Si tu sistema lo soporta, `rsa` es el mejor algoritmo que puedes utilizar para crear pares de claves SSH.
- **C «email»**: La bandera -c se utiliza para proporcionar un comentario personalizado al final de la clave pública, que suele ser el correo electrónico o la identificación del creador del par de claves.

Después de escribir el comando en tu terminal, tendrás que introducir el archivo en el que quieres guardar las claves. Por defecto, se encuentra en tu directorio personal, en una carpeta oculta llamada «.ssh», pero puedes cambiarla por la que quieras (nosotros vamos a dejarlo así y le damos a intro). A continuación, se te pedirá una frase de contraseña para añadir a tu par de claves. Esto añade una capa extra de seguridad si, en algún momento, tu dispositivo se ve comprometido. No es obligatorio añadir una frase de contraseña, pero siempre es recomendable, tampoco lo vamos a añadir, y le damos a intro.

Posteriormente, escribiremos lo siguiente en la terminal:
```
cd ~/.ssh
```
Damos intro y escribimos
```
ls
```
Aquí encontramos las claves que se han generado, y como veremos, debe haber una de ellas con el nombre: id_rsa.pub
Acontinuación escribiremos:
```
cat id_rsa.pub
```
Ahora saldrá la parte de la clave pública completa, la cual copiaremos en el portapapeles (usando el botón derecho, copiar) y posteriormente pegaremos en la plataforma. Aquí se muestra una imagen de todo el proceso:

<p align = "center">
<img src = "https://user-images.githubusercontent.com/88738496/186211643-6109ff62-975e-484b-9f6b-dbf87896ea1e.JPG">
</p>
<p align = "center">
<strong>Fig.3 - Proceso de generación de una SSH key </strong>
</p>

Ahora nos vamos a GitHub, entramos en Settings-->SSH and GPG Keys-->Generate new SSH Key   y pegamos lo copiado en el portapapeles. Le damos un nombre y listo, ya tenemos la clave configurada para el PC

Ahora ya podemos clonarnos el repositorio del Curso en nuestro ordenador local. Lo único que tendremos que hacer es abrir el link del repositorio en GitHub y copiamos la clave SSH en el portapapeles:

<p align = "center">
<img src = "https://user-images.githubusercontent.com/88738496/186213000-e86cac90-606c-4ae0-b61c-6fa31b10cbde.JPG">
</p>
<p align = "center">
<strong>Fig.4 - Copia SSH key en portapapeles </strong>
</p>

Ahora nos vamos a la terminal de GitBash, entramos en el directorio en el que queramos guardar el repositorio (recuerda que para ir moviendote de carpeta se usa el comando `cd`. Si no sabéis moveros por la terminal para encontrar la carpeta en la que queréis descargar el repositorio, miraros este tutorial de 2min antes de hacer nada para que os quede más claro: https://www.youtube.com/watch?v=OEhp7WJJKzs&ab_channel=YoAndroide  
Una vez dentro, ponemos el siguiente comando:
```
git clone "aqui pegamos lo copiado, sin las comillas"
```
Ahora sí, ya tenemos el repositorio en local.

Para luego subir los progresos que vayamos haciendo, al final del módulo 2 comentaremos las formas de hacerlo.


## Instalación de Anaconda Navigator
Comenzaremos con la instalación de Anaconda Navigator, que es una interfaz gráfica de usuario (GUI) de escritorio incluida en la distribución de Anaconda que le permite iniciar aplicaciones y administrar fácilmente paquetes, entornos y canales de conda sin usar comandos de línea de comandos. Al final, lo que estaremos usando es Conda, un sistema de administración de paquetes y un sistema de administración de entornos de código abierto que se ejecuta en Windows, macOS, Linux y z/OS. Conda instala, ejecuta y actualiza rápidamente los paquetes y sus dependencias. Conda crea, guarda, carga y cambia fácilmente entre entornos en su computadora local. Fue creado para programas de Python, pero puede empaquetar y distribuir software para cualquier idioma. De esta forma nos será más fácil acceder e iniciarnos a crear código en Python.

<p align = "center">
<img src = "https://user-images.githubusercontent.com/88738496/186192941-340ac9e1-76df-434c-9fb3-53b0a043c9d3.png" width="600" height="400">
</p>
<p align = "center">
<strong>Fig.5 - Interfaz principal de Anaconda Navigator </strong>
</p>

Desde el link de debajo de la imagen, descargamos el archivo ejecutable de la última versión de Anaconda para Windows 8 o más en 64 bits. Ejecutamos el instalador e instalamos el programa. Esta versión lleva una versión la versión de Python 3.9. La instalación es muy sencilla, pero para más detalles se puede consultar en el user guide de la página oficial: https://docs.anaconda.com/anaconda/install/windows/ 

Una vez tenemos anaconda, debemos empezar con lo más básico. Abriremos la aplicación e instalaremos (si no se han instalado por defecto) las extensiones "Anaconda Prompt" y "Jupyter Lab". Una vez los hayamos instalado, abriremos la terminal de conda (el Anaconda Prompt) y llamaremos desde ahí a Jupyter Lab, ya que es la forma que, a mí personalmente, menos problemas me ha dado. Esto lo hacemos simplemente escribiendo en la terminal lo siguiente:
```
jupyter lab
```
Depende del disco desde el cual lo llamemos, tendremos unos archivos disponibles u otros (preguntar si no queda esto claro!)

## Configuración de enviroments (Entornos Virtuales)
Un entorno virtual es un espacio independiente a tu instalación local, con el objetivo de aislar los recursos y librerías. Gracias a este concepto podemos tener distintos entornos virtuales con diferentes versiones de Python o de una librería concreta. Las ventajas de usar los enviroments son:

- **Organización**: es conveniente tener controladas las librerías y las versiones con las que estamos trabajando para que no existan problemas de incompatibilidades.
- **Estabilidad**: es un hecho que las librerías que usamos cambian de versión muy a menudo, esto puede ocasionar que si queremos llevarnos nuestros programas a otra máquina nos encontremos con versiones de librerías que han cambiado y hacen que nuestros programas ya no funcionen.
- **Trabajar con diferentes versiones de Python**: existen muchas aplicaciones en la versión 2.7 de Python y algunas no cuentan con soporte para Python 3. También podemos encontrarnos que tenemos que trabajar con un servidor cuya versión de Python no es la misma que la que tenemos instalada en nuestro ordenador. Creando distintos entornos virtuales podremos cambiar de versión de Python en dos líneas de código.

Los enviroments, librerías y comandos generales se llaman normalmente desde la terminal de Anaconda, pero para hacer este trabajo algo más sencillo, vamos a hacer uso de una extensión recientemente actualizada para JupyterLab que permite hacer toda esta gestión desde la interfaz, y que además, integra Mamba, una solución para corregir los porblemas de dependencias entre versiones que siempre son tan oportunos. La forma de proceder va a ser la siguiente:

Nos iremos a la terminal de Anaconda e instalaremos node.js desde la terminal, con el siguiente comando:
```
conda install -c conda-forge nodejs
```
A continuación, hacemos un shutdown de JupyterLab, en la esquina superior izquierda: File-->Shut down. Cerramos la pestaña y volvemos a llamar a jupyter desde la terminal. Ahora, abrimos otra terminal de anaconda y escribimos el comando de instalación de la extensión de mamba gator:
```
conda install -c conda-forge mamba_gator
```
Una vez hecho, shut down y volvemos a abrir. Ahora ya tenmos uso del conda package manager, el cual lo podemos encontrar en Settings-->Conda Package Manager, que se ve de esta forma:

<p align = "center">
<img src = "https://user-images.githubusercontent.com/88738496/186355396-8160707c-f0a6-4140-9dd9-6b59dc8c6593.JPG">
</p>
<p align = "center">
<strong>Fig.6 - Interfaz principal de Conda Package Manager </strong>
</p>

Ahora instalaremos en el "base" `nb_conda_kernels` y `conda-envs`

# Las Librerías en Python
## ¿Qué son?
La librería es un conjunto de módulos y paquetes que se distribuyen junto con Python. Muchas de las operaciones más comúnes de la programación diaria ya están implementadas en ella, de modo que podemos concentrarnos en lo que realmente nos ocupa. Para entenderlo mejor, si yo instalo por ejemplo la librería `math`, que normalmente viene por defecto cuando istalamos conda, ya tengo funciones matemáticas para mi uso que no tengo que volver a programar, como r ejemplo una operación de elevara a la potencia, o el uso de logaritmos.

```
import math

# Raíz cuadrada.
print(math.sqrt(16))

4.0
```

De acuerdo, con los objetivos de las librerías de Python existen diferentes clasificaciones. 

Estos son algunos tipos de librerías de Python:

- **Deep learning**: Están enfocadas, de cara a la predicción de datos; a través del Big Data.
- **Machine learning**: Estas librerías son útiles para el machine learning, ya que mejoran el proceso de información y la resolución de problemas de clasificación y el análisis de regresión de datos.
- **Cálculo numérico**: Preparan los datos y ofrecen atributos importantes para su cálculo.
- **Visualización**: Sirven para entender y comprender los datos, de una forma más legible. 
- **Inteligencia Artificial explicable**: Buscan resultados óptimos en Inteligencia Artificial, llevando adelante diversas metodologías tecnológicas.
- **Procesamiento de lenguaje natural**: A partir del cálculo de frecuencias normalizadas, se construyen los modelos con datos de texto.

## ¿Cómo se instalan?
Como se ha comentado antes, la froma estándar de instalarlas será desde la terminal del intérprete de python que estemos utilizando. La librería se instala desde un gestor de paquetes de python que puede ser `pip`, `conda`, `conda-forge` y otros. Como nosotros estamos trabajando con conda,siempre intentaremos instalar nuestras librerías desde el paquete conda o conda-forge. La froma estándar es ir a la web de la documentación de la librería que queramos instalar y copiar el código de instalación desde el canal conda-forge a ser posible. Por ejemplo, si queremos instalar la librería `Pandas`, tendríamos que poner el buscador "conda install pandas", entramos en la web oficial del canal conda-forge (si existe), en este caso si: https://anaconda.org/conda-forge/pandas y copiar el código de instalación en nuestra terminal de anaconda, damos intro y así se instalaría la librería.

Esta forma de hacerlo es un poco mas tediosa que si lo hacemos desde el Conda Package Manager. En este caso, podemos elegir el enviorment en el que queremos instalar la librería y la versión de la librería que queremos instalar directamente desde la interfaz, lo que resulta notablemente más sencillo. En este caso, solo hay que buscar el nombre de la librería dentro del enviroment en la que la queramos instalar y clicar el icono del carrito azul para hacer efectivos los cambios.

Para este curso crearemos un enviroment para cada módulo de trabajo, en el que instalaremos las librerías necesarias para las operaciones que tengamos que realizar. Esta es la mejor forma de proceder a la hora de programar, ya que evitaremos el solape de versiones de librerías, que siempre llevan consigo problemas posteriores de dependencias entre las mismas.

## Principales librerías de gestión de datos

### 1. Pandas
<p align = "center">
<img src = "https://user-images.githubusercontent.com/88738496/186364746-b3e5b9ca-102a-4f9f-8986-2f7030822160.png">
</p>
<p align = "center">
<strong>https://pandas.pydata.org/ </strong>
</p>

Pandas es una librería de código abierto muy popular dentro de los desarrolladores de Python, y sobre todo dentro del ámbito de **Data Science y Machine Learning**, ya que ofrece unas estructuras muy poderosas y flexibles que facilitan la manipulación y tratamiento de datos. Pandas surgió como necesidad de aunar en una única librería todo lo necesario para que un analista de datos pudiese tener en una misma herramienta todas las funcionalidades que necesitaba en su día a día, como son: cargar datos, modelar, analizar, manipular y prepararlos. Permite, de forma fácil e intuitiva realizar operaciones capaces de gestionar y manipular cualquier tipo de información sin importar el formato, y sobre todo de una forma rápida y eficaz. Esto hace que Pandas se haya convertido en el mejor amigo de cualquier curioso por los datos.

En el módulo 2 veremos las posibilidades y funcionalidades de la librería de forma práctica.

### 2. Numpy 
<p align = "center">
<img src = "https://user-images.githubusercontent.com/88738496/186366451-a0c22b35-9609-4349-bb00-0f9745ff5e68.png">
</p>
<p align = "center">
<strong>https://numpy.org/</strong>
</p>

NumPy ( Numerical Python ) es una biblioteca Python de código abierto que se utiliza en casi todos los campos de la ciencia y la ingeniería. Es el estándar universal para trabajar con datos numéricos en Python y es el núcleo de los ecosistemas científicos de Python y PyData. Los usuarios de NumPy incluyen a todos, desde codificadores principiantes hasta investigadores experimentados que realizan investigación y desarrollo científico e industrial de vanguardia. La API de NumPy se usa ampliamente en Pandas, SciPy, Matplotlib, scikit-learn, scikit-image y la mayoría de los otros paquetes de ciencia de datos y Python científico. Incorpora una nueva clase de objetos llamados arrays que permite representar colecciones de datos de un mismo tipo en varias dimensiones, y funciones muy eficientes para su manipulación. La ventaja de Numpy frente a las listas predefinidas en Python es que el procesamiento de los arrays se realiza mucho más rápido (hasta 50 veces más) que las listas, lo cual la hace ideal para el procesamiento de vectores y matrices de grandes dimensiones.

<p align = "center">
<img src = "https://user-images.githubusercontent.com/88738496/186382892-1645ab88-4d34-4a15-9ec1-adf295fc95b2.png">
</p>
<p align = "center">
</p>

Básicamente es una gran librería, que se incluye en muchas otras, como pandas, que servirá como operador matemático, lógica, de formas, clasificación, selección, E/S., transformadas discretas de Fourier, álgebra lineal básica, operaciones estadísticas básicas, simulación aleatoria y mucho más para los procesos que queramos realizar con nuestros set de datos. En el módulo 2 veremos cómo se usa.

### 3. Matplotlib
<p align = "center">
<img src = "https://user-images.githubusercontent.com/88738496/186385478-028b233b-9d74-4907-a0f3-6b001935f5c7.png">
</p>
<p align = "center">
<strong>https://matplotlib.org/</strong>
</p>

Matplotlib es una biblioteca completa para crear visualizaciones estáticas, animadas e interactivas en Python. Matplotlib hace que las cosas fáciles sean fáciles y las difíciles sean posibles.
Permite crear y personalizar los tipos de gráficos más comunes, entre ellos:

- Diagramas de barras
- Histograma
- Diagramas de sectores
- Diagramas de caja y bigotes
- Diagramas de violín
- Diagramas de dispersión o puntos
- Diagramas de lineas
- Diagramas de areas
- Diagramas de contorno
- Mapas de color

<p align = "center">
<img src = "https://user-images.githubusercontent.com/88738496/186387350-5ccc8b20-8ed0-4d1c-8589-cf82cb8fc4e8.png">
</p>
<p align = "center">
<strong>Ejemplo de gráficos profesionales en Matplotlib</strong>
</p>



### 4. Seaborn
<p align = "center">
<img src = "https://user-images.githubusercontent.com/88738496/186387923-8043ff45-038c-4863-9670-943e277b18ce.png" width="400" height="200">
</p>
<p align = "center">
<strong>https://seaborn.pydata.org/</strong>
</p>

Seaborn es una biblioteca de visualización de datos de Python basada en matplotlib e integrada en estructuras de datos de Pandas. Proporciona una interfaz de alto nivel para dibujar gráficos estadísticos atractivos e informativos. Seaborn lo ayuda a explorar y comprender sus datos. Sus funciones de trazado operan en marcos de datos y matrices que contienen conjuntos de datos completos y realizan internamente el mapeo semántico y la agregación estadística necesarios para producir gráficos informativos. Su API declarativa orientada a conjuntos de datos le permite concentrarse en lo que significan los diferentes elementos de sus gráficos, en lugar de los detalles de cómo dibujarlos.

<p align = "center">
<img src = "https://user-images.githubusercontent.com/88738496/186389097-6bbcc755-48c6-45c0-b14a-e4bc270efedb.png">
</p>
<p align = "center">
<strong>Ejemplo de gráfico en Seaborn</strong>
</p>



