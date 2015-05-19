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

Laravel MongoDB Sentry
======================

Because Sentry's models extends the original Eloquent model, it could not be used with MongoDB. This package includes models that extends `Jenssegers\Mongodb\Model` and thus support MongoDB.

Installation
------------

Make sure you have [jenssegers\mongodb](https://github.com/jenssegers/Laravel-MongoDB) installed before you continue.

Install using composer:

    composer require jenssegers/mongodb-sentry

For instructions on Sentry, check out https://cartalyst.com/manual/sentry/installation/laravel-4

Usage
-----

To use the included MongoDB-enabled models, change the Sentry configuration model sections:

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
