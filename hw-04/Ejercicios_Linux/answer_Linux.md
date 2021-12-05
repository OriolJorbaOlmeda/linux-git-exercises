Ejercicio 1: Para este ejercicio voy a utilizar una imagen de Ubuntu (Se puede ver en el Dockerfile), la cual haré correr con docker.

Una vez la imagen de Ubuntu esté corriendo, ya se nos habrirá directamente en la carpeta Entrega-Oriol, creada en el Dockerfile, la qual ya tendrá el fichero nginx_logs_examples.log dentro.

El comando para conseguir el objetivo es el siguiente:

grep -oE "\b([0-9]{1,3}\.){3}[0-9]{1,3}\b" nginx_logs_examples.log | sort -rn | uniq -c >> nginx_requests_total.txt

Lo que he hecho es inicialmente ejecutar un grep el qual separe las IPs del resto. Esto lo hace buscando todas las partes del fichero nginx_logs_examples.log que cumplan la siguiente exresion: \b([0-9]{1,3}\.){3}[0-9]{1,3}\b. Con el simbolo '|' inidcamos que comando se ejecuta a continuación, el cual és el sort -rn. Este nos ordenará las IPs de mas grande a más pequeña. Sin el -rn nos pasaría que se ordenarian segun el primer numero de la IP. Con el -rn nos aseguramos que lo hace por todo. Finalmente le uniq -c, nos agrupa las IDs por numero y nos da el número total de cada una. Todo esto se guarda en el fichero nginx_requests_total.txt gracias al comando '>>', el cual gurada toda la información filtrada anteriormente, en este fichero.
El resultado se puede ver en el fichero nginx_requests_total.txt.

Ejercicio 2: Para realizar este ejercicio, inicialmente hay que crear un fichero script.sh el cual nos va a permitir poder ejecutar los requisitos pedidos. Para ello creamos el fichero con:
nano script.sh Nano es el editor de texto y script.sh el nombre que le he dado a ese fichero.
Una vez dentro del fichero se escribe el código que se puede ver en la (Imagen_1.png). He creado las diferentes variables necesarias para hacer el código vas ameno. Con el primer if, compruebo que el directorio DIR no exista, para poder crearlo. Una vez creado, miro si el dia de la ejecución és domingo o no. Si lo es, creo una carpeta en el direcotrio DIR donde pongo ese mismo fichero. No he conseguido poner ficheros de otras fechas, así que solo me aparece un fichero .log. Una vez este fichero esta dentro de esa carpeta, la convierto en .tar.gz y depúes elimino esa carpeta extra.
Para ejecutar el fichero sript.sh debemos utilitzar: bash script.sh. Este crearà las carpetas y en la del dia actual copiarà el fichero .log
Como se puede ver en la (Imagen_2.png), se ha creado la copia del fichero .log, y a más al ser domingo, se ha creado el fichero .tar.gz. Si aplicamos tar -xvf fichero.tar.gz lo podremos descomprimir y veremos el fichero

Ejercicio 3: Para crear un contrab utilizando el script del ejercicio anterior, primero debemos entrar en el propio contrab con: contrab -e
Una vez dentro escribiremos el comando para que esa acción se realize, la cual es la siguiente:
59 23 \* \* \* bash /Entrega-Oriol/ script.sh
le decimos que se ejecute cada dia del año a las 23:59, el fichero que se debe ejecutar es /Entrega-Oriol/script.sh con el comando bash.
