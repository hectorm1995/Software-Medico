## RUN backend
```ruby
/Documentos/citas Medicas/api-clinica
php artisan serve
```
![texto alternativo de texto](./Imagenes/anexo3.PNG)

## /Documentos/citas Medicas/admin_clinica
```ruby
ng serve
```
## Instalación paquete de permisos Laravel

https://spatie.be/docs/laravel-permission/v5/installation-laravel

## Crear y copiar el archivo PermissionsDemoSeeder en /apiclinica/database/seeders/PermissionsDemoSeeder.php
# el enlace es del archivo es el siguiente: https://spatie.be/docs/laravel-permission/v5/basic-usage/new-app
## Agregar el correo de super-admin y contraseñas a los tres roles creados por defecto
# finalmente con el siguiente comando se borra y se actualizan las bases de datos
```ruby
php artisan migrate:fresh --seed --seeder=PermissionsDemoSeeder
```
## Editar middelware en los archivo php

## Crear una politica con laravel
### para el servidor del api-clinica
```ruby
php artisan make:policy UserPolicy --model=User
```
### run php artisan serve

