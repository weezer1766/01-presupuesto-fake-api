# JSON-SERVER: MOCKS BASE DE DATOS
https://www.npmjs.com/package/json-server	
	
## CREAR UN FAKE API DATABASE CON JSON-SERVER
	
https://www.youtube.com/watch?v=1zkgdLZEdwM
https://github.com/mehmetyilmaz001/fake-product-api-json-server --> EJEMPLO
		
## PUBLICAR UN FAKE API DATABASE CON JSON-SERVER EN HEROKU
https://www.youtube.com/watch?v=jAnJCsQDyXk
https://github.com/mehmetyilmaz001/fake-product-api-json-server --> EJEMPLO
https://github.com/jesperorb/json-server-heroku

## PASOS PARA CREAR EL FAKE API DATABASE
1. Abrimos el VS Code y abrimos una carpeta vacia con solo la base de datos
```db.json``` que previamente debe haber sido elaborada en formato json.
Notece que debe tener este nombre

2. Inicializamos el npm en el proyecto con la finalidad de que cree el archivo
package.json, ejecutamos el siguiente comando:
```npm init```

Cuando nos pida un entry point, debemos cambiar el nombre a ```server.js```, 
archivo que HEROKU necesitara como parte de su configuración.

3. Instalamos en el proyecto el paquete json-server, ejecutamos el siguiente 
comando:
```npm install -g json-server```

4. Luego agregamos el archivo server.js y agregamos la siguiente configuración:
```const data = require("./db.json");```

```const jsonServer = require("json-server");```
```const server = jsonServer.create();```
```const router = jsonServer.router(data);```
```const middlewares = jsonServer.defaults();```
```const port = process.env.PORT || 3000;```

```server.use(middlewares);```
```server.use(router);```

```server.listen(port);```

5. En el package json, en la sección de scripts debe agregarse el comando start
con la siguiente configuración: 

```"main": "server.js",```
```"scripts": {```
```     "start": "node server.js"```
```},```

6. A continuación debemos crear un nuevo repositorio en GITHUB y debemos subir
nuestro proyecto, para este ejemplo por ejemplo se creo el siguiente repositorio:

```https://github.com/weezer1766/01-presupuesto-fake-api.git```

7. Creamos una cuenta en Heroku, aceptamos los terminos y a continuación damos 
clic en el botón "New", ingresamos el nombre del nuevo app a deployar y la región,

https://dashboard.heroku.com/apps
https://dashboard.heroku.com/new-app

8. Una vez dentro debemos seleccionar "Deployment method" y seleccinamos la opción,
"GitHub", a continuación buscamos nuestro repositorio y seleccinamos la opción "Deploy"

9. La respuesta debe ser algo como esto:

Congrats!
You're successfully running JSON Server
✧*｡٩(ˊᗜˋ*)و✧*｡

Resources
/tipomovimiento 2x
/movimiento 5x
To access and modify resources, you can use any HTTP method:

GET POST PUT PATCH DELETE OPTIONS

undefined
Documentation
README