# FIX_MINIMIG_UnAMIGA_CORE
Mostramos como podemos mejorar la frecuencia de partida para el importante core Minimig-UnAMIGA

La placa CYC1000 tiene dos huellas, para montar dos osciladores el primer oscilador esta ya colocado y se trata de un oscilador no compensado en temperatura MEMS de 12Mhz colocada en el PIN_M2, cuando con este reloj se crea la descripción UnAMIGA se obtiene la siguente aproximación para el reloj PAL.

Aproximación de todos los UnAMIGA usando una CYCLONE IV = 28.522727Mhz

Escogí hace años la CYC1000 porque esta placa tiene incluso con lo diminuto de su tamaño una entrada de oscilador alternativa en el PIN_E15, actualmente la uso con el reloj correcto 28,37516Mhz que es la base de la implementacion de Dennis Van Weeren para crear su MiNIMIG.

Inciso sobre la placa actual (FPGAWARS APICULA) Tang Nano 20k:
Hace tiempo me puse en contacto con SiPEED y miembros de SiPEED estan en el grupo de trabajo, por lo que no ha sido casi ni necesario decir que si ya el PLL de una CYCLONE IV se agota "PLL para las cyclone IV es propiedad intelectual de Intel", se hacia tremendamente necesario partir de la mejor frecuencia posible para la primera FPGA de videojuegos la TANG NANO 20K, esta placa tiene un SI5351 que permite inyectar frencuencias muy exactas a la fpga gowin usada de segunda generación.
Esta fpga tiene un RISC-V de 400Mhz muy potente llamado BOUFFALO BL616, al que se le ha agregado la funcionalidad de manejar el SI5351, permitiendo en la práctica partir de relojes de sincria perfecta, y más aún si véis el esquema mejora aún más la situación de los relojes de partida dado que el SI5351 inyecta más de un reloj a la FPGA, aún así es cierto que tanto la fpga como el risc-v usan comparten el mismo reloj, pero el futuro es realmente esperanzador con la incorporación de un SI5351 tanto en el prototipo ATLAS como en la placa de desarrollo de videojuegos Tang nano 20k, que ya lo lleva incorporado.

El creador de MiMIG es actualmente un consultor en Paises Bajos:

https://www.xing.com/profile/Dennis_vanWeeren

FPGAWARS con chips de gowin:

https://github.com/YosysHQ/apicula

Esta vez y como será habitual en el 2024 es mejor un vídeo que se entienden mejor los objetivos.


[![HOW TO FIX UNAMIGA](https://img.youtube.com/vi/_fdW82qAI4Y/maxresdefault.jpg)](https://youtu.be/_fdW82qAI4Y)

Vengo a decir que somos afortunados en CYC1000 al disponer de 2 huellas con una libre para poner un SI5351, o mismamente un oscilador fijo PAL.
Y los que tengan una Tang Nano 20K, aún más afortunados por la elección del Bouffalo BL616 con su impresionante OTG, y lo útil a futuro de tener 2 integrados a mayores, un i2s mono de audio con una salida de audio realmente elevada, y un clon del SI5351 governado este generador de frecuencias desde el bus i2c del chip risc-v.
