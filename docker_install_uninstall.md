# INSTALAR Docker
```bash
#### 1. Actualizar paquetes existentes
sudo apt update
sudo apt install -y ca-certificates curl

#### 2. Crear directorio de claves y añadir clave oficial Docker
sudo install -m 0755 -d /etc/apt/keyrings

sudo curl -fsSL https://download.docker.com/linux/debian/gpg \
-o /etc/apt/keyrings/docker.asc # Debian

sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg \
-o /etc/apt/keyrings/docker.asc # Ubuntu

sudo chmod a+r /etc/apt/keyrings/docker.asc

#### 3. Añadir repositorio oficial Docker (formato moderno)
sudo tee /etc/apt/sources.list.d/docker.sources <<EOF
Types: deb
URIs: https://download.docker.com/linux/debian
Suites: $(. /etc/os-release && echo "$VERSION_CODENAME")
Components: stable
Signed-By: /etc/apt/keyrings/docker.asc
EOF

#### 4. Actualizar índices
sudo apt update

#### 5. Instalar Docker + Compose (oficiales)
sudo apt install -y \
docker-ce docker-ce-cli containerd.io \
docker-buildx-plugin docker-compose-plugin

#### 6. Iniciar y habilitar Docker
sudo systemctl enable docker
sudo systemctl start docker
### Verificar:
sudo systemctl status docker

#### 7. Usar Docker SIN sudo (correcto y permanente)
sudo usermod -aG docker $USER
newgrp docker
docker ps
docker run hello-world

#### 8. `newgrp docker` hace que la terminal actual reconozca inmediatamente que tu usuario pertenece al nuevo grupo docker
sudo usermod -aG docker $USER
newgrp docker
docker run hello-world # PRUEBA PARA VER SI DOCKER RESPONDE

#### 8. Ver versiones
docker --version
docker buildx version
docker compose version
___________________________________________________

Detén y elimina los contenedores actuales:**
    ```sh
    docker compose down
    ```

2.  **Vuelve a construir y levantar los servicios en segundo plano:**
    ```sh
    docker compose up -d

Este comando levanta (inicia y ejecuta) todos los servicios definidos en tu archivo
docker-compose.yml. Cada servicio se convierte en un contenedor en ejecución (por
ejemplo: un contenedor para Hadoop, otro para Spark, otro para Flink, etc.).
docker compose up -d

docker ps

Ver también los contenedores detenidos:
docker ps -a

Ver más detalles (en formato extendido):
docker ps --format "table {{.ID}}\t{{.Image}}\t{{.Status}}\t{{.Ports}}\t{{.Names}}"

Paso 1: Parar y eliminar los contenedores actuales
docker stop $(docker ps -aq)

# Limpieza profunda por si acaso
docker system prune -f 
docker rm $(docker ps -aq)
docker image rm -f $(docker image ls -q)
_______________________________________________


#### >>>>>>>DESINSTALAR DOCKER Y DEPENDENCIAS<<<<<<<
sudo apt purge -y \
docker.io docker-compose docker-doc podman-docker \
containerd runc docker-buildx

sudo rm -rf /var/lib/docker /var/lib/containerd
sudo rm -rf /etc/docker ~/.docker
sudo rm -f /etc/apt/keyrings/docker.asc /etc/apt/keyrings/docker.gpg
sudo rm -f /etc/apt/sources.list.d/docker.list /etc/apt/sources.list.d/docker.sources

sudo apt autoremove -y
sudo apt autoclean

# Verificar que se ha desinstalado
which docker
```

### I. Optimizar Docker para tu PC
```bash
Creamos configuración recomendada.
sudo mkdir -p /etc/docker
sudo nano /etc/docker/daemon.json
#### Pega el siguiente `json`
```

```json
{
  "log-driver": "json-file",
  "log-opts": {
    "max-size": "10m",
    "max-file": "3"
  },
  "storage-driver": "overlay2",
  "exec-opts": ["native.cgroupdriver=systemd"]
}
```
```bash
#### Guardar y reiniciar Docker:
sudo systemctl restart docker

#### Evita que los logs llenen el disco
#### Mejora estabilidad
#### Es ideal para 8 GB RAM
```

### II. Docker Compose base (plantilla limpia)
```bash
#### Crea una carpeta de prueba
mkdir docker-test
cd docker-test

#### Crea el archivo
nano docker-compose.yml

### Contenido recomendado en el siuiente `YAML`
```
```yaml

services:
  app:
    image: nginx:alpine
    container_name: nginx_test
    ports:
      - "8080:80"
    restart: unless-stopped
```
```bash
#### Levantarlo
docker compose up -d

#### Probar
curl http://localhost:8080

#### O abre en navegador
http://localhost:8080
```
