# INSTALACIÓN DE Python, MANEJADOR DE VERSIONES DE Python (Pyenv) Y ENTORNO VIRTUALES
```bash
#### 1. verifica la versión de python
python3 --version 
#### 2. Instala python si no está en el sistema
sudo apt install python3 
#### 3. Instala pip si no viene con la instalación
sudo apt install python3-pip 

#### Para que pyenv pueda compilar las diferentes versiones de Python desde la fuente, necesitas instalar algunas dependencias del sistema:
##### Paso 1.
sudo apt update
sudo apt upgrade
##### Paso 2.
sudo apt install -y make build-essential libssl-dev zlib1g-dev \
libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm \
libncurses5-dev libncursesw5-dev xz-utils tk-dev libffi-dev liblzma-dev python3-openssl git

#### Paso 3. Instalación recomendada de pyenv
sudo apt install curl
curl https://pyenv.run | bash

------------------------------------------------------------------
#### Paso 3.5. Si en caso hay error de que ya existe el archivo, eliminar y volver a instalar
rm -rf ~/.pyenv
curl https://pyenv.run | bash
------------------------------------------------------------------

#### Paso 4. Después de la instalación, el script te dará instrucciones sobre cómo agregar pyenv a tu PATH y cómo inicializarlo en tu shell (bash, zsh, etc.). Generalmente, implica añadir estas líneas a tu archivo ~/.bashrc (o ~/.zshrc si usas Zsh):
nano ~/.bashrc # Primero habrir el archivos
#### Paso 5. Añadir al final del archivo (Ej: de instrucciones a añadir, pero puede variar segun lo que te pida en la terminal despues de instalar https://pyenv.run):
export PYENV_ROOT="$HOME/.pyenv"
[[ -d $PYENV_ROOT/bin ]] && export PATH="$PYENV_ROOT/bin:$PATH"
eval "$(pyenv init - bash)"
eval "$(pyenv virtualenv-init -)"

#### Paso 6-Final. Importante para que se peuda usar `pyenv`
source ~/.bashrc # Reinicia la terminal para que se apliquen los cambios.

#### Instalar otras versiones de Python
pyenv install --list # Listar las versiones de Python disponibles para instalar.
pyenv install --list | grep " 3\." # Esto mostrará una lista muy larga. Puedes filtrar para ver las versiones de Python 3, por ejemplo.
pyenv install 3.12.10 # Ejemplo de instalacion de una version
pyenv versions # Lista versiones instaladas de Python y ENTORNOS Virtuales

#### Cambiar de version de Python
pyenv global 3.12.10 # Cambia la version de python de froma global
pyenv global system # Vuelve a la version de sistema
pyenv local 3.12.10 # Cambia la version solo en la ruta o directorio actual (en donde este posicionado, recomnedado hacerlo en la raiz de un proyecto)
pyenv shell 3.10.12 # Activa una sesion temporal de python solo en la terminal en donde se ejecute
pyenv prefix mi_proyecto_venv # Dice la ruta exacta del entorno virtual donde fue creado

#### Crear entornos virtuales y Activarlos
pyenv virtualenv 3.10.12 mi_proyecto_venv # ejecutar esto con la version preferida en la raiz del proyecto que tengas
pyenv uninstall mi_proyecto_venv # Elimina el entorno creado
pyenv activate mi_proyecto_venv # Activas el entorno virtual de forma temporal, solo para la terminal abierta. Si cierras la terminal o abres una nueva, el entorno vuelve al predeterminado (por ejemplo, system o el que diga `.python-version` en tu directorio)

pyenv deactivate # Volver al sistema o desactivarlo para usar el predeterminado que estaba anteriormente
pyenv local mi_proyecto_venv # Activa el entorno virtual de forma permanentente creando un `.python-version` en el proyecto raiz, no s epuede deshabilitar (recomendado de forma local). SE PUEDE USAR el mismo entorno en cualquier ruta o proyecto


#### Muestra si pyenv esta activo o usado
which python 
> /home/tu_usuario/.pyenv/version/python
#### Si estas en un entorno virtual, te muestra el nombre del entorno
> /home/ubnt/.pyenv/versions/entorno_virtual/bin/python

#### Usar despues de activar el entorno para comprobar si está creado y activo el entorno virtual
#### Sirve tambien para ver la version de python con pyenv que está usando
pyenv which python
> /home/ubnt/.pyenv/versions/entorno_virtual/bin/python


### Asegúrate de que estás usando la versión de Python deseada (por ejemplo, con pyenv local 3.10.12):
#### Esta es la forma estándar de Python y funciona si no estás usando el plugin pyenv-virtualenv o si prefieres un control más granular.
python -m venv .venv
#### Activar el entorno virtual
source .venv/bin/activate # Linux
.venv\Scripts\Activate.ps1 # Windows shell
.venv\Scripts\activate # Windows cmd

deactivate # Desactiva el entorno virtual

pyenv shell --unset # Vuelve al comportamiento normal de `pyenv`, usando la versión definida por `pyenv local` (si estás en una carpeta con ``.python-version``) o `pyenv global` (si no hay una versión local):

#### Instalación de paquetes (recomendado instalar en entorno viruales activados en el proyecto)
#### Siempre buena idea actualizar pip
pip install --upgrade pip
pip install requests
pip install pandas numpy matplotlib

#### Desinstalacion de paquetes
pip uninstall Flask # Si esta en un entorno virtual
sudo pip uninstall Flask # Si fue instalado a nivel global del sistema
```
