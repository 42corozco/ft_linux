# Erreur test 42.

## perl (c2ph - pstruct)
* **https://fr.linuxfromscratch.org/view/lfs-5.0-fr/appendixa/perl.html**
* **https://perldoc.perl.org/perldeprecation**
```
* c2ph et pstruct ne sont plus installés depuis Perl 5.26
```

## util-linux (tailf)
* tailf est obsolète **https://manpages.debian.org/testing/util-linux/tailf.1.en.html**
```
Attention : l'utilisation de 'tailf' est obsolète, utilisez 'tail -f' à la place
```

## gawk (igaw et gawk-4)
* igaw **https://github.com/openwrt/packages/issues/5110**
```
* Le script igawk et la page de manuel igawk.1 ne sont plus installés par `make install'. Ils sont obsolètes depuis gawk 4.0.0.
```

## pg
* **https://launchpad.net/ubuntu/+source/util-linux/2.29.2-2ubuntu1**
```
* Stop shipping the deprecated 'pg' utility
* Revert "Explicitly (re)enable deprecated pg utility"
* Remove 'pg' from being a pager alternative
```

## catchsegv
* **https://gitlab.gnome.org/GNOME/mutter/-/issues/2120**
```
Fixed on 2.35 by removing libSegFault and catchsegv.
```
