### waves over lambda
## Objetivo
We made a lot of substitutions to encrypt this. Can you decrypt it? Connect with `nc jupiter.challenges.picoctf.org 13758`.
## Hints
1. Flag is not in the usual flag format
## Datos de acceso al nivel
## Solución
```bash
┌──(kali㉿kali)-[~]
└─$ nc jupiter.challenges.picoctf.org 13758~  
-------------------------------------------------------------------------------
gwvecfnl joco bl pwmc kqfe - kcozmovgp_bl_g_wtoc_qfdyhf_hvtnkcnfpm
-------------------------------------------------------------------------------
jftbve jfh lwdo nbdo fn dp hblrwlfq ujov bv qwvhwv, b jfh tblbnoh njo ycbnblj dmlomd, fvh dfho lofcgj fdwve njo ywwal fvh dfrl bv njo qbycfcp coefchbve ncfvlpqtfvbf; bn jfh lncmga do njfn lwdo kwcoavwuqoheo wk njo gwmvncp gwmqh jfchqp kfbq nw jfto lwdo bdrwcnfvgo bv hofqbve ubnj f vwyqodfv wk njfn gwmvncp. b kbvh njfn njo hblncbgn jo vfdoh bl bv njo oxncodo ofln wk njo gwmvncp, smln wv njo ywchocl wk njcoo lnfnol, ncfvlpqtfvbf, dwqhftbf fvh ymawtbvf, bv njo dbhln wk njo gfcrfnjbfv dwmvnfbvl; wvo wk njo ubqholn fvh qofln avwuv rwcnbwvl wk omcwro. b ufl vwn fyqo nw qbejn wv fvp dfr wc uwca ebtbve njo oxfgn qwgfqbnp wk njo gflnqo hcfgmqf, fl njoco fco vw dfrl wk njbl gwmvncp fl pon nw gwdrfco ubnj wmc wuv wchvfvgo lmctop dfrl; ymn b kwmvh njfn yblncbni, njo rwln nwuv vfdoh yp gwmvn hcfgmqf, bl f kfbcqp uoqq-avwuv rqfgo. b ljfqq ovnoc joco lwdo wk dp vwnol, fl njop dfp cokcolj dp dodwcp ujov b nfqa wtoc dp ncftoql ubnj dbvf.

```
Como no sabemos que letras se reemplazaron ni tenemos la llave, se tiene que hacer un criptoanálisis de frecuencias y ver que letras son las que se repiten y la frecuencia en qué lo hacen.
Buscamos una página para resolver la sustitución e introducimos todo el código, en la parte de arriba obtenemos la bandera.
-------------------------------------------------------------------------------
congrats here is your flag - frequency_is_c_over_lambda_dnvtfrtayu
-------------------------------------------------------------------------------
having had some time at my disposal when in london, i had visited the british museum, and made search among the books and maps in the library regarding transylvania; it had struck me that some foreknowledge of the country could hardly fail to have some importance in dealing with a nobleman of that country. i find that the district he named is in the extreme east of the country, just on the borders of three states, transylvania, moldavia and bukovina, in the midst of the carpathian mountains; one of the wildest and least known portions of europe. i was not able to light on any map or work giving the exact locality of the castle dracula, as there are no maps of this country as yet to compare with our own ordnance survey maps; but i found that bistritz, the post town named by count dracula, is a fairly well-known place. i shall enter here some of my notes, as they may refresh my memory when i talk over my travels with mina.
## Notas adicionales
En [criptografía](https://es.wikipedia.org/wiki/Criptograf%C3%ADa "Criptografía"), el **cifrado por sustitución** es un método de [cifrado](https://es.wikipedia.org/wiki/Cifrado_(criptograf%C3%ADa) "Cifrado (criptografía)") por el que unidades de texto plano son sustituidas con texto cifrado siguiendo un sistema regular; las "unidades" pueden ser una sola letra (el caso más común), pares de letras, tríos de letras, mezclas de lo anterior, entre otros. El receptor descifra el texto realizando la sustitución inversa.
## Referencias
[Cifrado por sustitución - Wikipedia, la enciclopedia libre](https://es.wikipedia.org/wiki/Cifrado_por_sustituci%C3%B3n)
[Substitution Solver | guballa.de](https://www.guballa.de/substitution-solver)