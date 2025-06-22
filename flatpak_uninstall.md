# DESINSTALAR Flatpak Y RELACIONADOS
```bash
flatpak list # Listar las aplicaciones Flatpak instaladas
flatpak uninstall nombre_paquete # Desisntalar paquete especifico
flatpak uninstall --all # Desinstalar todas las aplicaciones Flatpak
flatpak uninstall --unused # Eliminar dependencias y "tiempos de ejecución" no utilizados
flatpak remote-ls # Eliminar los repositorios Flatpak (opcional pero recomendado)
flatpak remote-delete flathub # Para eliminar Flathub (o cualquier otro repositorio que hayas añadido)
sudo apt purge flatpak # Desinstalar el paquete Flatpak de Ubuntu
#### Limpiar directorios residuales (opcional, proceder con precaución)
rm -rf ~/.local/share/flatpak/ # Para el directorio del usuario
sudo rm -rf /var/lib/flatpak/ # Para el directorio del sistema
```