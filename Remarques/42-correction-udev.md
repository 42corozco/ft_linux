* si tienes systemctl tienes udev!
* Pour savoir si udev est bien sur ton pc https://linuxembedded.fr/2015/05/une-introduction-a-udev
```
udevadm monitor -k
```

## Les règles udev
Lorsque udev reçoit un événement noyau, il utilise une base de règles et applique les règles qui correspondent à l'événement. Les règles viennent de trois répertoires différents (du plus au moins prioritaire):
```
/etc/udev/rules.d/*.rules (règles locales ajoutées par l'administrateur),
/run/udev/rules.d/*.rules (règles volatiles, généralement créées par d'autres règles),
/lib/udev/rules.d/*.rules (règles fourni par la distribution).
```
