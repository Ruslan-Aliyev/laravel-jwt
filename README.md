# Laravel JWT

Key tutorials:
- https://www.youtube.com/watch?v=4PGKqrOZ9_k
- https://jwt-auth.readthedocs.io/en/develop/laravel-installation

```
composer require tymon/jwt-auth
php artisan vendor:publish --provider="Tymon\JWTAuth\Providers\LaravelServiceProvider"
php artisan jwt:secret     # used to encrypt jwt and refresh tokens
```

JWT expires after 5 min, refresh tokens expires after 1 day

Finish `.env` and migrate.

- https://jwt-auth.readthedocs.io/en/develop/quick-start

Edit the `User` model.

Edit the `auth.php` config file.

In Laravel 11, don't forget to run: `php artisan install:api`.

Finish `api.php` and the controller.

Seed some users.

In Laravel 11, also need to alter the base controller like so: https://github.com/laravel/framework/issues/50566#issuecomment-1999078578

`php artisan serve`

## Results

Get the JWT:
```
curl --location 'http://127.0.0.1:8000/api/auth/login' \
--header 'Content-Type: application/json' \
--data-raw '{
    "email": "halvorson.vern@example.org",
    "password": "password"
}'
```

Now we got the JWT, try: 
```
curl --location --request POST 'http://127.0.0.1:8000/api/auth/me' \
--header 'Authorization: ••••••'
```
