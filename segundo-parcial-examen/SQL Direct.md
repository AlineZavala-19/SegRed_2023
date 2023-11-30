### SQL Direct
## Objetivo
Connect to this PostgreSQL server and find the flag!
Additional details will be available after launching your challenge instance.
## Datos de acceso al nivel
## Solución
```bash
┌──(kali㉿kali)-[~/SEGURIDAD7A]
└─$ psql -h saturn.picoctf.net -p 56383 -U postgres pico
^[[APassword for user postgres: 

psql (16.0 (Debian 16.0-2), server 15.2 (Debian 15.2-1.pgdg110+1))
Type "help" for help.

pico=# 
pico=# 
pico=# help
You are using psql, the command-line interface to PostgreSQL.
Type:  \copyright for distribution terms
       \h for help with SQL commands
       \? for help with psql commands
       \g or terminate with semicolon to execute query
       \q to quit
pico=# \h
pico=# \l
pico=# \dt
         List of relations
 Schema | Name  | Type  |  Owner   
--------+-------+-------+----------
 public | flags | table | postgres
(1 row)

pico=# select * from flags;
 id | firstname | lastname  |                address                 
----+-----------+-----------+----------------------------------------
  1 | Luke      | Skywalker | picoCTF{L3arN_S0m3_5qL_t0d4Y_31fd14c0}
  2 | Leia      | Organa    | Alderaan
  3 | Han       | Solo      | Corellia
(3 rows)


```
picoCTF{L3arN_S0m3_5qL_t0d4Y_31fd14c0}
## Notas adicionales
## Referencias