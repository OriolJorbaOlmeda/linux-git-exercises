1. Para crear el proyecto, creo una carpeta que se va a llamar project con mkdir project y entro dentro esa carpeta con cd project. En la git bash primero se ecribe git init, para vincular ese proyecto con git como se puede ver en la (Imagen_3.png).

2. Para poder ignorar todos los ficheros .sh, hay que crear un fichero .gitignore. Una vez este creado este fichero, en escribiremos lo que se puede ver en la (Imagen_4.png). Como se puede ver, en el fichero decimos que ignore todos los ficheros con extensión .sh.

3. A continuación crearé dos ficheros nuevos con las intrucciones code demo1.txt y code demo2.txt. Code és el editor de texto que estoy utilizando, también se puede utilizar touch, que lo único que hace es crear el fichero. Como podemos ver en la (Imagen_5.png), se han creado los dos ficheros. A continuación, para añadirlos en el stage area debemos debemos utilizar el comando git add demo1.txt demo2.txt. Esto lo que hará és passar esos ficheros de untracked a tracked. Es decir, los pasará al stage area. Una vez aplicado ese comando, veremos que los ficheros ya no estan untracked (Imagen_6.png).

4. El siguiente paso es añadir el contenido al fichero demo1.txt. Lo haré con la instrucción echo "primer cambio" >> demo1.txt. De esta forma añado el cambio directamente des de consola. Si me dirijo al fichero demo1.txt, se podrá ver el cambió (Imagen_7.png). Como se puede ver en la barra de encima, ahora el fichero aparece como modificado, así que tendremos que volver a aplicar git add, ya que lo que se guarda en el stage area es el estado en el que se habia hecho el add, no se guarda el modificado. Una vez modificado y añadido de nuevo, se debe aplicar el commit con git commit -m "Modified demo1.txt". Como se puede ver en la (Imagen_8.png), se ha realizado el commit correctamente.

5. En este paso, hay que hacer los mismo que en el anterior, pero añadiendo un commit con información erronea. Haré el mismo proceso que en el anterior, pero con el commit erroneo.

6. Como en el paso anterior hemos escrito mal el commit, deveremos rectificarlo. Para ello utilizaremos git commit --amend. Se no abrirá un editor de texto, donde podremos cambiar el nombre del fichero, como podemos ver en la (Imagen_9.png). Solo hace falta cambiar el nombre a demo2.txt y se resuelve el problema. Como podemos ver en la (Imagen_10.png), el texto del commit se ha modificado.

7. El siguiente paso es crear una nueva rama develop. Para crear una nueva rama hay que unilizar el comando git branch.
   En nuestro caso será git branch develop. Para acceder a la rama, utilizaremos el comando git checkout. Como se puede ver en la (Imagen_11.png), ha cambiado de rama de master a develop. A continuación creamos el fichero script.sh con touch y le añadimos el txto que se puede ver en la (Imagen_12.png).

8. Para darle permisos de ejecución, deberemos utilizar el comando chmod +x scrip.sh, de esta forma tendrá esos permisos. Finalmente, con los permisos ya concedido. Hacemos un add y commit de este fichero en la ramam develop. Para que nos deje añadirlo, hay que poner git add -f, ya que filtra todos los ficheros .sh.

9. Ahora falta hacer un merge de develop a master. Para ello, primero debemos dirigirnos a master. Una vez en master, haremos un git merge develop. Veremos que los ficheros se han añadido. En mi caso, me he olvidado de hacer el add y commit de .gitignore en master, pero lo he hecho en develop sin darme cuenta, aunque funciona igual. Se puede ver el resultado del merge en la (Imagen_12.png).

10. Finalmente, se tendrá que subir el repositorio a remoto. Para hacerlo hay que entrar a github y crear un nuveo proyecto. Una vez creado, nos darà un link el qual debemos copiar. Una vez copiado, aplicamos el comando git remote add origin https://github.com/OriolJorbaOlmeda/Proyecto.git, el cual a a vincular nuestro repositorio con el remoto. Después aplicamos un push, para subir todos los ficheros al remoto con git push -u origin master. En las (Imagen_13.png) se puede ver el proceso.
    Finalmente, en la (Imagen_14.png), podemos ver como queda el repositorio remoto.
    El link del repositorio remoto es: https://github.com/OriolJorbaOlmeda/Proyecto
