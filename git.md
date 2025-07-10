# INSTALAR Git
```bash
sudo apt update
sudo apt install git
```
#### AUTENTICACIÓN DEL GIT AL GitHub
#### Configurar credenciales para hacer operaciones locales y remotas(nube)
##### Si las credenciales tiene espacios debes usar `" "`
```bash
#### Afecta al repositorio actual (ruta actual)
git config user.name "TuNombre De Usuario"
git config user.email "tuemail@ejemplo.com"

#### Afecta a todos los repositorios
git config --global user.name TuNombreDeUsuario
git config --global user.email tuemail@ejemplo.com

#### (RECOMENDACION) Afecta al repositorio actual
git config user.name TuNombreDeUsuario
git config user.email tuemail@ejemplo.com

#### Dependiendo en el modo en el que lo configuraste podrás verificar las credenciales
git config --global --list
git config --list
```
#### GitHub ya no permite autenticación con usuario y contraseña tradicionales al hacer `git push` (y otras operaciones que requieren autenticación). Como parte de sus medidas de seguridad, solo se puede autenticar usando tokens de acceso personal (PAT - Personal Access Token), llaves SSH u OAuth. En tu cuenta de GitHub debes hacer clic en tu perfil de usuario y se abrirá un menú de opciones. Entra en la siguiente ruta:
>`Settings`/`<> Developer Settings`/`Personal access tokens`/`Tokens(classic)`  Luego elije la opción `Generate new token(classic)`
##### Te llevará a un espacio de opciones. Solo marca las siguientes:
- [x] `repo` – Acceso total a repos privados y públicos
    - [x] `repo:status` – Access commit status
    - [x] `repo_deployment` – Access deployment status
    - [x] `public_repo` – Access public repositories
    - [x] `repo:invite` – Access repository invitations
    - [x] `security_events` – Read and write security events
- [ ] `admin:org` – Full control of orgs and teams, read and write org projects
    - [ ] `write:org` – Read and write org and team membership, read and write org projects
    - [x] `read:org` – Read org and team membership, read org projects
    - [ ] `manage_runners:org` – Manage org runners and runner groups
##### Por ultimo presiona el botón `Generate token`, copias el token que se generó (ej: `ghp_skJASNu75sOPJKg6stgsbu`) porque no podrás verlo si actualizas o cierras la pestaña del navegador. Ese token es el password para hacer las operaciones con `git` hacia el GitHub.
### Comandos Git
```bash
git init # Inicia un repositorio local
git branch # te dice en que rama estas
git branch -m nombre_de_la_rama # Cambia la rama por la del repositorio remoto o dejalo por default. Default (main, master).
---------------------------------------------------------------------
git remote add origin https://github.com/nombre_usuario/nombre_proyecto.git # Conectar repositorio remoto con el local
git add . # Agrega todos los archivos modificados y añadidos en un repositorio local (área de staging), preparándolos para el próximo commit.
git commit -m "tu_comentario" # Comenta los cambios de los archivos editados y añadidos.
git status # Muestra el estado actual de tu repositorio Git.
git status -s `ó` git status --short # Muestra un resumen conciso de los cambios, usando códigos de una o dos letras para indicar el estado de cada archivo (ej: ?? para no rastreado,  M para modificado, A  para agregado).
git push -u origin main # Sube tus cambios locales del branch main al repositorio remoto. Cambiar nombre de rama si quieres crear uno nuevo en GitHub y subir cambios 
git push origin main # Para las subidas siguientes al repositorio remoto, una vez que ya estableciste la conexión inicial con git push `-u origin main`
---------------------------------------------------------------------

git push --force-with-lease origin main `ó` --force-with-lease -u origin main  # Verifica si hubo cambios en el remoto antes de forzar le push y sobrescribirlo evitando el cambio de alguien.
git push --force origin main `ó` --force -u origin main  # Fuerza el push, sobrescribiendo el historial y archivos remotos. Puede borrar cambios de otros si no se tiene cuidado.
git remote -v # Muestra las URLs de los repositorios remotos configurados. Útil para verificar a dónde se están enviando o desde dónde se están trayendo los cambios.
---------------------------------------------------------------------
git pull origin main # Trae los cambios editados o añadidos, lo hace igual con nuevos archivos añadidos
git pull --rebase origin main
# Descarga los cambios de origin/main y reordena tus commits locales encima de ellos.
# Si en el remoto se eliminaron carpetas, archivos o líneas de código, en tu local también se reflejarán esos cambios al finalizar el rebase.
# Mantiene un historial más lineal, sin commits de merge.

git clone https://github.com/nombre_usuario/nombre_repositorio.git
# Clonar un repositorio desde GitHub (en repos privados primero tienes que tener acceso, puedes clonar si es repositorio propio)
---------------------------------------------------------------------

git fetch origin
# Descarga los commits, ramas y actualizaciones del repositorio remoto origin.
# No cambia tu rama local ni tu carpeta de trabajo. Solo actualiza las referencias remotas (por ejemplo, origin/main).
# Permite ver los cambios nuevos en remoto antes de integrarlos a tu rama local.

git log HEAD..origin/main --oneline # Muestra los commits nuevo en la rama remota.
git log origin/main --oneline #Todo el historial de la rama remota origin/main.
git log origin/main # Muestra el historial completo de commits de la rama remota origin/main.
git log	# El historial de tu rama local actual.
git diff origin/main # Muestra exactamente qué líneas cambiaron en los archivos, comparando tu rama local con la rama remota origin/main.


git merge origin/main
# Si hiciste fetch antes, y ambos (tú y el remoto) modificaron la misma línea de un archivo, Git generará un conflicto que debes resolver.
# Si no ejecutaste fetch, usará la referencia de origin/main que tengas localmente (puede estar desactualizada) y no detectará cambios recientes del remoto.
# Crea un commit de merge si hay diferencias. Mantiene la historia de ambos flujos de trabajo.

git rebase origin/main # Ideal si quieres que tu trabajo parezca que fue hecho “después” de los cambios en remoto o locales.
---------------------------------------------------------------------
git fetch origin # Actualiza tu referencia remota.
git rebase origin/main # Reaplica tus commits locales encima de los cambios de origin/main, como si los hubieras hecho después.
---------------------------------------------------------------------
git fetch origin # Actualiza tu referencia remota.
git merge origin/main # Fusiona los cambios de origin/main en tu rama local, manteniendo tus cambios locales y combinándolos con los remotos.
---------------------------------------------------------------------
git fetch origin
git reset --hard origin/main # Reemplaza todo tu repositorio local con el estado de origin/main.
git clean -fd # Elimina archivos no versionados y carpetas no versionadas.
git fetch origin && git reset --hard origin/main && git clean -fd # Comando directo
---------------------------------------------------------------------
git fetch origin # Descarga la última versión del repositorio remoto (sin tocar tus archivos aún).
git reset --hard origin/main # Reemplaza tu rama local con la versión del remoto. Tu trabajo local se borra y se reemplaza completamente con lo que hay en el remoto.

sudo apt update   # Actualiza la base de datos de versiones disponibles
sudo apt upgrade  # Instala las nuevas versiones de tus paquetes

```
