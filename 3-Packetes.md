# (I) Estando en ROOT
## Empezamos crendo la carpeta donde tendras todos los paquetes
```
mkdir -v $LFS/sources
chmod -v a+wt $LFS/sources
```
### Sitio para descargar los ultimos paquetes.
https://ftp.wrz.de/pub/LFS/lfs-packages/

### yo descargare el lfs-packages-11.2.tar (ya que estoy haciendo la version del libro 11.2)
```
cd $LFS/sources/
wget https://ftp.wrz.de/pub/LFS/lfs-packages/lfs-packages-11.2.tar
tar xvf lfs-packages-11.2.tar
mv 11.2-rc1/* .
rm -r lfs-packages-11.2.tar 11.2-rc1
```
verificar los paquetes
```
pushd $LFS/sources
  md5sum -c md5sums
popd
```

# Pour les personnes de 42.
Changer tout **$LFS/sources** pour **$LFS/usr/src/kernel-<ta version>** 
* Exemple:
  ```
  mkdir -v $LFS/usr/src/kernel-<ta version>
  chmod -v a+wt $LFS/usr/src/kernel-<ta version>
  ```
