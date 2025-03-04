# 🚀 Kaido Kit FilamentPhp Starter Code

A powerful and opinionated FilamentPHP starter kit designed to accelerate your admin panel development. Kaido Kit provides a robust foundation with pre-configured plugins, configuration and best practices for building feature-rich admin interfaces.

![GitHub stars](https://img.shields.io/github/stars/siubie/kaido-kit?style=flat-square)
![GitHub forks](https://img.shields.io/github/forks/siubie/kaido-kit?style=flat-square)
![GitHub issues](https://img.shields.io/github/issues/siubie/kaido-kit?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-blue?style=flat-square)
![PHP Version](https://img.shields.io/badge/PHP-8.2-blue?style=flat-square&logo=php)
![Laravel Version](https://img.shields.io/badge/Laravel-11.0-red?style=flat-square&logo=laravel)
![Filament Version](https://img.shields.io/badge/Filament-3.2-purple?style=flat-square)
## Introduction Video
[![Build FilamentPhp Apps 10x Faster | Kaido-Kit Starter Kit (Complete Demo)](https://img.youtube.com/vi/t6q1zBqaBGU/maxresdefault.jpg)](http://www.youtube.com/watch?v=t6q1zBqaBGU "Build FilamentPhp Apps 10x Faster | Kaido-Kit Starter Kit (Complete Demo)")
## ✨ Features

### 🛠️ Developer Experience

- ⚡ Quick CRUD generation with customized [FilamentPHP](https://filamentphp.com/) stubs
    - Optimized UX out of the box
    - No need to modify generated resources
- 🔄 Auto reload on save for rapid development
- 📚 Easy API documentation using [Scramble](https://scramble.dedoc.co/)
- 📤 Built-in Export and Import examples in Filament resources

### 🔐 Authentication & Authorization

- 🛡️ Role-Based Access Control (RBAC) using [Filament Shield](https://filamentphp.com/plugins/bezhansalleh-shield)
- 🔑 Enhanced login page with custom design
- 🌐 Social login with Google via [Filament Socialite](https://filamentphp.com/plugins/dododedodonl-socialite)
- 👤 User profile management with [Filament Breezy](https://filamentphp.com/plugins/jeffgreco-breezy)
- 🔒 Instant 2-Factor Authentication capabilities
- 👥 Simple user-to-role assignment
- 🎭 User impersonation via [Filament Impersonate](https://filamentphp.com/plugins/joseph-szobody-impersonate)

### 📡 API & Integration

- 🚀 Full API support with [Filament API Service](https://filamentphp.com/plugins/rupadana-api-service)
    - Seamlessly integrated with Shield
    - Ready-to-use API endpoints
- 📨 Email integration using [Resend](https://resend.com/)
- 📝 Auto-generated API documentation

### 📁 Media & Content Management

- 🖼️ Integrated [Filament Media Library](https://filamentphp.com/plugins/filament-spatie-media-library)
    - Easy media handling process
    - [Spatie Media Library](https://spatie.be/docs/laravel-medialibrary) support

### ⚙️ Configuration & Settings

- 🎛️ Dynamic plugin management via [Filament Settings](https://filamentphp.com/plugins/filament-spatie-settings)
    - Enable/disable features on the fly
    - [Spatie Laravel Settings](https://github.com/spatie/laravel-settings) integration

## 🚀 Quick Start

1. Create new project using composer

    ```php
    composer create-project siubie/kaido-kit
    ```

2. Composer install

    ```php
    composer install
    ```

3. Npm Install

    ```php
    npm install
    ```

4. Copy .env

    ```php
    cp .env.example .env
    ```

5. Configure your database in .env

    ```php
    DB_CONNECTION=mysql
    DB_HOST=127.0.0.1
    DB_PORT=3306
    DB_DATABASE=kaido_kit
    DB_USERNAME=root
    DB_PASSWORD=
    ```

6. Configure your google sign in cliend id and secret (optional)

    ```php
    #google auth
    GOOGLE_CLIENT_ID=
    GOOGLE_CLIENT_SECRET=
    GOOGLE_REDIRECT_URI=http://localhost:8000/admin/oauth/callback/google
    ```

7. Configure your resend for email sending (optional)

    ```php
    #resend
    MAIL_MAILER=resend
    MAIL_HOST=127.0.0.1
    MAIL_PORT=2525
    MAIL_USERNAME=null
    MAIL_PASSWORD=null
    MAIL_ENCRYPTION=null
    RESEND_API_KEY=
    MAIL_FROM_ADDRESS="admin@domain.com"
    MAIL_FROM_NAME="${APP_NAME}"
    ```

8. Migrate your database

    ```php
    php artisan migrate --seed
    ```

9. Serve the Application

    ```script
    composer run dev
    ```

11. If run successfully you will get this login interface

    ![image.png](.github/images/login-screen.png)

12. When signed in it will show this (not much yet but it getting there :) )

    ![image.png](.github/images/after-login-without-rbac.png)

13. Next step is to setup the RBAC, first generate the role and permission

    ```php
    php artisan shield:generate --all
    ```

14. It will ask which panel do you want to generate permission/policies for choose the admin panel.
15. Setup the super admin using this command

    ```php
    php artisan shield:super-admin
    ```

    ![image.png](.github/images/provide-superadmin.png)

16. Choose your super admin user and login again.

    ![image.png](.github/images/after-login-rbac.png)

## Running on Docker with Laravel Sail

1. Clone the repository

```bash
git clone https://github.com/siubie/kaido-kit.git
```

2. Copy .env.example to .env

```bash
cp .env.example .env
```

3. Install dependencies

```bash
composer install
```

4. Install Laravel Sail

```bash
composer require laravel/sail --dev
php artisan sail:install
```

5. Run Sail

```bash
./vendor/bin/sail up -d
```

6. Generate App Key

```bash
./vendor/bin/sail artisan key:generate
```

7. Run migration

```bash
./vendor/bin/sail artisan migrate --seed
```

8. Next step is to setup the RBAC, first generate the role and permission

```bash
./vendor/bin/sail artisan shield:generate --all
```

9. Setup the super admin using this command

```bash
./vendor/bin/sail artisan shield:super-admin
```

10. Serve the Application

```bash
./vendor/bin/sail composer run dev
```

## Security
Set your app Debug to false in .env file
```php
APP_NAME="Kaido-Kit"
APP_ENV=local
APP_KEY=base64:gWUd7RPrCZm6iu7qFddY3039BQLroNHJ0nqKcBr8eeA=
APP_DEBUG=false
APP_TIMEZONE=UTC
APP_URL=https://localhost:8000
```

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 🙏 Acknowledgments

- [FilamentPHP](https://filamentphp.com/)
- [Laravel](https://laravel.com/)
- All our amazing contributors

## 💬 Support

- 🐛 [Report a bug](https://github.com/siubie/kaido-kit/issues)
- 💡 [Request a feature](https://github.com/siubie/kaido-kit/issues)
- 📧 [Email support](mailto:putraprima@gmail.com)
- 💬 [Discord community](https://discord.com/invite/RwqXDUJGPg)
- 💬 [Whatsapp community](https://chat.whatsapp.com/HJtRp9Eo5wl6NhYIJbkuZL)

## ⭐ Show your support
For Indonesian community you can get support and the recording course for how to create this kit here :
https://www.dosenngoding.com/courses/8

Give a ⭐️ if this project helped you!
## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=siubie/kaido-kit&type=Date)](https://star-history.com/#siubie/kaido-kit&Date)
