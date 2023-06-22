# oracle_connection

-download xampp
 	https://www.apachefriends.org/download.html

-download Oracle instant client and install.
	https://www.oracle.com/database/technologies/instant-client.html

-download oci8 extensions
	https://pecl.php.net/package/oci8

- remove extensions according to xampp version to xampp\php\ext

-open php.ini 
	remove the comment from extension=oci8_19

-open phpinfo.php 
	make sure the extension oci8 installed

-restart xampp

#using Laravel
can use yajra/laravel-oci8 package
1. composer require yajra/laravel-oci8
2. open the config/app.php file and add the following line inside the providers:
'providers' => [
Yajra\Oci8\Oci8ServiceProvider::class,
]

3. publish the configuration files by executing the following command:
php artisan vendor:publish --tag=oracle

5. open config/database.php file and locate the oracle array :
'oracle' => [
'driver'    => 'oracle',
'tns'       => env('DB_TNS', ''),
'host'      => env('DB_HOST', ''),
'port'      => env('DB_PORT', '1521'),
'database'  => env('DB_DATABASE', ''),
'username'  => env('DB_USERNAME', ''),
'password'  => env('DB_PASSWORD', ''),
'charset'   => env('DB_CHARSET', 'AL32UTF8'),
'prefix'    => env('DB_PREFIX', ''),
'prefix_schema' => env('DB_SCHEMA_PREFIX', ''),
'edition'   => env('DB_EDITION', 'ora$base'),
]

6. open .env file and add the database configuration
DB_CONNECTION=oracle
DB_HOST=
DB_PORT=
DB_DATABASE=
DB_USERNAME=
DB_PASSWORD=
DB_SERVICE_NAME=





