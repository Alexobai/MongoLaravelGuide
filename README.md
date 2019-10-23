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
1.   $table->index('id');\
     $table->unique('email');\
     in user table migrate
           
1. The dynamic variable in routes are the parameter in controller
1. MongoDB use different id when register
1. Do not use name as id in the table migration definition
1. remember to include __use Jenssegers\Mongodb\Eloquent\Model as Eloquent;__ in Model
1. __php artisan storage:link__ used for access image from our private dir to webpage
1. _id is a funtional id, when you call other table from the _id table, use name like PointedToModelName_id. Or it will not work.
1. when calling like user()->profile; these names are the function name in the model;
