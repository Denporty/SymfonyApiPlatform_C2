### Initialiser projet Symfony

```
create-project --prefer-dist symfony/skeleton 4-api-platform
```

* Update composer.json to downgrad version

```
composer update
```

```
composer require api
```

```
composer require symfony/maker-bundle --dev
```

```
php bin/console make:entity
```

* Confirmer l'utilisation de api-platform pour le CRUD

* Configurer .env 

```
DATABASE_URL="postgresql://docker:docker@127.0.0.1:5432/<db_name>?serverVersion=13&charset=utf8"
```

```
php bin/console doctrine:migrations:migrate
```

```
composer require orm-fixtures
```

```
php bin/console doctrine:fixture:load 
```

```
php bin/console make:user   
```

```
composer require jwt-auth 
```

```
 mkdir config/jwt   
```

```
php bin/console lexik:jwt:generate-keypair 
```
### Récupérer token jwt-auth

- .../api/login method POST dans le body au format JSON : 
``` 
 {
  "email": "<YOUR_MAIL>",
  "password": "<YOUR_PASSWORD>"
  } 
  ```
- retourne un token 
- .../api/tasks (ou autres routes protect par jwt) method GET/POST/PUT/DELETE etc... ajouter dans le header (key : Authorization, value : Bearer <JWT_TOKEN_GENERATE> 