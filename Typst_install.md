# Install TYPST
```bash
# 1. Definir arquitectura
ARCH="x86_64-unknown-linux-musl"

# 2. Obtener la URL de la ÚLTIMA versión automáticamente desde GitHub
URL=$(curl -s https://api.github.com/repos/typst/typst/releases/latest | grep "browser_download_url.*$ARCH.tar.xz" | cut -d : -f 2,3 | tr -d \")

# 3. Descargar
wget -O typst.tar.xz "$URL"

# 4. Extraer
tar -xf typst.tar.xz

# 5. Instalar (Mover el binario buscando dentro de la carpeta extraída)
# El asterisco * nos ahorra saber el nombre exacto de la versión
sudo mv typst-$ARCH*/typst /usr/local/bin/

# 6. Limpiar
rm -rf typst.tar.xz typst-$ARCH*

# 7. Verificar
typst --version
```
