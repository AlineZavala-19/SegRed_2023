### la cifra de
## Objetivo
I found this cipher in an old book. Can you figure out what it says? Connect with .`nc jupiter.challenges.picoctf.org 58295`
## Hints
1. There are tools that make this easy.
2. Perhaps looking at history will help
## Datos de acceso al nivel
## Solución
```bash
┌──(kali㉿kali)-[~]
└─$ nc jupiter.challenges.picoctf.org 58295 
Encrypted message:
Ne iy nytkwpsznyg nth it mtsztcy vjzprj zfzjy rkhpibj nrkitt ltc tnnygy ysee itd tte cxjltk

Ifrosr tnj noawde uk siyyzre, yse Bnretèwp Cousex mls hjpn xjtnbjytki xatd eisjd

Iz bls lfwskqj azycihzeej yz Brftsk ip Volpnèxj ls oy hay tcimnyarqj dkxnrogpd os 1553 my Mnzvgs Mazytszf Merqlsu ny hox moup Wa inqrg ipl. Ynr. Gotgat Gltzndtg Gplrfdo 

Ltc tnj tmvqpmkseaznzn uk ehox nivmpr g ylbrj ts ltcmki my yqtdosr tnj wocjc hgqq ol fy oxitngwj arusahje fuw ln guaaxjytrd catizm tzxbkw zf vqlckx hizm ceyupcz yz tnj fpvjc hgqqpohzCZK{m311a50_0x_a1rn3x3_h1ah3xf966878l}

Tnj qixxe wkqw-duhfmkseej ipsiwtpznzn uk l puqjarusahjeii htpnjc hubpvkw, hay rldk fcoaso 1467 be Qpot Gltzndtg Fwbkwei.

Zmp Volpnèxj Nivmpr ox ehkwpfuwp surptorps ifwlki ehk Fwbkwei Jndc uw Llhjcto Htpnjc.

It 1508, Ozhgsyey Ycizmpmozd itapnzjo tnj do-ifwlki eahzwa xjntg (f xazwtx uk dhokeej fwpnfmezx) ehgy hoaqo lgypr hj l cxneiifw curaotjyt uk ehk Atgksèce Inahkw.

Merqlsu’x deityd htzkrje avupaxjo it 1555 fd a itytosfaznzn uk ehk ktryy. Ehk qzwkw saraps uk ehk fwpnfmezx lrk szw ymtfzjo rklflgwwy, hze tnj llvmlbkyd ati ehk nydkc wezypry fce sniej gj mkfys uk l mtjxotnn kkd ahxfde, cmtcn hln hj oilkprkse woys eghs cuwceyuznjjyt.

```
El texto nos lo podemos llevar al CyberChef y seleccionar la opción Vigenere pero nos pide una llave, para esto buscamos una opción online para obtenerla, en ella ingresamos todo el código dado y mediante un criptoanálisis para saber cuales letras o palabras se repiten y con que frecuencia, deducir la llave. La llave que se utilizó es 'flag' y ahora si en CyberChef desciframos el código y en el texto se encuentra la bandera.
## Notas adicionales
El **cifrado de Vigenère** es un cifrado basado en diferentes series de caracteres o letras del [cifrado César](https://es.wikipedia.org/wiki/Cifrado_C%C3%A9sar "Cifrado César") formando estos caracteres una tabla, llamada **tabla de Vigenère**, que se usa como clave. El cifrado de Vigenère es un [cifrado por sustitución](https://es.wikipedia.org/wiki/Cifrado_por_sustituci%C3%B3n "Cifrado por sustitución") simple polialfabético.
## Referencias
[Cifrado de Vigenère - Wikipedia, la enciclopedia libre](https://es.wikipedia.org/wiki/Cifrado_de_Vigen%C3%A8re)
[Vigenère Decode - CyberChef](https://cyberchef.org/#recipe=Vigen%C3%A8re_Decode('flag'))
[Vigenere Solver | guballa.de](https://www.guballa.de/vigenere-solver)
