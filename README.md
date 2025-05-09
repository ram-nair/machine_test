Prerequisites
--------------
1.Installed Docker
2.Docker Compose installed on your system
3.Git installed 

Clone the application:
git clone <your-laravel-repo-url>

4.Create Docker Configuration Files
(Create a file named Dockerfile in project root)

5.Create a file named docker-compose.yml in project root

6.Create a directory named nginx/conf.d in the project root and add a file named app.conf

7.Create a directory named php in the project root and add a file named local.ini

8.Update .env File using the Sqlite database details & config Middleware details
(DB_CONNECTION=sqlite
DB_DATABASE=C:\wamp64\www\machine_test\database\database.sqlite)

REQUEST_LOGGING_ENABLED=true


9.Build and Run Docker Containers
(docker-compose build app
docker-compose up -d)

10.Install Dependencies
(docker-compose exec app composer install)

11.application key

docker-compose exec app php artisan key:generate


12.Run Migration:
docker-compose exec app php artisan migrate


13.clear cache:
docker-compose exec app php artisan config:cache
docker-compose exec app php artisan route:cache


14.Viewing Logs in SQLite

php artisan tinker
inside tinker 
DB::table('request_logs')->get();

check in browser:
http://127.0.0.1:8000/



Make change(true/false) the flag(REQUEST_LOGGING_ENABLED) in the .ENV file for writing log in sqlite db.







