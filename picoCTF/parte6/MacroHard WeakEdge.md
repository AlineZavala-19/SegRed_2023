### MacroHard WeakEdge
## Objetivo
I've hidden a flag in this file. Can you find it? [Forensics is fun.pptm](https://mercury.picoctf.net/static/3944a59474f9f676942282c50b9c3675/Forensics%20is%20fun.pptm)
## Datos de acceso al nivel
## Solución
Extraer la presentación de PowerPoint como un archivo ZIP.
Mirando a través de los archivos extraídos, parece sospechoso ppt/slideMasters/hidden
`cat ppt/slideMasters/hidden``Z m x h Z z o g c G l j b 0 N U R n t E M W R f d V 9 r b j B 3 X 3 B w d H N f c l 9 6 M X A 1 f Q`
Lo metemos al CyberChef
Flag --> picoCTF{D1d_u_kn0w_ppts_r_z1p5}`
## Notas adicionales
Los archivos de PowerPoint son en realidad ZIP: `unzip Forensics\ is\ fun.pptm`
## Referencias
