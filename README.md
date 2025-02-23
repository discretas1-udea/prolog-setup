# Básicos de Prolog
[![Prolog](https://img.shields.io/badge/Lenguajes-Prolog-red)](https://www.swi-prolog.org/)
[![date](https://img.shields.io/badge/Semestre-2025-blue)]()
[![date](https://img.shields.io/badge/Universidad-UdeA-green)]()
[![date](https://img.shields.io/badge/Carrera-Ingenier%C3%ADa%20de%20sistemas-gray)]()
[![date](https://img.shields.io/badge/Asignatura-Matem%C3%A1ticas%20discretas%20I-purple)]()

### Algunos links de interés
1. [Documentación oficial de Prolog](https://www.swi-prolog.org/)
2. [Tutorial de Prolog de Swish](https://swish.swi-prolog.org/p/Tutorial%20de%20prolog.swinb) (Recomendado)

> [!TIP]
> El tutorial de Prolog de SWISH es sencillo y está muy bien documentado para entender como escribir cláusulas en Prolog, archivos .pl para las bases de conocimiento y también la relación entre estas y proposiciones simples. Se recomienda encarecidamente seguirlo con atención. 

## Instalación de PROLOG

> [!IMPORTANT]
> Cada persona escoge la opción que le quede más sencilla de instalar. 

### Instalación en Windows
La instalación de Prolog en Windows se realiza mediante un archivo .exe
Solamente se ejecuta dicho archivo, se escoje la ruta donde se desee instalar y se finaliza. 



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
