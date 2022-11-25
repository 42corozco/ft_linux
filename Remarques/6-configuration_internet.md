## Esto es para configurar, mas que todo en el proyecto de 42, donde usaremos el lfs dentro de una maquina virtual.

### Preciso, que solo hago la parte 9.2.1.2, 9.2.2.2, 9.2.3. y 9.2.4

Dentro de la maquina virtual, hacemos la comanda **networkctl list** la cual nos dara la lista de redes.
```
WARNING: systemd-networkd is not running, output will be incomplete.

IDX LINK   TYPE     OPERATIONAL SETUP    
  1 lo     loopback n/a         unmanaged
  2 enp0s3 ether    n/a         unmanaged

2 links listed.
```

o, usando **networkctl status** nos dara mas informacion
```
WARNING: systemd-networkd is not running, output will be incomplete.

●        State: n/a
  Online state: unknown
       Address: 10.0.2.15 on enp0s3
                fe80::32e4:3078:f8c4:7c1f on enp0s3
       Gateway: 10.0.2.2 on enp0s3
```
### Para mas informacion [-- linuxtricks --][1]

Como en mi caso, estare usando una ip fija, usare
* para ver tu dns, en la terminal fuera de la maquina virtual, pudes hacer **cat /etc/systemd/resolved.conf**

* Copiar la parte del resolved.conf de tu terminal, en tu lfs **/etc/resolv.conf**

Para la ip fija, haremos lo mismo que esta en [9.2.1.2. Static IP Configuration][2] de Linux From Scratch 

**/etc/systemd/network/10-eth-static.network**
```
[Match]
Name=enp0s3             <dato dado de networkctl status>

[Network]
Address=10.0.2.15/24    <dato dado de networkctl status>
Gateway=10.0.2.2        <dato dado de networkctl status>
DNS=                    <tu dns {cat /etc/systemd/resolved.conf}>
```

**/etc/hosts**
```
127.0.0.1 localhost corozco-vm
::1       localhost corozco-vm
```







[1]:https://www.linuxtricks.fr/wiki/systemd-le-reseau-avec-systemd-networkd

[2]:https://linuxfromscratch.org/lfs/view/11.2-systemd/chapter09/network.html