# APT_APLICACIONES
### Genome - Software
```bash
sudo apt update
sudo apt install gnome-software # Instala un gestor de descargas de programas o aplicaciones
```
### Krita
```bash
sudo apt update
sudo apt install krita # Programa de manipulación de imágenes basado en píxeles (Arte digital (como Photoshop + pinceles))
```

### GNU Image Manipulation Program (Gimp)
```bash
sudo apt update
sudo apt install gimp # Editar imágenes y fotos (Retoque fotográfico y diseño gráfico, collages, posters, banners)
```

### Brave (Navegador web)
```bash
sudo apt update

sudo curl -fsSLo /usr/share/keyrings/brave-browser-archive-keyring.gpg https://brave-browser-apt-release.s3.brave.com/brave-browser-archive-keyring.gpg
echo "deb [signed-by=/usr/share/keyrings/brave-browser-archive-keyring.gpg] https://brave-browser-apt-release.s3.brave.com/ stable main"|sudo tee /etc/apt/sources.list.d/brave-browser-release.list

sudo apt update
sudo apt install brave-browser
```

### Inkscape
```bash
sudo apt update
sudo apt install inkscape # Diseñar logos, íconos y gráficos vectoriales (Diseño web y gráfico vectorial, logotipo, iconos)
```
# SNAP_APLICACIONES
### [Cameractrls](https://snapcraft.io/cameractrls)
```bash
sudo snap install cameractrls # configuración avanzada de cámara
```
### [Draw.io](https://snapcraft.io/drawio)
```bash
## herramienta de diagramación de producción más flexible y con mayor privacidad. Cree diagramas de flujo, diagramas de procesos,
sudo snap search drawio
```
# FLATHUB(FLATPAK)_APLICACIONES
### [Easy Effects](https://flathub.org/apps/com.github.wwmm.easyeffects) (Instalación)
> #### [Ecualización automática de auriculares](https://github.com/jaakkopasanen/AutoEq) (Recurso de ajuste de audio)
```bash
flatpak install flathub com.github.wwmm.easyeffects # Herramienta avanzada de manipulación de audio
flatpak run com.github.wwmm.easyeffects # Arrancar aplicacion
```
### [Upscaler](https://flathub.org/apps/io.gitlab.theevilskeleton.Upscaler)
### [Upscayl](https://flathub.org/apps/org.upscayl.Upscayl)
```bash
#### Mejorador de imágenes
##### Opcion 1 
flatpak install flathub io.gitlab.theevilskeleton.Upscaler
##### Opcion 2 
flatpak install flathub org.upscayl.Upscayl
```
### [Echo](https://flathub.org/apps/io.github.lo2dev.Echo) (Hacer ping a servidores)
> #### [Consultar Repositorio en caso de permisos](https://github.com/lo2dev/Echo)
```bash
flatpak install flathub io.github.lo2dev.Echo # Parámetros de ping avanzados como conteo de ping, tiempo de espera, etc.
```
### []()
