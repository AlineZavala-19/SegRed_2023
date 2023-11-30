### St3g0
## Objetivo
Download this image and find the flag.

- [Download image](https://artifacts.picoctf.net/c/217/pico.flag.png)
## Hints
1. We know the end sequence of the message will be `$t3g0`.
## Datos de acceso al nivel
## Solución
```bash
┌──(kali㉿kali)-[~/SEGURIDAD7A]
└─$ wget https://artifacts.picoctf.net/c/217/pico.flag.png
--2023-11-05 00:21:59--  https://artifacts.picoctf.net/c/217/pico.flag.png
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.160.124.108, 18.160.124.119, 18.160.124.34, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.160.124.108|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 13443 (13K) [application/octet-stream]
Saving to: ‘pico.flag.png’

pico.flag.png                 100%[===============================================>]  13.13K  --.-KB/s    in 0.006s  

2023-11-05 00:22:14 (2.19 MB/s) - ‘pico.flag.png’ saved [13443/13443]

                                                                                                                      
┌──(kali㉿kali)-[~/SEGURIDAD7A]
└─$ sudo apt install ruby
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
ruby is already the newest version (1:3.1).
ruby set to manually installed.
The following packages were automatically installed and are no longer required:
  gcc-12-base libarmadillo11 libcodec2-1.1 libgcc-12-dev libgfapi0 libgfrpc0 libgfxdr0 libglusterfs0
  libgupnp-igd-1.0-4 libjim0.81 libnfs13 libobjc-12-dev libstdc++-12-dev python3-jdcal
Use 'sudo apt autoremove' to remove them.
0 upgraded, 0 newly installed, 0 to remove and 0 not upgraded.
                                                                                                                      
┌──(kali㉿kali)-[~/SEGURIDAD7A]
└─$ sudo gem install zsteg

Fetching zsteg-0.2.13.gem
Fetching rainbow-3.1.1.gem
Fetching iostruct-0.0.5.gem
Fetching zpng-0.4.5.gem
Successfully installed rainbow-3.1.1
Successfully installed zpng-0.4.5
Successfully installed iostruct-0.0.5
Successfully installed zsteg-0.2.13
Parsing documentation for rainbow-3.1.1
Installing ri documentation for rainbow-3.1.1
Parsing documentation for zpng-0.4.5
Installing ri documentation for zpng-0.4.5
Parsing documentation for iostruct-0.0.5
Installing ri documentation for iostruct-0.0.5
Parsing documentation for zsteg-0.2.13
Installing ri documentation for zsteg-0.2.13
Done installing documentation for rainbow, zpng, iostruct, zsteg after 1 seconds
4 gems installed
                                                                                                                      
┌──(kali㉿kali)-[~/SEGURIDAD7A]
└─$ zsteg -h
Usage: zsteg [options] filename.png [param_string]

    -a, --all                        try all known methods
    -E, --extract NAME               extract specified payload, NAME is like '1b,rgb,lsb'

Iteration/extraction params:
    -o, --order X                    pixel iteration order (default: 'auto')
                                     valid values: ALL,xy,yx,XY,YX,xY,Xy,bY,...
    -c, --channels X                 channels (R/G/B/A) or any combination, comma separated
                                     valid values: r,g,b,a,rg,bgr,rgba,r3g2b3,...
    -b, --bits N                     number of bits, single int value or '1,3,5' or range '1-8'
                                     advanced: specify individual bits like '00001110' or '0x88'
        --lsb                        least significant bit comes first
        --msb                        most significant bit comes first
    -P, --prime                      analyze/extract only prime bytes/pixels
        --shift N                    prepend N zero bits
        --invert                     invert bits (XOR 0xff)
        --pixel-align                pixel-align hidden data

Analysis params:
    -l, --limit N                    limit bytes checked, 0 = no limit (default: 256)

        --[no-]file                  use 'file' command to detect data type (default: YES)
        --no-strings                 disable ASCII strings finding (default: enabled)
    -s, --strings X                  ASCII strings find mode: first, all, longest, none
                                     (default: first)
    -n, --min-str-len X              minimum string length (default: 8)

    -v, --verbose                    Run verbosely (can be used multiple times)
    -q, --quiet                      Silent any warnings (can be used multiple times)
    -C, --[no-]color                 Force (or disable) color output (default: auto)

PARAMS SHORTCUT
        zsteg fname.png 2b,b,lsb,xy  ==>  --bits 2 --channel b --lsb --order xy
                                                                                                                      
┌──(kali㉿kali)-[~/SEGURIDAD7A]
└─$ zsteg pico.flag.png
b1,r,lsb,xy         .. text: "~__B>VG?G@"
b1,rgb,lsb,xy       .. text: "picoCTF{7h3r3_15_n0_5p00n_a9a181eb}$t3g0"
b1,abgr,lsb,xy      .. text: "E2A5q4E%uSA"
b2,b,lsb,xy         .. text: "AAPAAQTAAA"
b2,b,msb,xy         .. text: "HWUUUUUU"
b3,r,lsb,xy         .. file: gfxboot compiled html help file
b4,r,lsb,xy         .. file: Targa image data (16-273) 65536 x 4097 x 1 +4352 +4369 - 1-bit alpha - right "\021\020\001\001\021\021\001\001\021\021\001"                                                                                    
b4,g,lsb,xy         .. file: 0420 Alliant virtual executable not stripped
b4,b,lsb,xy         .. file: Targa image data - Map 272 x 17 x 16 +257 +272 - 1-bit alpha "\020\001\021\001\021\020\020\001\020\001\020\001"                                                                                                
b4,bgr,lsb,xy       .. file: Targa image data - Map 273 x 272 x 16 +1 +4113 - 1-bit alpha "\020\001\001\001"
b4,rgba,msb,xy      .. file: Applesoft BASIC program data, first line number 8

```
picoCTF{7h3r3_15_n0_5p00n_a9a181eb}
## Notas adicionales
## Referencias
