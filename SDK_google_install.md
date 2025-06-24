# INSTALAR SDK Google Cloud
```bash
#### 1. Asegúrate de tener las dependencias necesarias
sudo apt-get update
sudo apt-get install -y apt-transport-https ca-certificates gnupg

#### 2. Importa la clave pública de Google Cloud:
#### Esto es un paso de seguridad para asegurar que los paquetes que descargas son auténticos y no han sido modificados.
echo "deb [signed-by=/usr/share/keyrings/cloud.google.gpg] https://packages.cloud.google.com/apt cloud-sdk main" | sudo tee -a /etc/apt/sources.list.d/google-cloud-sdk.list
curl https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo gpg --dearmor -o /usr/share/keyrings/cloud.google.gpg

#### 3. Actualiza la lista de paquetes e instala el SDK:
#### Ahora que tu sistema conoce el repositorio de Google, actualiza la lista de paquetes y finalmente instala la CLI.
sudo apt-get update && sudo apt-get install -y google-cloud-cli

#### 4. Inicializa el SDK:
#### Una vez instalado, ejecuta gcloud init para configurar tu cuenta, seleccionar un proyecto por defecto y una región/zona.
gcloud init
-----------------------------------------------------------------------------
#### 2.5. (SUPOSICION) Elimina el archivo de clave incorrecto si dice que `ya existe` y luego volver a ejecutar el paso 2. 
#### Si no sale ese mensaje, seguir al paso 3.
sudo rm /usr/share/keyrings/cloud.google.gpg
```
* ##### Al iniciar el SDK, inicia sesión con una cuata donde está el proyecto a usar en GCP.
* ##### Al llegar al paso de configurar el región pones (n) cuando te lo pida. (El proyecto tienes su propia región configurada)


