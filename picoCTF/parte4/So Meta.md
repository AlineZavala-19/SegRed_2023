### So Meta
## Objetivo
Find the flag in this [picture](https://jupiter.challenges.picoctf.org/static/89b371a46702a31aa9931a2a2b12f8bf/pico_img.png).
## Datos de acceso al nivel
## Solución
```bash
┌──(kali㉿kali)-[~]
└─$ wget 'https://jupiter.challenges.picoctf.org/static/89b371a46702a31aa9931a2a2b12f8bf/pico_img.png' 
--2023-10-16 12:50:03--  https://jupiter.challenges.picoctf.org/static/89b371a46702a31aa9931a2a2b12f8bf/pico_img.png
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 108795 (106K) [application/octet-stream]
Saving to: ‘pico_img.png’

pico_img.png        100%[=================>] 106.25K   131KB/s    in 0.8s    

2023-10-16 12:50:13 (131 KB/s) - ‘pico_img.png’ saved [108795/108795]

                                                                              
┌──(kali㉿kali)-[~]
└─$ exiftool pico_img.png                           
ExifTool Version Number         : 12.65
File Name                       : pico_img.png
Directory                       : .
File Size                       : 109 kB
File Modification Date/Time     : 2020:10:26 14:38:23-04:00
File Access Date/Time           : 2023:10:16 12:50:13-04:00
File Inode Change Date/Time     : 2023:10:16 12:50:13-04:00
File Permissions                : -rw-r--r--
File Type                       : PNG
File Type Extension             : png
MIME Type                       : image/png
Image Width                     : 600
Image Height                    : 600
Bit Depth                       : 8
Color Type                      : RGB
Compression                     : Deflate/Inflate
Filter                          : Adaptive
Interlace                       : Noninterlaced
Software                        : Adobe ImageReady
XMP Toolkit                     : Adobe XMP Core 5.3-c011 66.145661, 2012/02/06-14:56:27
Creator Tool                    : Adobe Photoshop CS6 (Windows)
Instance ID                     : xmp.iid:A5566E73B2B811E8BC7F9A4303DF1F9B
Document ID                     : xmp.did:A5566E74B2B811E8BC7F9A4303DF1F9B
Derived From Instance ID        : xmp.iid:A5566E71B2B811E8BC7F9A4303DF1F9B
Derived From Document ID        : xmp.did:A5566E72B2B811E8BC7F9A4303DF1F9B
Warning                         : [minor] Text/EXIF chunk(s) found after PNG IDAT (may be ignored by some readers)
Artist                          : picoCTF{s0_m3ta_eb36bf44}
Image Size                      : 600x600
Megapixels                      : 0.360

```
## Flag 
picoCTF{s0_m3ta_eb36bf44}
## Notas adicionales
Los metadatos son 
exiftool --> xiftool es una aplicación de línea de comandos y biblioteca Perl que le permite leer y escribir EXIF, GPS, IPTC, XMP, makernotes y otra información de metadatos en imagen, audio y video.
exiftool -Artist
## Referencias
https://www.exiftool.org/