- https://www.youtube.com/watch?v=4PGKqrOZ9_k
- https://jwt-auth.readthedocs.io/en/develop/laravel-installation


composer require tymon/jwt-auth
php artisan vendor:publish --provider="Tymon\JWTAuth\Providers\LaravelServiceProvider"
php artisan jwt:secret # used to encrypt jwt and refresh tokens

JWT expires after 5min, refresh tokens expires after 1day

finish env
migrate

https://jwt-auth.readthedocs.io/en/develop/quick-start

edit User model

auth config file 

Laravel 11+: `php artisan install:api`

api.php

controller

seed some users

php artisan serve

Laravel 11: Need alter base controller: https://github.com/laravel/framework/issues/50566#issuecomment-1999078578

curl --location 'http://127.0.0.1:8000/api/auth/login' \
--header 'Content-Type: application/json' \
--data-raw '{
    "email": "halvorson.vern@example.org",
    "password": "password"
}'

Now we got the JWT, try: 

curl --location --request POST 'http://127.0.0.1:8000/api/auth/me' \
--header 'Authorization: ••••••'