## Level X
## Objetivo
## Datos de acceso al nivel
## Solución
```bash
alivz-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/85/gdbme
--2023-11-23 00:38:45--  https://artifacts.picoctf.net/c/85/gdbme
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.93, 3.160.5.18, 3.160.5.71, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.93|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 17048 (17K) [application/octet-stream]
Saving to: 'gdbme.1'

gdbme                                                    100%[================================================================================================================================>]  16.65K  --.-KB/s    in 0s      

2023-11-23 00:38:45 (35.5 MB/s) - 'gdbme.1' saved [17048/17048]

alivz-picoctf@webshell:~$ chmod +x gdbme
alivz-picoctf@webshell:~$ gdb gdbme
GNU gdb (Ubuntu 12.0.90-0ubuntu1) 12.0.90
Copyright (C) 2022 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
Type "show copying" and "show warranty" for details.
This GDB was configured as "x86_64-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<https://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
    <http://www.gnu.org/software/gdb/documentation/>.

For help, type "help".
Type "apropos word" to search for commands related to "word"...
Reading symbols from gdbme...
(No debugging symbols found in gdbme)
(gdb) layout asm
```
![[Pasted image 20231122184038.png]]

flag --> picoCTF{d3bugg3r_dr1v3_197c378a}
## Notas adicionales
## Referencias


```bash
wgetalivz-picoctf@webshell:~$ wget https://jupiter.challenges.picoctf.org/static/27dd5548b14661f65ce3ac6a8a8f575b/need-for-speed
--2023-11-23 02:19:29--  https://jupiter.challenges.picoctf.org/static/27dd5548b14661f65ce3ac6a8a8f575b/need-for-speed
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 8888 (8.7K) [application/octet-stream]
Saving to: 'need-for-speed'

need-for-speed                                           100%[================================================================================================================================>]   8.68K  --.-KB/s    in 0s      

2023-11-23 02:19:29 (278 MB/s) - 'need-for-speed' saved [8888/8888]

alivz-picoctf@webshell:~$ file need-for-speed
need-for-speed: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=2d0d401d07683664113690a7fb94413a0039d228, not stripped
alivz-picoctf@webshell:~$ chmod -x need-for-speed
alivz-picoctf@webshell:~$ ./need-for-speed
-bash: ./need-for-speed: Permission denied
alivz-picoctf@webshell:~$ chmod +x need-for-speed
alivz-picoctf@webshell:~$ ./need-for-speed
Keep this thing over 50 mph!
============================

Creating key...
Not fast enough. BOOM!
alivz-picoctf@webshell:~$ objdump -D need-for-speed -M intel | grep '<main>:' -A20
000000000000091a <main>:
 91a:   55                      push   rbp
 91b:   48 89 e5                mov    rbp,rsp
 91e:   48 83 ec 10             sub    rsp,0x10
 922:   89 7d fc                mov    DWORD PTR [rbp-0x4],edi
 925:   48 89 75 f0             mov    QWORD PTR [rbp-0x10],rsi
 929:   b8 00 00 00 00          mov    eax,0x0
 92e:   e8 a5 ff ff ff          call   8d8 <header>
 933:   b8 00 00 00 00          mov    eax,0x0
 938:   e8 f2 fe ff ff          call   82f <set_timer>
 93d:   b8 00 00 00 00          mov    eax,0x0
 942:   e8 36 ff ff ff          call   87d <get_key>
 947:   b8 00 00 00 00          mov    eax,0x0
 94c:   e8 5b ff ff ff          call   8ac <print_flag>
 951:   b8 00 00 00 00          mov    eax,0x0
 956:   c9                      leave  
 957:   c3                      ret    
 958:   0f 1f 84 00 00 00 00    nop    DWORD PTR [rax+rax*1+0x0]
 95f:   00 

0000000000000960 <__libc_csu_init>:
alivz-picoctf@webshell:~$ gdb
GNU gdb (Ubuntu 12.0.90-0ubuntu1) 12.0.90
Copyright (C) 2022 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
Type "show copying" and "show warranty" for details.
This GDB was configured as "x86_64-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<https://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
    <http://www.gnu.org/software/gdb/documentation/>.

For help, type "help".
Type "apropos word" to search for commands related to "word".
(gdb) need-for-speed
Undefined command: "need-for-speed".  Try "help".
(gdb) exit
alivz-picoctf@webshell:~$ gdb need-for-speed
GNU gdb (Ubuntu 12.0.90-0ubuntu1) 12.0.90
Copyright (C) 2022 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
Type "show copying" and "show warranty" for details.
This GDB was configured as "x86_64-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<https://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
    <http://www.gnu.org/software/gdb/documentation/>.

For help, type "help".
Type "apropos word" to search for commands related to "word"...
Reading symbols from need-for-speed...
(No debugging symbols found in need-for-speed)
(gdb) info functions
All defined functions:

Non-debugging symbols:
0x00000000000005d8  _init
0x0000000000000600  putchar@plt
0x0000000000000610  puts@plt
0x0000000000000620  alarm@plt
0x0000000000000630  __sysv_signal@plt
0x0000000000000640  exit@plt
0x0000000000000650  __cxa_finalize@plt
0x0000000000000660  _start
0x0000000000000690  deregister_tm_clones
0x00000000000006d0  register_tm_clones
0x0000000000000720  __do_global_dtors_aux
0x0000000000000760  frame_dummy
0x000000000000076a  decrypt_flag
0x00000000000007f1  calculate_key
0x000000000000080e  alarm_handler
0x000000000000082f  set_timer
0x000000000000087d  get_key
0x00000000000008ac  print_flag
0x00000000000008d8  header
0x000000000000091a  main
0x0000000000000960  __libc_csu_init
0x00000000000009d0  __libc_csu_fini
0x00000000000009d4  _fini
(gdb) set disassembly-flavor intel
(gdb) disassemble main
Dump of assembler code for function main:
   0x000000000000091a <+0>:     push   rbp
   0x000000000000091b <+1>:     mov    rbp,rsp
   0x000000000000091e <+4>:     sub    rsp,0x10
   0x0000000000000922 <+8>:     mov    DWORD PTR [rbp-0x4],edi
   0x0000000000000925 <+11>:    mov    QWORD PTR [rbp-0x10],rsi
   0x0000000000000929 <+15>:    mov    eax,0x0
   0x000000000000092e <+20>:    call   0x8d8 <header>
   0x0000000000000933 <+25>:    mov    eax,0x0
   0x0000000000000938 <+30>:    call   0x82f <set_timer>
   0x000000000000093d <+35>:    mov    eax,0x0
   0x0000000000000942 <+40>:    call   0x87d <get_key>
   0x0000000000000947 <+45>:    mov    eax,0x0
   0x000000000000094c <+50>:    call   0x8ac <print_flag>
   0x0000000000000951 <+55>:    mov    eax,0x0
   0x0000000000000956 <+60>:    leave  
   0x0000000000000957 <+61>:    ret    
End of assembler dump.
(gdb) break main
Breakpoint 1 at 0x91e
(gdb) info breakpoints
Num     Type           Disp Enb Address            What
1       breakpoint     keep y   0x000000000000091e <main+4>
(gdb) run
Starting program: /home/alivz-picoctf/need-for-speed 
warning: Error disabling address space randomization: Operation not permitted
[Thread debugging using libthread_db enabled]
Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".

Breakpoint 1, 0x000056399320091e in main ()
(gdb) disassemble main
Dump of assembler code for function main:
   0x000056399320091a <+0>:     push   rbp
   0x000056399320091b <+1>:     mov    rbp,rsp
=> 0x000056399320091e <+4>:     sub    rsp,0x10
   0x0000563993200922 <+8>:     mov    DWORD PTR [rbp-0x4],edi
   0x0000563993200925 <+11>:    mov    QWORD PTR [rbp-0x10],rsi
   0x0000563993200929 <+15>:    mov    eax,0x0
   0x000056399320092e <+20>:    call   0x5639932008d8 <header>
   0x0000563993200933 <+25>:    mov    eax,0x0
   0x0000563993200938 <+30>:    call   0x56399320082f <set_timer>
   0x000056399320093d <+35>:    mov    eax,0x0
   0x0000563993200942 <+40>:    call   0x56399320087d <get_key>
   0x0000563993200947 <+45>:    mov    eax,0x0
   0x000056399320094c <+50>:    call   0x5639932008ac <print_flag>
   0x0000563993200951 <+55>:    mov    eax,0x0
   0x0000563993200956 <+60>:    leave  
   0x0000563993200957 <+61>:    ret    
End of assembler dump.
(gdb) call (int) get_key()
Creating key...
Finished
$1 = 9
(gdb) call (int) print_flag()
Printing flag:
PICOCTF{Good job keeping bus #1f2ac4ec speeding along!}
$2 = 56
(gdb) exit
A debugging session is active.

        Inferior 1 [process 244] will be killed.

Quit anyway? (y or n) y
```

```bash

```
