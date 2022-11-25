## Preparar el systema de ficheros para entrar en chroot

Esto es por si en algun momento te desconectas, o dejas la instalacion para luego.

```
mkdir -pv $LFS
mkdir -v $LFS/boot      
mount -v -t ext4 /dev/sdb3 $LFS
mount -v -t ext2 /dev/sdb1 $LFS/boot
/sbin/swapon -v /dev/sdb2

mkdir -pv $LFS/{dev,proc,sys,run,boot}
mount -v --bind /dev $LFS/dev
mount -v --bind /dev/pts $LFS/dev/pts
mount -vt proc proc $LFS/proc
mount -vt sysfs sysfs $LFS/sys
mount -vt tmpfs tmpfs $LFS/run
if [ -h $LFS/dev/shm ]; then
  mkdir -pv $LFS/$(readlink $LFS/dev/shm)
fi
```

## Conectarse en chroot
```
chroot "$LFS" /usr/bin/env -i   \
    HOME=/root                  \
    TERM="$TERM"                \
    PS1='(lfs chroot) \u:\w\$ ' \
    PATH=/usr/bin:/usr/sbin     \
    /bin/bash --login
```
