## cambio de nombre
Edit the Makefile in the main directory and manually change the following variables:
```
EXTRAVERSION = -<login>
```
Sole cambiar el extraversion si quieres cambiar el login.

# Si no has hecho make, tiempo de hacerlo
```
make 
make modules_install
```
Copiar los ficheros
```
cp -iv arch/x86/boot/bzImage /boot/vmlinuz-5.19.2-corozco
cp -iv System.map /boot/System.map-5.19.2
cp -iv .config /boot/config-5.19.2
```