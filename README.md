# ttlkn_backend
A base API architecture for tutelkan


# 1.- crear el repositorio vacío en github, y luego clonar
# 2.- crear el package.json del proyecto a travéz de npm init con la siguiente información
 - Package name: api_sigma (respetando lower case)
 - Versión: 1.0.0
 - Descripción: Arquitectura base para apis de tutelkan
 - Entry Point: index.js
 - Test Command: (vacío por el momento)
 - Git Repository: https://github.com/RodGonzalez760/ttlkn_backend.git (aparece automaticamente al ser clonado)
 - KeyWords: api arquitectura base tutelkan
 - Autor: Rodrigo González
 - Licence: ISC (por defecto)
  
  Esto crea el archivo package.json

# 3.- instalar las dependencias
 - express:
 - express-async-errors: middleware que ayuda a controlar las excepciones asincronas
 - awilix: container para realizar injección de dependencias
 - cors: configuración de peticiones desde el exterior hasta nuestra api
 - compression: ayuda a comprimir las peticiones http
 - helmet: con este solo paquete estamos librando nuestra api de algunos ataques
 - bcrypt: para encriptar las contraseñas
 - jsonwebtoken: para generar tokens
 - memory-cache: aplica el principio de caching de restful, haciendo un caching en memoria
 - mongoose o sequelize: ODM - ORM para la base de datos a utilizar
 - swagger-ui-express: para documentar la api
 ** ya se usan en tutelkan:
    -backpack-core: (muestra 6 vulnerabilidades 4 medias, 2 altas, no se solucionan con npm audit fix) (por el momento no instalado)
        *busco reemplazar por webpack, npm i --save-dev webpack webpack-cli (por el momento no instalado)
    -bcryptjs
    -body-parser
    -core-js
    -cron
    -crypto-js
    -dotenv
    -morgan
    -mssql, mysql, oracledb
    -multer
    -node-excel-export: (muestra 1 vulnerabilidad media, no se soluciona con npm audit fix)
    -nodemailer
    -socket.io

# 4.- Crear el archivo .gitignore en la raíz del proyecto para los siguientes directorios:
 - node_modules

# 5.- Instalar las dependencias de desarrollo:
- dotenv: configuración de las variables de entorno
- jest: testing
- *opcional, nodemon (por el momento Instalado), mockingoose

# 6.- Creo los scripts en package.json
    "start": "node index.js"    **PARA PRODUCCIÓ**
    "dev": "nodemon index.js"   **PARA DESARROLLO**

    **Para usar backpack: 
            "dev": "backpack dev --inspect=0.0.0.0:9229",
            "build": "backpack build",

# 7.- Creamos la arquitectura de N capas
 -tests
 -src
  -controllers
  -models
  -services
  -repositories
  -middlewares
  -routes
  -helpers
  -startup

    *para todos los directorios crear un index.js para exponer los componentes