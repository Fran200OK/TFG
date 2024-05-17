El módulo RTP funciona junto con la herramienta de ProcesaConexiones.
Por motivos de Copyright no estoy habilitado para subir dicha herramienta.

En el caso de que se quiera utilizar, contactar con Daniel Morató Osés (https://www.tlm.unavarra.es/~daniel/).

Una vez que se disponga de la herramienta de ProcesaConexiones (en mi caso usé la versión 2.3.0), se debe añadir
el fichero moduleRTPAppLevel.c a la carpeta "src" de ProcesaConexiones.

Para compilar el módulo hay que seguir los siguientes pasos:

-1. Abrir la Terminal y ubicarnos en el fichero "src".

-2. Compilar: gcc -shared -fPIC -Wall -g -pedantic -O3 -std=c99 -D_GNU_SOURCE -o moduleRTPAppLevel.so moduleRTPAppLevel.c

-3. Ejecutar: ./procesaConexiones --loadModule ./moduleRTPAppLevel.so --appLevelProtosUDP moduleRTPAppLevel --inputFile traza.pcap >salida.txt

La traza que queramos analizar tiene que ubicarse también en el fichero "src" con el nombre "traza.pcap". Posteriormente, se nos generará un fichero 
de salida em formato txt con los resultados obtenidos por el módulo RTP junto con los de ProcesaConexiones.
