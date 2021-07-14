# Ironhack - Basketball

## Deployment

Para realizar un despliegue en Heroku es importante:

- Contar con una cuenta en HEROKU.COM
- Crear una aplicación nueva dentro de HEROKU.COM
- Verificar que tenemos instalado HEROKU CLI en local (en la computadora).
- Realizar la conexión remota con:

```shell
heroku git:remote -a [NOMBRE DEL PROYECTO]
```

- Empujamos desde terminal en local:
```shell
git push heroku master
```

- En caso de fallo, revisar debugging:

```shell
heroku logs --tail
```



## Errores comunes

### `nodemon not found``

Establecer dentro de los scripts uno de desarrollo (dev) y uno de producción (start):

```json
...
"scripts": {
    "start": "node index.js",
    "dev": "nodemon index.js",
    "test": "echo \"Error: no test specified\" && exit 1"
},
...
```


### Se obtiene un error de puerto

- Instalar dotenv

```shell
npm install dotenv
```

- Dentro de `index.js`, invocamos la librería como middleware:

```javascript
/**
 * 2. MIDDLEWARES
 */

require('dotenv').config()

```

- Creamos un archivo `.env`, vacío en ese momento dentro de nuestra estructura de carpetas.

- Establecimos el puerto con proccess.env.PORT en la llamada del servidor:

```javascript
app.listen(process.env.PORT || 3004, () => {
    console.log("Estoy en el puerto 3004")
})
```












