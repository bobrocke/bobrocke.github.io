---
layout: post
title: Laravel on Shared Hosting
description:
image:
category:
tags:
---
Despite what is commonly understood, Laravel can, indeed, be run on shared hosting. I use Reclaim Hosting and here's how I got my simple Laravel app running there.
<!--more-->

To get started, I used Reclaim Hosting cPanel's Installatron to install Laravel and create a MySQL database. My domain there is `laravel.bobrockefeller.reclaim.hosting` and the installer put my Laravel site at `home/public_html/laravel/public/`. Then I deleted everything in `home/public_html/laravel/` (yes, hang on). Once I had a clean directory, I used the cPanel tools to clone my site repository from GitHub into `home/public_html/laravel/`. So far, so good.

I copied over an `.env` file and made the necessary changes in these key sections:

```
APP_NAME=Laravel
APP_ENV=local
APP_KEY=bf6db3037bdb4c2badb8ca04c3ae10f6
APP_DEBUG=false
APP_TIMEZONE=UTC
APP_URL=https://laravel.bobrockefeller.reclaim.hosting
```

and:

```
DB_CONNECTION=mysql
DB_HOST=localhost
DB_PORT=3306
DB_DATABASE=my_database_name
DB_USERNAME=my_user_name
DB_PASSWORD=my_password
```

You may have other changes that need to be made, but those did it for me.

Next up: `ea-php83 /usr/local/bin/composer install`. I needed for force PHP v8.3 because Reclaim Hosting's PHP version selection for the my domains don't apply to the terminal. Go figure.

Reclaim Hosting does not allow `node.js`, so I had to skip `npm install`, assuming the Installatron installation handled that and that Reclaim Hosting will keep the necessary `node_modules` up to date. We'll see if that bites me later. It also means I need to run `npm run build` locally before deploying.

Now to get the database ready:

```
php artisan migrate
php artisan db:seed
```

And then to be sure Laravel's caches are clear:

```
php artisan cache:clear
php artisan config:clear
```

For some reason, I did not have to muck around with a `.htaccess` file. I guess Installatron took care of pointing requests into `home/public_html/laravel/public/`? 