# APT_APLICACIONES
### Genome - Software (Debian, Ubuntu)
```bash
sudo apt update
sudo apt install gnome-software # Instala un gestor de descargas de programas o aplicaciones
```
### Krita (Debian, Ubuntu)
```bash
sudo apt update
sudo apt install krita # Programa de manipulación de imágenes basado en píxeles (Arte digital (como Photoshop + pinceles))
```

### GNU Image Manipulation Program (Gimp) (Debian, Ubuntu)
```bash
sudo apt update
sudo apt install gimp # Editar imágenes y fotos (Retoque fotográfico y diseño gráfico, collages, posters, banners)
```

### Brave (Navegador web) (Debian, Ubuntu)
```bash
sudo apt update

sudo curl -fsSLo /usr/share/keyrings/brave-browser-archive-keyring.gpg https://brave-browser-apt-release.s3.brave.com/brave-browser-archive-keyring.gpg
echo "deb [signed-by=/usr/share/keyrings/brave-browser-archive-keyring.gpg] https://brave-browser-apt-release.s3.brave.com/ stable main"|sudo tee /etc/apt/sources.list.d/brave-browser-release.list

sudo apt update
sudo apt install brave-browser
```
Note that Debian focuses more on stability rather than newest features. Therefore packages will typically contain some older version, compared to the latest release.
### [DB Browser for SQLite](https://sqlitebrowser.org/dl/) (Debian, Ubuntu, ...)

### Inkscape
```bash
sudo apt update
sudo apt install inkscape # Diseñar logos, íconos y gráficos vectoriales (Diseño web y gráfico vectorial, logotipo, iconos)
```
# FLATHUB(FLATPAK)_APLICACIONES
### [Easy Effects](https://flathub.org/apps/com.github.wwmm.easyeffects) (Debian, Ubuntu)
> #### [Ecualización automática de auriculares](https://github.com/jaakkopasanen/AutoEq) (Recurso de ajuste de audio)
```bash
flatpak install flathub com.github.wwmm.easyeffects # Herramienta avanzada de manipulación de audio
flatpak run com.github.wwmm.easyeffects # Arrancar aplicacion
```
### [Draw.io](https://flathub.org/en/apps/com.jgraph.drawio.desktop) (Debian, Ubuntu)
```bash
flatpak install flathub com.jgraph.drawio.desktop

### Arranque
flatpak run com.jgraph.drawio.desktop
```

### [Upscaler](https://flathub.org/apps/io.gitlab.theevilskeleton.Upscaler) (Debian, Ubuntu)
### [Upscayl](https://flathub.org/apps/org.upscayl.Upscayl) (Debian, Ubuntu)
```bash
#### Mejorador de imágenes

##### Opcion 1 
flatpak install flathub io.gitlab.theevilskeleton.Upscaler
##### Opcion 2 
flatpak install flathub org.upscayl.Upscayl
```
### [Echo](https://flathub.org/apps/io.github.lo2dev.Echo) (Hacer ping a servidores) (Debian, Ubuntu)
> #### [Consultar Repositorio en caso de permisos](https://github.com/lo2dev/Echo)
```bash
flatpak install flathub io.github.lo2dev.Echo # Parámetros de ping avanzados como conteo de ping, tiempo de espera, etc.
```
### []()

# SNAP_APLICACIONES
### [Cameractrls](https://snapcraft.io/cameractrls) (Debian, Ubuntu)
```bash
sudo snap install cameractrls # configuración avanzada de cámara
```
