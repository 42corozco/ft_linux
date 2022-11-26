## * Instalaciones que hice en mi VM (UBUNTU-22.04.1 - Virtualbox) 
## LFS ( 11.2-systemd ) Version -[Fr][1] o -[En][2]
[1]: https://fr.linuxfromscratch.org/view/lfs-systemd-stable/index.html
[2]: https://linuxfromscratch.org/lfs/view/11.2-systemd/


* Instalar openssh-server (conectarme en ssh a la maquina virtual) y Vim (editor de texto)
```
sudo apt-get install -y openssh-server vim
```

## Ya que la VM era nueva, no tenia un Password para Root, lo creamos. 
```
sudo passwd root
```

## Este script, se encuentra en la propia pagina de LFS. (Es para ver las versiones)
```
cat > version-check.sh << "EOF"
#!/bin/bash
# Script simple pour afficher les numéros de version des outils de développement critiques
export LC_ALL=C
bash --version | head -n1 | cut -d" " -f2-4
MYSH=$(readlink -f /bin/sh)
echo "/bin/sh -> $MYSH"
echo $MYSH | grep -q bash || echo "ERREUR: /bin/sh ne pointe pas vers bash"
unset MYSH

echo -n "Binutils: "; ld --version | head -n1 | cut -d" " -f3-
bison --version | head -n1

if [ -h /usr/bin/yacc ]; then
  echo "/usr/bin/yacc -> `readlink -f /usr/bin/yacc`";
elif [ -x /usr/bin/yacc ]; then
  echo yacc is `/usr/bin/yacc --version | head -n1`
else
  echo "yacc introuvable"
fi

echo -n "Coreutils: "; chown --version | head -n1 | cut -d")" -f2
diff --version | head -n1
find --version | head -n1
gawk --version | head -n1

if [ -h /usr/bin/awk ]; then
  echo "/usr/bin/awk -> `readlink -f /usr/bin/awk`";
elif [ -x /usr/bin/awk ]; then
  echo awk is `/usr/bin/awk --version | head -n1`
else
  echo "awk introuvable"
fi

gcc --version | head -n1
g++ --version | head -n1
grep --version | head -n1
gzip --version | head -n1
cat /proc/version
m4 --version | head -n1
make --version | head -n1
patch --version | head -n1
echo Perl `perl -V:version`
python3 --version
sed --version | head -n1
tar --version | head -n1
makeinfo --version | head -n1  # version de texinfo
xz --version | head -n1

echo 'int main(){}' > dummy.c && g++ -o dummy dummy.c
if [ -x dummy ]
  then echo "g++ compilation OK";
  else echo "g++ compilation échouée"; fi
rm -f dummy.c dummy
EOF
bash version-check.sh
```
---------------------------------------------
## instalar lo que haga falta.
```
sudo apt-get install -y g++ make texinfo m4 gawk bison
```
### (si error) ERREUR: /bin/sh ne pointe pas vers bash
```
sudo ln -sf bash /bin/sh
```
