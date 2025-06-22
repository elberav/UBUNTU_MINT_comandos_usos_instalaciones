# DESINTALAR IMAGE MAGICK
#### (OPCIONAL SI APRECE LA APLICACION SIN QUE LO INSTALES. NO AFECTA AL SISTEMA.)
#### Desintalar imagemagick
```bash
sudo apt autoremove imagemagick
```
Ó
```bash
sudo apt remove imagemagick
sudo apt autoremove # remueve dependencias
```
#### En caso diga que no se encuentra programa, listar paquetes relacionados con imagemagick
```bash
apt list --installed | grep imagemagick
```
#### Ej: de paquetes que tienen que aparecer
```bash
imagemagick-6.q16
imagemagick-common
```
#### Desisntalar paquetes encontrados
```bash
sudo apt autoremove imagemagick-6.q16 imagemagick-common  # Reemplaza con los paquetes que encontraste
```