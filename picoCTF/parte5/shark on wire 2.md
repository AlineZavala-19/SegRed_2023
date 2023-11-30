### shark on wire 2
## Objetivo
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recover the flag that was pilfered from the network.
## Datos de acceso al nivel
## Solución
El paquete de inicio tiene una dirección IP de 10.0.0.66. Le siguen más paquetes con esta misma dirección, hasta el paquete final. Vamos a filtrar solo los paquetes que provienen de esa dirección --> barra de filtros. A continuación, podemos ver más detalles sobre el transporte de estos paquetes marcando Ver resolución de --> nombre --> Resolver dirección de transporte. Luego vemos que en la información del paquete de cada paquete, hay un número de 4 dígitos en algún lugar que comienza con el número 5. Si luego tomamos los últimos 3 dígitos de cada número en el orden de los tiempos del paquete y los convertimos a ASCII, podemos obtener nuestra bandera. 
picoCTF{p1LLf3r3data_v1a_st3g0}
## Notas adicionales
ip.addr == 10.0.0.66
## Referencias
