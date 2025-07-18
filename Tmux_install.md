# Tmux INSTALL
```bash
sudo apt update
sudo apt install tmux # Multiplexor de terminales. Poderoso enfocado en seguridad y velocidad.
----------------------------------------------------------------------
##### Atajos dentro de Tmux
Ctrl + b c       # Crear nueva ventana en tmux
Ctrl + b %       # Dividir el panel actual verticalmente (lado a lado)
Ctrl + b "       # Dividir el panel actual horizontalmente (uno sobre otro)

Ctrl + b ↑       # Moverse al panel de arriba
Ctrl + b ↓       # Moverse al panel de abajo
Ctrl + b ←       # Moverse al panel de la izquierda
Ctrl + b →       # Moverse al panel de la derecha

Ctrl + b 1       # Cambia a la ventana número 1
Ctrl + b 2       # Cambia a la ventana número 2
Ctrl + b 3       # Cambia a la ventana número 3
Ctrl + b 4       # Cambia a la ventana número 4

Ctrl + b p   # Ir a la ventana anterior

----------------------------------------------------------------------
Ctrl + b Ctrl + ↑    # Aumentar el tamaño del panel hacia arriba
Ctrl + b Ctrl + ↓    # Aumentar el tamaño del panel hacia abajo
Ctrl + b Ctrl + ←    # Aumentar el tamaño del panel hacia la izquierda
Ctrl + b Ctrl + →    # Aumentar el tamaño del panel hacia la derecha
//////////////////////////////////
Ctrl + b Alt + ↑     # Aumentar tamaño arriba (mas rapido)
Ctrl + b Alt + ↓     # Aumentar tamaño abajo (mas rapido)
Ctrl + b Alt + ←     # Aumentar tamaño izquierda (mas rapido)
Ctrl + b Alt + →     # Aumentar tamaño derecha (mas rapido)
----------------------------------------------------------------------
##### Fuera de Tmux
tmux ls # Lista todas las sesiones de tmux actualmente activas

tmux attach       # Conecta la ultima sesion activa
tmux attach -t nombre_de_la_sesion (por default las sesiones son 0; 1; 2; 3)  # Te conecta a la sesión llamada "nombre_de_la_sesion".
tmux a -t 1       # (Forma abreviada del comando anterior).
```
