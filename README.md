# Básicos de Prolog
[![Prolog](https://img.shields.io/badge/Lenguajes-Prolog-red)](https://www.swi-prolog.org/)
[![date](https://img.shields.io/badge/Semestre-2025-blue)]()
[![date](https://img.shields.io/badge/Universidad-UdeA-green)]()
[![date](https://img.shields.io/badge/Carrera-Ingenier%C3%ADa%20de%20sistemas-black)]()
[![date](https://img.shields.io/badge/Asignatura-Matem%C3%A1ticas%20discretas%20I-purple)]()

### Algunos links de interés
1. [Documentación oficial de Prolog](https://www.swi-prolog.org/)
2. [Tutorial de Prolog de Swish](https://swish.swi-prolog.org/p/Tutorial%20de%20prolog.swinb) (Recomendado)

> [!TIP]
> El tutorial de Prolog de SWISH es sencillo y está muy bien documentado para entender como escribir cláusulas en Prolog, archivos .pl para las bases de conocimiento y también la relación entre estas y proposiciones simples. Se recomienda encarecidamente seguirlo con atención. 

# Setup

## Instalación de PROLOG

> [!IMPORTANT]
> Cada persona escoge la opción que le quede más sencilla de instalar. 

### Instalación en Windows
La instalación de Prolog en Windows se realiza mediante un archivo .exe
Solamente se ejecuta dicho archivo, se escoje la ruta donde se desee instalar y se finaliza. 

<details><summary><b>Instrucciones para la instalación en Windows</b></summary>

1. Se descarga el .exe desde la [página oficial](https://www.swi-prolog.org/download/stable).

2. Se ejecuta el archivo .exe
![Screenshot executing .exe file](https://github.com/discretas1-udea/prolog-basics/blob/main/assets/windows-installation/01.png)

3. Se da clic en el botón siguiente para iniciar la instalación
![Screenshot 2](https://github.com/discretas1-udea/prolog-basics/blob/main/assets/windows-installation/02.png)

4. Se debe aceptar el acuerdo de licencia para poder instalar
![Screenshot 3](https://github.com/discretas1-udea/prolog-basics/blob/main/assets/windows-installation/03.png)

5. Se agrega al PATH del sistema ya sea para el usuario actual o para todos los usuarios según se desee 
![Screenshot 4](https://github.com/discretas1-udea/prolog-basics/blob/main/assets/windows-installation/04.png)

6. Se escoge la carpeta en la cual se desea instalar el programa y se da clic en siguiente
![Screenshot 5](https://github.com/discretas1-udea/prolog-basics/blob/main/assets/windows-installation/05.png)

7. Se deja la carpeta del menú de inicio por defecto y se da clic en siguiente
![Screenshot 6](https://github.com/discretas1-udea/prolog-basics/blob/main/assets/windows-installation/06.png)

8. Se seleccionan todos los componentes que nos permite el instalador y se da clic en instalar
![Screenshot 7](https://github.com/discretas1-udea/prolog-basics/blob/main/assets/windows-installation/07.png)

9. Una vez finalice de instalar, buscamos SWI-Prolog en el buscador de Windows y ya podemos observar que se encuentra instalado
![Screenshot 8](https://github.com/discretas1-udea/prolog-basics/blob/main/assets/windows-installation/08.png)


</details>


---

### Instalación en Linux
Para instalar Prolog en Linux, se debe tener clara cual es la distribución en específico y seguir el tutorial de la documentación oficial: [Clic acá](https://www.swi-prolog.org/build/unix.html) para ver las instrucciones.

<details><summary><b>Instrucciones para distribuciones basadas en Debian</b></summary>

1. Actualiza la información de los paquetes e instala las actualizaciones disponibles. 
    ```sh
    sudo apt update && sudo apt upgrade -y
    ```

2. Instala el paquete 'swi-prolog' desde los repositorios oficiales.
    ```sh
    sudo apt install swi-prolog -y
    ```

3. `(OPCIONAL)` Verifica la instalación de Prolog.
    ```sh
    dpkg -l | grep swi-prolog
    swipl --version
    ```

4. Abre Prolog desde la terminal.
    ```sh
    swipl
    ```

5. Si deseas salir del programa y quedar nuevamente en la terminal puedes apretar la combinación de teclas `Ctrl + c` y luego presiona la tecla `e`.

</details>

---

### Instalación y uso en un notebook de Google Colab
> [!WARNING]
> Usar Prolog en un notebook de Colab es más cómodo si se quiere trabajar con él sin la necesidad de instalarlo localmente. Sin embargo, al estar en un entorno de ejecución de Python, estamos sujetos a trabajar con Prolog a través de la librería [PySwip](https://pyswip.readthedocs.io/en/latest/get_started.html) y no directamente. (Como podría serlo en un entorno local). Por lo tanto, tendremos que usar Python para ejecutar Prolog, lo cual, puede ser un poco tedioso si no se tienen conocimientos previos de programación en Python. 

<details><summary><b>Comandos para la instalación en el Notebook</b></summary>

1. Instale SWI-PROLOG en el entorno virtual.
    ```sh
    !apt-get install swi-prolog -y
    ```

2. Instale con pip la librería PySwip en el entorno virtual.
    ```sh
    !pip install -U pyswip
    ```

3. Importe el módulo necesario de la librería PySwip para usar Prolog en el Notebook
    ```sh
    from pyswip import Prolog
    ```
</details>

## Guardado y consulta de una base de conocimiento
Las bases de conocimiento son archivos en los cuales registraremos los hechos y reglas con los que Prolog trabajará. Estos hechos y reglas se guardan en archivos con extensión `.pl` 

<details><summary><b>Bases de conocimiento en Windows</b></summary>
En Windows se puede usar el menú que nos proporciona la terminal de SWI-PROLOG para crear las bases de conocimiento. 

1. En el menú de la terminal de Prolog, vamos a la pestaña `File` y damos clic en `New`
![Screenshots 1](https://github.com/discretas1-udea/prolog-basics/tree/main/assets/windows-consult/01.png)

2. Se nos abre una carpeta en la cual vamos a escribir el nombre deseado para nuestra base de conocimiento con extensión `.pl` y damos clic en Guardar
![Screenshot 2](https://github.com/discretas1-udea/prolog-basics/tree/main/assets/windows-consult/02.png)

3. Podemos observar que se abre una pestaña con el nombre que recién le dimos a la base de datos. Esta pestaña es un editor de texto, que podremos usar para crear nuestras bases de conocimiento
![Screenshot 3](https://github.com/discretas1-udea/prolog-basics/tree/main/assets/windows-consult/03.png)

4. En la pestaña donde tenemos abierto Prolog vamos a escribir lo siguiente:
    ```prolog
    consult('baseconocimiento.pl') .
    ```
    
    Asegúrate que escribes el nombre del archivo que creaste.
    Si el archivo está creado correctamente entonces la terminal arrojará como salida `true`. Si el archivo no existe, arrojará un error. 

![Screenshot 4](https://github.com/discretas1-udea/prolog-basics/tree/main/assets/windows-consult/04.png)

5. Si el archivo `.pl` se encuentra en otra carpeta diferente, desde el menú también podemos abrirla. Dando clic en la pestaña File y luego en Consult. Se selecciona entonces el archivo .pl que se quiere consultar. 

6. En caso de querer editar una base de conocimiento, desde el menú en la pestaña File y la opción Edit, seleccionando la base que queremos cambiar, podremos editarla. 


