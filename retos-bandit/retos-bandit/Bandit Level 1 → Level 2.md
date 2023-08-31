Bandit Level 1 → Level 2
## Objetivo
The password for the next level is stored in a file called **-** located in the home directory
## Datos de acceso al nivel
```
bandit1
NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
```
## Solución
```bash
bandit1@bandit:~$ whoami
bandit1
bandit1@bandit:~$ pwd
/home/bandit1
bandit1@bandit:~$ ls
-
bandit1@bandit:~$ cat -
^C
bandit1@bandit:~$ cat ./-
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
bandit1@bandit:~$ pwd
/home/bandit1
bandit1@bandit:~$ cat /home/bandit1/-
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
bandit1@bandit:~$
```
## Notas adicionales
- Cuando un archivo comienza con - para poder accederlo tenemos que anteponer ./ al nombre o bien especificar la ruta completa al archivo
## Referencias
- [Búsqueda en Google de "nombre de archivo discontinuo"](https://www.google.com/search?q=dashed+filename)