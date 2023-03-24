# Laravel - Docker

This is a brand new Laravel 10 app with Breeze and Blade installed.

The idea is to implement some Docker configuration similar to how `Laravel sail` does it.
I also want to implement some SSL certificate and add a custom domain to this project.

## App Components

-   Blank Laravel 10 app
-   Installed Breeze and Blade

```
composer require laravel/breeze --dev
php artisan breeze:install --dark
npm install
npm run dev
npm run build
```

-   Modified the `welcome` view, with just a message to test that it's working

## Creating the setup

1. Create a `docker-compose.yml` file on the root
2. Create a `docker` folder and add all the files you need

## Using the app

1. Install `Docker` and `docker-compose`
2. Clone the Github repo
3. Create the `.env` file by running `cp .env.example .env`
4. On the terminal run `docker-compose up -d` to create all the containers
5. Once all containers are up and running, you have to go inside the `php` container. You could run `docker-compose exec php bash`
6. Go to `/var/www/html` where all the files are located and run:
    - composer install
    - php artisan key:generate
    - php artisan migrate
    - npm install
    - npm run dev
    - npm run build
