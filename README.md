# MongoLaravelGuide

1. Creating a new project: __composer create-project --prefer-dist laravel/laravel laravelmongodb__
1. Edit .env file: \
__MONGO_DB_HOST=127.0.0.1\
MONGO_DB_PORT=27017\
MONGO_DB_DATABASE=mongocrud\
MONGO_DB_USERNAME=\
MONGO_DB_PASSWORD=__
1. Add these in database.php:\
'connections' => [\


        ......\
     'mongodb' => [\
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
1. Ready to add models and other things
