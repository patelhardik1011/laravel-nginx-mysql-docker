# laravel-nginx-mysql-docker
Basically this repository is about how we can set up Laravel, MySql and Nginx with Docker.

## About Laravel

Laravel is a web application framework with expressive, elegant syntax. We believe development must be an enjoyable and creative experience to be truly fulfilling. Laravel takes the pain out of development by easing common tasks used in many web projects, such as:

- [Simple, fast routing engine](https://laravel.com/docs/routing).
- [Powerful dependency injection container](https://laravel.com/docs/container).
- Multiple back-ends for [session](https://laravel.com/docs/session) and [cache](https://laravel.com/docs/cache) storage.
- Expressive, intuitive [database ORM](https://laravel.com/docs/eloquent).
- Database agnostic [schema migrations](https://laravel.com/docs/migrations).
- [Robust background job processing](https://laravel.com/docs/queues).
- [Real-time event broadcasting](https://laravel.com/docs/broadcasting).

Laravel is accessible, powerful, and provides tools required for large, robust applications.

## Setup with Docker

- Go to Docker folder and build image using below command. Here in my case I have taken image name as **laravel-php-image** which has PHP 7.4 version
  ```
    docker build -t "image_name" .
  ```
- Change your folder structure permission if you are on linux. For folder make it 755 and for files make it 644.
- Create **.env** file from **.env.example** file
- In docker-compose.yml file in **laravel-app** service need to provide image name as per built.
- Run below commands:
  ```
    docker-compose exec laravel-app composer install  
    docker-compose exec laravel-app php artisan key:generate
    docker-compose exec laravel-app php artisan cache:clear    
  ```  
- Set DB_HOST as mysql container name in the .env file
  
- Visit http://localhost:8000 and enjoy Laravel!!
