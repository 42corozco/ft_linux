## Damos formato a un dispositivo de almacenamiento de bloque con un determinado sistema de archivos
  1. /dev/sdb1 -> "   /   "
  2. /dev/sdb2 -> " swap  "
  3. /dev/sdb3 -> " /Boot "
```
mkfs -v -t ext4 /dev/sdb3
mkfs -v -t ext2 /dev/sdb1
mkswap /dev/sdb2
```
# Attention
## Importante tener en cuanta la variable LFS.

Toda la instalacion la hice en ROOT, tener cuidado con las comandas que hagas.

* Guardarla en tu Usuario.
```
export LFS=/mnt/lfs
echo "export LFS=/mnt/lfs" >> ~/.bashrc
source ~/.bashrc
```
* Guardarla en tu Root
```
### conectarse en root
su -
echo "export LFS=/mnt/lfs" >> /root/.bashrc
source /root/.bashrc
```

### Estando en root, montar los discos
* mounts a storage device or filesystem, making it accessible and attaching it to an existing directory structure.
```
mkdir -pv $LFS
mkdir -v $LFS/boot
mount -v -t ext4 /dev/sdb3 $LFS
mount -v -t ext2 /dev/sdb1 $LFS/boot
/sbin/swapon -v /dev/sdb2
```
