# DESINSTALAR PAQUETES O INSTALACIONES
```bash
sudo apt purge nombre_del_paquete # Para eliminar el paquete y sus archivos de configuración. Es MAS AGRESIVO que el metodo (comando)siguiente
sudo apt autoremove nombre_del_paquete # Más adecuado porque hace dos procesos automaticos y es más seguro
sudo apt clean # Para limpiar la caché de paquetes descargados:

#### Si lo instalaste como un "Snap"
snap list # Para listar tus Snaps instalados y encontrar el nombre exacto
sudo snap remove --purge nombre_del_snap # Para una eliminación más completa (incluyendo datos de usuario y configuración)
##### NOTA: Ten en cuenta que snap remove --purge es una eliminación más agresiva y no se puede deshacer fácilmente.
sudo snap remove nombre_del_snap # Para desinstalar un Snap
```