## extraer el archivo de laravel admin-clinica.zip
## abrir git bash en el directorio admin-clinica
```ruby
npm install
```
```ruby
ng serve
```
```ruby
al abrir http://localhost:4200/ debe mostrarse la interfaz de Pre-Clinic
```
## en caso de existir un error abrir y cerrar el vscode
## generar los enviroments
``` ruby
ng generate environments
## verificar en admin-clinic/src/enviroments
```
## editar environment.development.ts
``` ruby
export const environment = {
    URL_BACKEND: 'http://127.0.0.1:8000',
    URL_SERVICIOS: 'http://127.0.0.1:8000/api',
    URL_FRONTEND: 'http://localhost:4200/',
};
```
## crear dentro de la carpeta app una carpeta que se llame config
## crear en el directorio admin-clinic/src/app/config un archivo config.ts
## importar manualmente las siguientes lineas de codigo
``` ruby
import { environment } from "src/environments/environment.development";

export const URL_BACKEND = environment.URL_BACKEND;
export const URL_SERVICIOS = environment.URL_SERVICIOS;
export const URL_FRONTEND = environment.URL_FRONTEND;
```
## modificar el auth.services.ts
``` ruby
/admin-clinica/src/app/shared/auth/auth.service.ts
let URL = URL_SERVICIOS+"/auth/login";
```
## modificar los archivos
/admin-clinica/src/app/shared/auth/auth.service.ts
/admin-clinica/src/app/authentication/login/login.component.ts
/admin-clinica/src/app/authentication/login/login.component.html
/admin-clinica/src/app/common-component/header/header.component.html
/admin-clinica/src/app/common-component/header/header.component.ts
/admin-clinica/src/app/core/components/uikit/uikit.component.html
/admin-clinica/src/app/shared/gaurd/auth.gaurd.ts
