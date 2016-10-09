Respuestas ejercicio 1


11) He usado el comando git reset --hard HEAD~1  porque lo qeu queremos hacer es deshacer el ultimo commit, por lo que al hacer el reset,
apuntamos el puntero de la rama Styled a donde apunta el puntero HEAD menos una posicion ,es decir,  al primer commit donde creamos el archivo
y usamos la opcion --hard para que el cambio afecte tanto al stating area como al working copy


12) He usado los siguientes comandos: primero el git reflog puesto que hemos hecho un reset --hard en el anterior comando lo que supone que  en el working copy
 no tenemos tampoco las ultimas modificaciones y con esto obtendremos la referencia del commit previo y despues, con la misma operacion  que la anterior
  git reset --hard cb15597 pondremos de nuevo el puntero styled al commit perdido


13)No da conflicto, puesto que la rama styled es la que absorbe a master , en la rama styled tiene los ultimos cambios es decir lo que hay en el archivo de la 
rama master mas los cambios del ultimo commit hechos en la propia rama styled


19) Si que da conflicto, hemos creado la rama htmlfy a partir de master con lo cual ya parte de que no tiene los ultimos cambiso de la rama styled y ademas 
luego en la propia rama htmlfy hemos modificado el archivo de nuevo haciendo un nuevo commit, con lo cual al hacer un merge hay dos  y git nos pide que resolvamos
el conflicto antes de hacer el ultimo commit (en este caso nos quedamos con lo que habia en la rama styled editando el archivo y borrando los cambios anadidos
por la rama htmlify en el merge) y despues hacemos el nuevo commit para terminar con ell estado modo conflicto del git


21) En este caso como nos hemos quedado en el conflicto anterior con lo que habia en la rama styled , rama que en otras palabras contiene los cambios de master
mas los ultimos cambios recientes y  al ser la rama master la que absorve lo que se hace es un fast forward automatico, actualizando el puntero master a donde 
apunta el puntero styled es decir a los ultimos cambios por lo que no hay conflicto posible

25)En este caso use el comando git log --graph --decorate, de este modo  puedo ver el grafo y los punteros de los commits el prettyonline no lo he usado
primero porque habia pocos commits que ver y despues porque verlo tan junto no  lo veo bien :)


26)Si  podria ser un forward porque no perderiamos cambios , el puntero de la rama title apunta al archivo con titulo,al ultimo commit y la rama master
esta apuntando al commit justo previo por tanto como es la rama master la que absorbe  supone actualizar la posicion del puntero con el contenido de la rama
title pero   al contrario si que no podria hacerse porque perderiamos cambios


27)  He usado el comando git reset HEAD~1 , lo mismo que en el caso del 11) solo que no ponemos el comando con la opcion --hard para que el working copy no se
actualice y no perdamos los cambios

28) En este punto el archivo que tenemos en el stating area esta retrocedido , es decir sin el titulo, sin embargo en el working copy si que 
tenemos los ultimos cambios, es decir el archivo con titulo, si hacemos un diff te dice que efectivamente al staging area le falta el titulo, entonces  para alinear
el contenido de ambos areas he usado el comando git reset --hard  HEAD

29)He usado el comando git branch -D title como estoy en la rama master no me ha dado problema

30) En este punto hemos dejado descolgados los ultimos commits, puesto que hemos movido el puntero master y encima hemos borrado la rama title, por lo que la unica
manera de recuperarlos es hacerlo como el paso 12 con un reflog y posicionarnos en la referencia el commit del merge

32)y 33) he usado el mismo comando en ambos git reset --hard a las referencias dadas por el reflog del commit inicial y del commit del merge con la rama title      
