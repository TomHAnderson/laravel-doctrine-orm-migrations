=============
Configuration
=============


``config/migrations.php`` is the configuration file for migrations.
The file is divided into arrays by key that match the entity manager
name in ``config/doctrine.php``.


``table_storage.table_name``
============================

This database table keeps track of all the migrations that have already
run for your application. Using this information, we can determine which
of the migrations on disk haven't actually been run in the database.

default: ``migrations``


``table_storage.schema_filter``
================

Tables which are filtered by Regular Expression. You optionally exclude
or limit to certain tables. The default will allow all tables.

default: ``'/^(?!password_resets|failed_jobs).*$/'``


``migrations_paths``
====================

The directory is where migrations are stored

default: ``'Database\\Migrations' => database_path('migrations')``


``organize_migrations``
=======================

Organize migrations file by directory.
Possible values: ``"year"``, ``"year_and_month"`` and ``"none"``

default: ``"none"``


.. role:: raw-html(raw)
   :format: html

.. include:: footer.rst
