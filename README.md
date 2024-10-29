# Chef en Casa 🍲

Chef en Casa es una aplicación de recetas gourmet que permite a los usuarios explorar, guardar y organizar recetas. Con una interfaz intuitiva y personalizada, los usuarios pueden buscar recetas, agregar sus favoritas, escribir notas personalizadas y planificar su menú semanal.

## Tabla de Contenidos
- [Funcionalidades](#funcionalidades)
- [Tecnologías](#tecnologías)
- [Instalación](#instalación)
- [Estructura del Proyecto](#estructura-del-proyecto)
- [Equipo de Desarrollo](#contacto)

## Funcionalidades
- **Buscar y Visualizar Recetas**: Búsqueda de recetas a través de la API de Spoonacular.
- **Guardar Favoritos**: Los usuarios pueden agregar recetas a su lista de favoritas para acceso rápido.
- **Añadir Notas Personalizadas**: Permite que cada usuario escriba notas personales en cada receta.
- **Organización del Menú Semanal**: Los usuarios pueden planificar sus comidas diarias para almuerzo y cena.

## Tecnologías
- **Frontend**: HTML, CSS, JavaScript, React
- **Backend**: Python, Flask, SQLAlchemy
- **Gestión de Estado**: Flux
- **API Externa**: Spoonacular API
- **Base de Datos**: Postgress para desarrollo, y SQLAlchemy ORM



### 1) Installation:

> If you use Github Codespaces (recommended) or Gitpod this template will already come with Python, Node and the Posgres Database installed. If you are working locally make sure to install Python 3.10, Node 

It is recomended to install the backend first, make sure you have Python 3.8, Pipenv and a database engine (Posgress recomended)

1. Install the python packages: `$ pipenv install`
2. Create a .env file based on the .env.example: `$ cp .env.example .env`
3. Install your database engine and create your database, depending on your database you have to create a DATABASE_URL variable with one of the possible values, make sure you replace the valudes with your database information:

| Engine    | DATABASE_URL                                        |
| --------- | --------------------------------------------------- |
| SQLite    | sqlite:////test.db                                  |
| MySQL     | mysql://username:password@localhost:port/example    |
| Postgress | postgres://username:password@localhost:5432/example |

4. Migrate the migrations: `$ pipenv run migrate` (skip if you have not made changes to the models on the `./src/api/models.py`)
5. Run the migrations: `$ pipenv run upgrade`
6. Run the application: `$ pipenv run start`

> Note: Codespaces users can connect to psql by typing: `psql -h localhost -U gitpod example`

### Undo a migration

You are also able to undo a migration by running

```sh
$ pipenv run downgrade
```

### Backend Populate Table Users

To insert test users in the database execute the following command:

```sh
$ flask insert-test-users 5
```

And you will see the following message:

```
  Creating test users
  test_user1@test.com created.
  test_user2@test.com created.
  test_user3@test.com created.
  test_user4@test.com created.
  test_user5@test.com created.
  Users created successfully!
```

### **Important note for the database and the data inside it**

Every Github codespace environment will have **its own database**, so if you're working with more people eveyone will have a different database and different records inside it. This data **will be lost**, so don't spend too much time manually creating records for testing, instead, you can automate adding records to your database by editing ```commands.py``` file inside ```/src/api``` folder. Edit line 32 function ```insert_test_data``` to insert the data according to your model (use the function ```insert_test_users``` above as an example). Then, all you need to do is run ```pipenv run insert-test-data```.

### Front-End Manual Installation:

-   Make sure you are using node version 14+ and that you have already successfully installed and runned the backend.

1. Install the packages: `$ npm install`
2. Start coding! start the webpack dev server `$ npm run start`

## Estructura del Proyecto 

## Estructura del Proyecto

```plaintext
proyectoFinal-ChefenCasa/
├── app.py                    # Archivo principal de la aplicación Flask
├── config.py                 # Configuración de la aplicación
├── models/                   # Modelos de SQLAlchemy
│   ├── user.py
│   ├── recetas.py
│   └── favoritos.py
├── routes/                   # Rutas de la API
│   ├── auth.py
│   ├── recetas.py
│   └── favoritos.py
├── static/                   # Archivos estáticos (CSS, JS, imágenes)
├── templates/                # Plantillas HTML
├── .env                      # Variables de entorno
├── requirements.txt          # Dependencias de Python
└── README.md                 # Documentación del proyecto


## Equipo de Desarrollo

- **Natalia Iacono** - Desarrolladora Full Stack  
- **Alejandra Aguirre** - Desarrolladora Full Stack  
- **Carlos Molina** - Desarrollador Full Stack
 

