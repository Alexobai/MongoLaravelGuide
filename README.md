# MongoLaravelGuide

1. Creating a new project: composer create-project --prefer-dist laravel/laravel MongoIns "5.8.*"
1. Edit .env file: \
__MONGO_DB_HOST=127.0.0.1\
MONGO_DB_PORT=27017\
MONGO_DB_DATABASE=mongocrud\
MONGO_DB_USERNAME=\
MONGO_DB_PASSWORD=__
1. Add these in database.php:\
'connections' => [

     'mongodb' => [ \
            'driver'   => 'mongodb',\
            'host'     => env('MONGO_DB_HOST', 'localhost'),\
            'port'     => env('MONGO_DB_PORT', 27017),\
            'database' => env('MONGO_DB_DATABASE'),\
            'username' => env('MONGO_DB_USERNAME'),\
            'password' => env('MONGO_DB_PASSWORD'),\
            'options'  => []\
        ],\
    ]
1. do: __composer require jenssegers/mongodb__
1. add: __Jenssegers\Mongodb\MongodbServiceProvider::class__ in config/app/php
1. namespace App;

use Illuminate\Notifications\Notifiable;\
use Jenssegers\Mongodb\Auth\User as Authenticatable; 


class User extends Authenticatable 
{ \
    use Notifiable; 

    protected $connection = 'mongodb'; 
in User model
1.   $table->index('id'); 
     $table->unique('email'); 
     in user table migrate
           
