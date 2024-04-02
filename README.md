## REQUISITOS DEL PROYECTO
## PHP v8.1
## Laravel v10.10
## Node js v18.20

## Instalar xampp
https://www.apachefriends.org/es/download_success.html
## Instalar composer
https://getcomposer.org/download/
seleccionar check de path
Todo siguiente
## Crear una carpeta donde estará el proyecto
## en el directorio de la carpeta clic derecho abrir git-bash
## Crear proyecto con LARAVEL (API)
## Seguir los pasos de esta web
https://www.binaryboxtuts.com/php-tutorials/laravel-8-json-web-tokenjwt-authentication/
composer create-project laravel/laravel api-clinica
## Abrir VS Code --> api-clinica --> env -->
DB_DATABASE=citas_medicas
## abrir Xampp
## Iniciar apache y Mysql
## Crear una base de datos llamada citas_medicas
## abrir git-bash
php artisan migrate
composer require tymon/jwt-auth
## archivo de configuración publico
php artisan vendor:publish --provider="Tymon\JWTAuth\Providers\LaravelServiceProvider"
## Generación de la llave
php artisan jwt:secret
## Abrir VSCode
api-clinica/config/auth.php 
buscar guards y pegar lo siguiente para habilitar la api
'guards' => [
        'web' => [
            'driver' => 'session',
            'provider' => 'users',
        ], 
        'api' => [
            'driver' => 'jwt',
            'provider' => 'users',
            'hash' => false,
        ],
    ],
## Configurar
/app/Models/User.php
## buscar y añadir las siguientes lineas

use Tymon\JWTAuth\Contracts\JWTSubject;
 
class User extends Authenticatable implements JWTSubject
## Al final

/**
     * Get the identifier that will be stored in the subject claim of the JWT.
     *
     * @return mixed
     */
    public function getJWTIdentifier()
    {
        return $this->getKey();
    }
 
    /**
     * Return a key value array, containing any custom claims to be added to the JWT.
     *
     * @return array
     */
    public function getJWTCustomClaims()
    {
        return [];
    }
## Crear el auto controller
php artisan make:controller AuthController
## Modificar el archivo app/Http/Controllers/AuthController.php
## copiar y pegar todo lo correspondiente a ese archivo descrito en el enlace
## Modificar el archivo routes/api.php
## copiar y pegar todo lo correspondiente a ese archivo descrito en el enlace
