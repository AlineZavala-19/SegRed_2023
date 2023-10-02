### Magikarp Ground Mission
## Objetivo
Do you know how to move between directories and read files in the shell? Start the container, `ssh` to it, and then `ls` once connected to begin. Login via `ssh` as `ctf-player` with the password, `481e7b14`

---

|CHALLENGE ENDPOINTS|
|---|
|SSH|`ssh ctf-player@venus.picoctf.net -p 58983`|

## Hints
Finding a cheatsheet for bash would be really helpful!
## Datos de acceso al nivel
alivz
Webshell
## Solución
ssh ctf-player@venus.picoctf.net -p 58886
password: 481e7b14
```bash
ctf-player@pico-chall$ ls
3of3.flag.txt  drop-in
ctf-player@pico-chall$ cat 1of3.flag.txt 
cat: 1of3.flag.txt: No such file or directory
ctf-player@pico-chall$ 1of3.flag.txt instructions-to-2of3.txt
-bash: 1of3.flag.txt: command not found
ctf-player@pico-chall$ cd /
ctf-player@pico-chall$ ls
2of3.flag.txt  bin  boot  dev  etc  home  instructions-to-3of3.txt  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
ctf-player@pico-chall$ cat 2of3.flag.txt
0ut_0f_\/\/4t3r_
ctf-player@pico-chall$ cat instructions-to-3of3.txt
Lastly, ctf-player, go home... more succinctly `~`
ctf-player@pico-chall$ cd ~
ctf-player@pico-chall$ ls
3of3.flag.txt  drop-in
ctf-player@pico-chall$ cat 3of3.flag.txt
1118a9a4}
ctf-player@pico-chall$ 
```
## Notas adicionales
ls
cat
## Referencias