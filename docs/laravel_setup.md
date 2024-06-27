# Laravel setup

## Installation with sail

```bash
docker context use default

curl -s https://laravel.build/{ app-name } | bash

cd { app-name }

# set up the db
./vendor/bin/sail artisan migrate
```
[source](https://laravel.com/docs/11.x/installation#docker-installation-using-sail)

