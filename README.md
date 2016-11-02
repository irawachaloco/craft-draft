# craft-draft

# cc-catalogo v.1.0

El proyecto está desarrollado en Craft CMS https://craftcms.com/

Sin embargo, los carpetas centrales sobre las que corre el mismo CRAFT no se están versionando, asumiendo que habrá permanentes actualizaciones.

Este entorno es un proyecto con node.js que utiliza una herramienta (Dploy https://leanmeanfightingmachine.github.io/dploy/) para hacer ´deployments´ al ftp de manera automática.


#Sobre Craft CMS
Para correr el proyecto localmente es recomendable obtener la última versión de Craft y descargar la carpeta ´app´ en la siguiente ruta build/craft/. Idealmente, las actualizaciones sobre la app deberán existir de manera local y en el servidor, Craft se encarga de dicha actualización, por lo que es importante mantener todas los entornos actualizados.


#Configuración para proyecto base:

##A) Para un nuevo proyecto:
1.Crear un repositorio para albergar el proyecto: directorio raiz.

2.Se crea el package.json a través de la línea de comando con la instrucción


    npm init


Esto genera el archivo package.json, donde irán las configuraciones y dependencias de node.js.

3. En el archivo package.json se agregan los scripts para instalar Dploy y hacer deployments, ésta es la herramienta que hará los deployments. Seguir las intrucciones en https://leanmeanfightingmachine.github.io/dploy/.

4. Instalar Dploy en el proyecto a través del comando:


    npm install dploy --save


5. Una vez instalado Dploy se configura el archivo .yaml, el cual se genera a través de la instalación del mismo Dploy. En ese archivo (.yaml) se debe configurar el entrorno local y remoto. Algo parecido a esto:
    

    server_name:


    host: ftp.myserver.com


    user: user


    pass: password


    path:
        local: deploy/
        remote: public_html/


Una vez lista la configuración, se regresa al package.json para cambiar la configuracion del script para Dploy y se sustituye simplemente por:
    dploy
ó
    deploy <server_name>
Este comando hará el deploy a partir de la revisión de los últimos commits, es decir, subirá sólamente los cambios que estén versinados en los commits de git.

##B) Si el proyecto existe:
1. Clonar el repositorio de github.
2. Configurar los archivos en craft/config
3. Dentro del directorio raíz del proyecto se deben instalar las dependencias (generar node_modules) a través del comando:
    npm install
4. Configurar los archivo .yaml y listo!

=============================

En package.json en `scripts` van instrucciones (p.ej las cosas que van a operar)

Antes crear el proyecto en git
Luego local
Es importante el gitignore para NO VERSINAR node_modules (son enormes!!!)

Sobre el local:
para iniciar proyecto o package.json:

    npm init


para instalar stylus:

    npm install http-server --save


para instalar stylus:

    npm install stylus --save

para empezar a correr el proyecto en el servidor, sí sólo sí: script definido como `start`en el package.json

    npm start

En npm todo se corre con run, excepto npm start y npm test


Una vez que corro:

    npm run <nombre del script>

Todo lo que sea node o screipts los paras con:

    ctrl + c


Buscar tut de bash o shell   

Cuando bajo el proyecto de git, debo hacer:
pnm install 
//para instalar las dependencias que hay en el package.json y es cuando se crean node_modules