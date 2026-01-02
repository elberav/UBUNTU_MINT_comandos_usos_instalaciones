# INTALACIÓN DE VLC (REPRDUCTOR MULTIMEDIA)
```bash
sudo apt update
sudo apt install ubuntu-restricted-extras # Durante el proceso de instalación, se solicitará la aceptación de los términos de la licencia de software de Microsoft, necesaria para la instalación de las fuentes TrueType.
sudo apt install vlc # Instalar a continuacion (junto con el anterioir refueza la relacion multimedia)
```
### Dependencias necesarias
```bash
## Edita
sudo nano /etc/apt/sources.list


## Reemplazar las líneas deb por estas en sources.list:
deb http://deb.debian.org/debian trixie main contrib non-free non-free-firmware
deb http://security.debian.org/debian-security trixie-security main contrib non-free non-free-firmware
deb http://deb.debian.org/debian trixie-updates main contrib non-free non-free-firmware

##### main → software libre básico
##### contrib → software libre que depende de cosas no libres
##### non-free → códecs propietarios (mp3, aac, h264, etc.)
```

### Actualiza e instala TODO lo multimedia
```bash
sudo apt update
sudo apt install -y ffmpeg audacity vlc libavcodec-extra gstreamer1.0-libav \
gstreamer1.0-plugins-{base,good,bad,ugly}

```
