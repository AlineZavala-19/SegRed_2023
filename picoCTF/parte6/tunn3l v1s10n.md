### tunn3l v1s10n
## Objetivo
We found this [file](https://mercury.picoctf.net/static/09a86202e72dbdb5bf4d1b5d2c6a5b86/tunn3l_v1s10n). Recover the flag.
## Hints
1. Weird that it won't display right...
## Datos de acceso al nivel
## Solución
Podemos cambiar la altura del mapa de bits usando un editor hexadecimal. El ancho comienza en el desplazamiento hexadecimal `12`, dura 4 bytes y es seguido por la altura en el desplazamiento `16`, que también es de 4 bytes. 
Establecemos la altura en el mismo número que la anchura (`6e 04`) ya que la imagen parece que parte de ella se extendió hacia fuera. Hacemos el cambio en el editor hexadecimal reemplazando `32 01` en el desplazamiento `16` a `6e 04`, guardamos la imagen y luego la abrimos.
picoCTF{qu1t3_a_v13w_2020}
## Notas adicionales
## Referencias

