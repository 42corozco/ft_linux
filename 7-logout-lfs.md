# Quitar chmod y desmontar los sistemas de ficheros virtuales.

## Desconectarte de tu maquina virtual.
logout

## Umount todo.
```
umount -v $LFS/dev/pts
umount -v $LFS/dev
umount -v $LFS/run
umount -v $LFS/proc
umount -v $LFS/sys
umount -v $LFS/boot
umount -v $LFS/home
umount -v $LFS
```

## Apagar la maquina virtual?
```
poweroff
```
