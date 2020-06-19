UNIT TEST
====

How to hit endpoint in unit test
----
$parameters = ['param' => 'value'];
$header = [ 'HTTP_Authorization' => 'value'];

$this->get($url, $header);
$this->post($url, $parameters, $header);
$this->put($url, $parameters, $header);
$this->delete($url, $parameters, $header);

Expect Response Unit Test
----
$this->seeStatusCode(200);
$this->seeJson([ 'error' => false ]);
$this->seeJsonStructure([
    'error',
    'status',
    'message',
    'data'    => ['\*' =>
        [
            'product_name',
            'product_description',
            'created_at',
            'updated_at'
        ]
    ],

]);

/*remove \ at \\*

Steps
----
- install lumen
- uncomment bootstrap/app.php
$app->withEloquent();
$app->withFacades();

- create DB manually
- php artisan make:migration create_products_table
- php artisan migrate
- create model
- create faker/ factory
- create seed
- php artisan db:seed

install fractal, library untuk response JSON (optional)
----
- composer require league/fractal
- create routes, transformer, controller

running test
----
- ./vendor/bin/phpunit tests //test all our endpoints

running test in older version (Lumen <= 5.5)
---
- ./vendor/bin/phpunit tests --filter=testShouldReturnAllProducts // test specified unit test

Source
----
- Full repo: https://github.com/stephenjude/ProductAPI
- Source: https://medium.com/@stephenjudeso/testing-lumen-api-with-phpunit-tests-555835724b96
- phpunit doc: https://github.com/laravel/browser-kit-testing

## END UNIT TEST
