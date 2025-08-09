# Mobydick

_"Call me Ishmael."_

Your journey begins here — a reliable Docker-powered harbor for PHP development.

Mobydick helps you launch your vessel (containers) with modern and legacy PHP frameworks,  
navigating smoothly through the stormy seas of configuration, security, and dependency.

---

## ⚓ Prerequisites

Before setting sail, make sure these are aboard:

- Docker
- Apache
- MariaDB
- PHP 7.1 ~ 8.1 Frameworks

## 🧭 First Step: Generate a Certificate

### Create a certificate

```bash
$ generate-cert.sh
```

> 🗝️ Import it into your [Keychain Access](https://support.apple.com/ja-jp/guide/keychain-access/kyca1083/mac) to ensure secure waters ahead.

## 🚢 Launching the Fleet

```bash
$ docker compose up -d
```

## 🛠️ Installing Frameworks

### 📦 [Modern Container](https://github.com/limnxn/mobydick/blob/main/php/dockerfile-php-modern) (PHP 8.1.4)

#### CakePHP

```bash
$ composer require cakephp/cakephp .
```

#### Laravel

```bash
$ composer create-project laravel/laravel .
```

#### Laravel Mix

```bash
$ npm install
$ npm run watch
```

### 🪞 [Legacy Container](https://github.com/limnxn/mobydick/blob/main/php/dockerfile-php-legacy) (PHP 7.1)

#### Koseven

```bash
$ composer require koseven/koseven .
```

## 🐚 Database Settings

| Item     | Info        |
| -------- | ----------- |
| Host     | `127.0.0.1` |
| Port     | `3306`      |
| User     | `test`      |
| Password | `passw0rd`  |
| Database | `mobydick`  |

## 🐳 FAQ: Troubles on the High Seas

> Don’t worry, even Ahab had bugs.

### Koseven Troubleshooting

1. Log file missing
   - Check path at `/application/config/log4php.properties`
2. Database connection fails
   - Verify `/application/config/database.php`
3. Host trust issues
   - Add your host to `/application/config/url.php`
4. Missing styles
   - Ensure correct URL conditions in `/application/classes/Controller/Base.php`
5. Admin page not loading
   - Review IP settings in `/application/classes/Controller/Admin/Base.php`
6. Can't login to admin panel
   - Check `Cookie::$secure` and `Cookie::$domain` in `/application/bootstrap.php`
   - Clear session/cookie in Chrome DevTools
7. Event page errors
   - Create symbolic links:
   - `$ ln -s /var/www/html/public/www/official /home/{appName}Official`
   - `$ ln -s /var/www/html/public/www/contents /home/contents`
   - `$ ln -s /var/www/html/public/www/contents2 /home/contents2`
8. Image registration issues
   - Create folders:
   - `$ mkdir /mnt/{s3,s3/movie,s3/radio}`
   - `$ chmod -R 777 /mnt/s3`
