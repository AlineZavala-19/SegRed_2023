## Wave a flag
## Objetivo
Can you invoke help flags for a tool or binary? [This program](https://mercury.picoctf.net/static/b28b6021d6040b086c2226ebeb913bc2/warm) has extraordinarily helpful information...

## Hints
1. This program will only work in the webshell or another Linux computer.
2. To get the file accessible in your shell, enter the following in the Terminal prompt: `$ wget https://mercury.picoctf.net/static/b28b6021d6040b086c2226ebeb913bc2/warm`
3. Run this program by entering the following in the Terminal prompt: `$ ./warm`, but you'll first have to make it executable with `$ chmod +x warm`
4. -h and --help are the most common arguments to give to programs to get more information from them!
5. Not every program implements help features like -h and --help
## Datos de acceso al nivel
alivz
Webshell

## Solución
```bash
alivz-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/b28b6021d6040b086c2226ebeb913bc2/warm
--2023-10-02 03:09:45--  https://mercury.picoctf.net/static/b28b6021d6040b086c2226ebeb913bc2/warm
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 10936 (11K) [application/octet-stream]
Saving to: 'warm'

warm                  100%[======================>]  10.68K  --.-KB/s    in 0s      

2023-10-02 03:09:45 (315 MB/s) - 'warm' saved [10936/10936]

alivz-picoctf@webshell:~$ ls
README.txt  flag  warm
alivz-picoctf@webshell:~$ ./warm
-bash: ./warm: Permission denied
alivz-picoctf@webshell:~$ ls -la
total 84
drwxr-xr-x 4 alivz-picoctf alivz-picoctf  4096 Oct  2 03:09 .
drwxr-xr-x 3 root          root             27 Sep 25 16:38 ..
-rw------- 1 alivz-picoctf alivz-picoctf  1157 Oct  1 22:46 .bash_history
-rw-r--r-- 1 alivz-picoctf alivz-picoctf   220 Sep 25 16:38 .bash_logout
-rw-r--r-- 1 alivz-picoctf alivz-picoctf  3771 Sep 25 16:38 .bashrc
-rw-rw-r-- 1 alivz-picoctf alivz-picoctf  1024 Oct  2 03:02 .flag.swp
-rw------- 1 alivz-picoctf alivz-picoctf    20 Oct  1 22:50 .lesshst
drwxrwxr-x 3 alivz-picoctf alivz-picoctf    19 Oct  1 07:23 .local
-rw-r--r-- 1 alivz-picoctf alivz-picoctf 12288 Oct  1 02:56 .ltdis.sh.swp
-rw-r--r-- 1 alivz-picoctf alivz-picoctf   807 Sep 25 16:38 .profile
-rw------- 1 alivz-picoctf alivz-picoctf 12288 Oct  1 09:54 .pwhash.py.swp
-rw------- 1 alivz-picoctf alivz-picoctf   198 Oct  1 09:14 .python_history
drwx------ 2 alivz-picoctf alivz-picoctf    48 Oct  1 05:00 .ssh
-rw-rw-r-- 1 alivz-picoctf alivz-picoctf   167 Oct  1 07:30 .wget-hsts
-rw-r--r-- 1 root          root           4443 Oct  2 03:09 README.txt
-rw-rw-r-- 1 alivz-picoctf alivz-picoctf    34 Mar 16  2021 flag
-rw-rw-r-- 1 alivz-picoctf alivz-picoctf 10936 Mar 16  2021 warm
alivz-picoctf@webshell:~$ chmod 744 warm
alivz-picoctf@webshell:~$ ./warm
Hello user! Pass me a -h to learn what I can do!
alivz-picoctf@webshell:~$ ./warm -h
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_d6969390}
```
## Notas adicionales
wget -->
ls -->
./ -->
-la -->
chmod 744 -->
-h -->
## Referencias
