# Visit Management

sitio web de administracion de visitas para el ITCHII

## Prerequisitos

Tienes que tener previamente instalado

[Python 3.7](www.python.org)

```bash
Pip

curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
```

## Requerimientos

#### Estando en la ruta raiz del proyecto

```bash
Instalar Requerimientos

pip3 install -r requirements.txt
```

## Correr el proyecto
Modificar en el archivo `config.py` la variable ` SQLALCHEMY_DATABASE_URI`, el usuario y la contraseña.
`{os.environ.get("DB_USER")}` y `{os.environ.get("DB_PASS")}` respectivamente.

Crear una base de datos en `MySQL` llamada `proyecto_visitas`. 

En la raiz del proyecto correr el CLI de python3 `python3` e ingresar el siguiente codigo
`from flask_visitas import db` damos enter y luego ingresamos `db.create_all()`.

En el archivo `servicio.sql` se encuntran usuarios creados manualmente para testeo. Debe correrlos
manualmente en MySQL.

Siguiente solo es correr el proyecto: `python3 run.py`

## Previews
![alt text](https://github.com/DavidBanda/Flask-ITCHII/blob/master/prevs/pw-1.png)

![alt text](https://github.com/DavidBanda/Flask-ITCHII/blob/master/prevs/pw-2.png)

![alt text](https://github.com/DavidBanda/Flask-ITCHII/blob/master/prevs/pw-3.png)

![alt text](https://github.com/DavidBanda/Flask-ITCHII/blob/master/prevs/pw-4.png)

![alt text](https://github.com/DavidBanda/Flask-ITCHII/blob/master/prevs/pw-5.png)

![alt text](https://github.com/DavidBanda/Flask-ITCHII/blob/master/prevs/pw-6.png)

![alt text](https://github.com/DavidBanda/Flask-ITCHII/blob/master/prevs/pw-7.png)

## Estructura del proyecto
La configuración del proyecto esta dentro de flask_visitas/__init__.py. En este archivo se configura:
1. La base de datos mediante **SQLAlchemy**, que es un ORM para MySQL.
2. BCrypt, para el cifrado de contraseñas.
3. Mail, para el envio de correos electronicos.
4. LoginManager, una libreria de Flask para manejar el inicio de sesión.
4. Rutas. Estas son las direcciones a las que se pueden acceder en la aplicacion web. Cada conjunto de rutas estan en archivos separados llamados BluePrints. 

Cada conjunto de rutas esta en su propia carpeta. En este caso, hay dos conjuntos de rutas: usuarios y solicitudes. Usuarios contiene paginas para la informacion de los usuarios,así como login, registro, etc. Solicitues se encarga del proceso de generacion de solicitudes para las visitas. Las carptas de las rutas tienen la siguente estructura:
- usuarios
    - choices: contiene categorias para elegir como tuplas
    - dict_choices: contiene las mismas categoras, pero en formas de diccionarios
    - forms: las formas son objectos tipo FlaskForm que renderizan automaticamente un formulario HTML
    - models: son objetos tipo SQLAlchemy.Model. Estos sirven para insertar y leer registros desde la base de datos sin tener que escribir querys.
    - routes: En este archivo es donde estan las rutas de la aplicación. Toda la logica tambien esta implementada en estas rutas
    - utils: Funciones utiles para todo el conjunto de rutas
    - __ init __

El login es gestionado usando _login_user_ de la libreria _flask_login_. Y todas las contraseñas que se guardan son encriptadas por _bcrypt.generate_password_hash_

### Templates
Esta aplicacion móvil regresa HTML. Todos los HTML que se renderizan se encuentran en la carpeta de _templates_, y están escritps en jinja2

Es importante saber que la aplicacion no se ejecuta desde flask_visitas/__init__.py, aquí solo se crea la instancia de la aplicación. La aplicacion se inicia en run.py, usando la instancia creada en flask_visitas/__init__.py. 

En run se indica que se puede solicitar la aplicación desde cualquier dirección IP (indicado con el 0.0.0.0) y se indica si la aplicación es debbugeable o no. (Al momento de deployearse en producción es importante hacerla no debuggeable)

