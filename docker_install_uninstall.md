# INSTALAR Docker
```bash
#### 1. Actualizar paquetes existentes
sudo apt update
sudo apt upgrade -y

#### 2. Instala paquetes necesarios como la confianza en las conexiones segurtas (HTTPS)
sudo apt install -y ca-certificates curl gnupg lsb-release

#### 3. Descargar y añadir la clave GPG oficial de Docker
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

-------------------------------------------------------------------------------
#### 3.5. >>>ALTERNATIVO AL COMANDO ANTERIOR EN CASO DE ERROR<<<
curl -fsSL https://get.docker.com/ -o get-docker.sh # ALTERNATIVO (Este script contiene todas las instrucciones para detectar tu distribución y versión de sistema operativo, y luego instalar la última versión estable de Docker automáticamente)
sudo sh get-docker.sh # Ejecutar el script de instalación con privilegios de administrador. Ejecuta ese script descargado con permisos de superusuario (sudo), lo que agrega el repositorio de Docker. Importa la clave GPG. Instala docker-ce, docker-ce-cli y containerd.io. Habilita y arranca el servicio de Docker.
-------------------------------------------------------------------------------

#### 4. Le dice a tu sistema dónde encontrar los paquetes de Docker. Añade el repositorio oficial de Docker
echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] \
  https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

#### 5. Actualiza e instala Docker Engine y sus componentes
sudo apt update
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
sudo apt install docker-compose

#### 6. Ver la version del docker
sudo docker --version
#### 7. `usermod -aG docker $USER` Agrega tu usuario al grupo docker para Docker sin necesidad de usar `sudo`
#### 8. `newgrp docker` hace que la terminal actual reconozca inmediatamente que tu usuario pertenece al nuevo grupo docker
sudo usermod -aG docker $USER
newgrp docker
docker run hello-world # PRUEBA PARA VER SI DOCKER RESPONDE


#### >>>>>>>DESINSTALAR DOCKER Y DEPENDENCIAS<<<<<<<
# Paso 1: Desinstalar los paquetes de Docker
sudo apt purge -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin docker-ce-rootless-extras
# Paso 2: Desinstalar paquetes de versiones antiguas (por si acaso)
sudo apt purge -y docker docker-engine docker.io docker-doc docker-compose
# Paso 3: Eliminar los datos de Docker
sudo rm -rf /var/lib/docker
sudo rm -rf /var/lib/containerd
# Paso 4: Limpiar las configuraciones del gestor de paquetes (APT)
sudo rm /etc/apt/sources.list.d/docker.list
sudo rm -rf /etc/apt/keyrings/docker.gpg
# Paso 5: Limpiar la caché de paquetes
sudo apt clean
# Paso 6: Verificar que se ha desinstalado
which docker
```
