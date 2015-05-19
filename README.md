To use this Fix version

First add to your project 

    "cartalyst/sentry": "dev-feature/laravel-5",
Then

    "repositories": [
        {
            "type": "vcs",
            "url": "https://github.com/thebdcoder/laravel-mongodb-sentry-fix"
        }
    ],

Finally add this package to main project

        "jenssegers/mongodb-sentry": "dev-master"


After that do .

    php artisan vendor:publish --provider="Cartalyst\Sentry\SentryServiceProvider"

This will create a sentry config file on your config folder then change the Group , User and throttle to the following 

```
    'groups' => array(

        'model' => 'Jenssegers\Mongodb\Sentry\Group',

    ),

    'users' => array(

        'model' => 'Jenssegers\Mongodb\Sentry\User',

    ),

    'throttling' => array(

        'model' => 'Jenssegers\Mongodb\Sentry\Throttle',

    ),
```

Or if you have a custom model, make sure it extends the correct model.
