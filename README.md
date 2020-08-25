# Visit Management

sitio web de administracion de visitas para el ITCHII

## Prerequisitos

Tienes que tener previamente instalado

[Python3](www.python.org)

```bash
Pip

curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
```

```bash
Flask 

pip3 install flask
```

```bash
Flask-Sqlalchemy

pip3 install flask-sqlalchemy
```

```bash
Flask-Bcrypt 

pip3 install Flask-Bcrypt
```

```bash
Flask-login

pip3 install flask-login
```

```bash
Flask-mail

pip3 install Flask-Mail
```

```bash
Flask-wtf

pip3 install Flask-WTF
```

```bash
Email_Validator

pip3 install email-validator
```

```bash
Pillow

pip3 install Pillow
```

```bash
MySQL-python

pip3 install mysql-python
pip3 install mysqlclient
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
