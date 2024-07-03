# Laravel setup

## Installation with sail

```bash
docker context use default

curl -s https://laravel.build/{ app-name } | bash

cd { app-name }

sail up -d

# set up the db
./vendor/bin/sail artisan migrate
# if error try : ./vendor/bin/sail php artisan migrate
```
[source](https://laravel.com/docs/11.x/installation#docker-installation-using-sail)


## Errors

If error `Access denied for user 'sail'@'%'` :

Check in `.env` that the `DB_DATABASE` name is not one already used by another project, if so change it and run :

```bash
sail down -v

sail up -d

./vendor/bin/sail artisan migrate
# if error try : ./vendor/bin/sail php artisan migrate
```

