# HABILITAR / DETECTAR MICROFONO Linux
#### Abrir el archivo o terminal de configuración base del sistema de sonido
```bash
sudo nano /etc/modprobe.d/alsa-base.conf
```
#### Añadir al final del archivo o terminal
```bash
options snd-hda-intel model=dell-headset-multi
```
* NOTA: En la terminal después de añadir el comando, presionar `Control + O`, presiona ENTER y al final `Control + X`, reiniciar PC o cerrar sesion para que se apliquen los cambios.</h5>
#### Luego de que se apliquen los cambios, escribir en la terminal:
```bash
alsamixer 
```
##### (aparecerá unas graficas(presionar F6(seleccionar default:0) y luego F4 para configurar la entrada de volumen y distorción del microfono))