============
Installation
============

Install this package with composer:

.. code-block:: bash

  composer require laravel-doctrine/migrations


After updating composer, add the ServiceProvider to the providers array in `config/app.php`

.. code-block:: bash

  LaravelDoctrine\Migrations\MigrationsServiceProvider::class,


To publish the config use:

.. code-block:: bash

  php artisan vendor:publish --tag="config" --provider="LaravelDoctrine\Migrations\MigrationsServiceProvider"


.. role:: raw-html(raw)
   :format: html

.. include:: footer.rst