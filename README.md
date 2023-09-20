* Creamos un entorno virtual y lo activamos con los siguientes comandos

python -m virtualenv venv
.\venv\Scripts\activate 

* Instalamos django
pip install djang

* Comenzamos el proyecto con el comando

django-admin start project django_crud_api

*y nuestra app
python manage.py startapp tasks

*migramos las tablas de task con

python manage.py migrate

* Instalamos el rest framework
pip install djangorestframework

* para luego autorizar a la coneccion de puertos entre front y back instalamos
pip install django-cors-headers

* Agregamos en django_crud_api/settings.py en INSTALLED_APPS
'corsheaders',
    'rest_framework',
    'tasks',

* Y en MIDDLEWARE, antes de CommonMiddleware
'corsheaders.middleware.CorsMiddleware',

* Agrego los permisos de cors a settings.py que luego añadiremos cuando trabajemos con el front

CORS_ALLOWED_ORIGINS = [
    
]

* Realizamos las migraciones luego de crear los modelos con
python manage.py makemigrations 
python manage.py migrate tasks

* creamos un usuario para acceder al panel de admin de django en  url/admin con

python manage.py createsuperuser

* para documentar la api instalamos coreapi: 
pip install coreapi

* hacemos los cambios con Legacy CoreAPI Schemas Docs  https://www.django-rest-framework.org/coreapi/ y asi podremos ver
todo documentado en localhost:8000/tasks/docs/

* Comenzamos a instalar react
npm create vite           - seleccionamos React con JS seteando el nombre del proyecto como client

*en  cd client


npm install
npm i react-router-dom react-hot-toast axios react-hook-form