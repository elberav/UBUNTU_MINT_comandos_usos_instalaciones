## NodeJs + npm INSTALL UNINSTALL
```bash
sudo apt-get update

### Cambiar setup_20 por otra eversion de preferencia (ej: setup_22, setup_17)
### La version nodesource elejida remplaza el script anterior (si existe) en el repositorio de la maquina
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -

### Instalar nodejs + npm
sudo apt install -y nodejs

## Verifica
node -v
npm -v
----------------------------------------------------------------------------
### ***DESINSTALAR***
sudo apt purge nodejs # Elimina configuraciones
sudo apt autoremove nodejs # Elimina dependencias y paquete

### Quitar o eliminar el repositorio
ls /etc/apt/sources.list.d/ # Lista los repositorios
    > ej:`nodesource.list`
sudo rm /etc/apt/sources.list.d/nodesource.list # Elimina el script

### Elimina también su clave GPG (opcional)
#### Lista las claves
##### Opcion 1
sudo apt-key list

##### Opcion 2
ls /usr/share/keyrings/
    > ej:`nodesource.gpg`

sudo rm /usr/share/keyrings/nodesource.gpg # Elimina si existe y deseas
----------------------------------------------------------------------------
## Util para compartir proyecto desde VSCode
### EL proyecto dede estar ejecutandose (Live Server) en el puerto libre elegido (ej:5500)

### LocalTunel
sudo npm install -g localtunnel
lt --port 5500 # ejecuta localtunel con un puerto del proyecto
lt --port 5500 --subdomain miwebespecial # Cambiar subdominio (si está disponible)

### Para usar LocalTunnel inmediatamente sin instalación global, simplemente
npx localtunnel --port 5500 # Ejecucion temporal
----------------------------------------------------------------------------


```
> ## <a href="https://nodejs.org/es/download" title="clic aqui">INTALAR CON nvm - GESTIONAR VERSIONES</a>
```bash
## Desinstalar una versión específica de Node
nvm uninstall 24
nvm install 22 && nvm use 22 # Otra version personalizado

## Desinstalar nvm y todas las versiones de Node
rm -rf ~/.nvm

##Luego elimina nvm de tu shell (solo una vez):
nano ~/.bashrc

## Borra las líneas relacionadas con nvm y guarda.
##(O si usas zsh, edita ~/.zshrc).

## Cierra y abre la terminal y Verifica:
node -v
```
