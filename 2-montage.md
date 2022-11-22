## Creando carpetas
```
mkfs -v -t ext4 /dev/sdb3
mkfs -v -t ext2 /dev/sdb1
mkswap /dev/sdb2
```

# (I)variables IMPORTANTE
```
export LFS=/mnt/lfs
echo "export LFS=/mnt/lfs" >> ~/.bashrc
source ~/.bashrc
```
```
### conectarse en root
su -
echo "export LFS=/mnt/lfs" >> /root/.bashrc
source /root/.bashrc
```

### Estando en root, montar los discos
```
mkdir -pv $LFS
mkdir -v $LFS/boot
mount -v -t ext4 /dev/sdb3 $LFS
mount -v -t ext2 /dev/sdb1 $LFS/boot
/sbin/swapon -v /dev/sdb2
```
