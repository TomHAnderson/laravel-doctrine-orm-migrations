========================
doctrine:migrations:diff
========================

.. code-block:: bash

  php artisan doctrine:migrations:diff


This command generates a migration by comparing the current database to
ORM mapping information.
Doctrine provides this command to generate migration classes by changing
entity mappings instead of manually adding modifications to migration class.

Given the following entity

.. code-block:: php

  use Doctrine\ORM\Mapping as ORM;

  #[ORM\Entity]
  class User
  {
      #[ORM\Id]
      #[ORM\Column(type: "integer")]
      #[ORM\GeneratedValue(strategy: "AUTO")]
      private $id;

      #[ORM\Column(type: "string", nullable: false)]
      private $name;
  }

When the diff command is ran the output will be like

.. code-block:: bash

  Generated new migration class to "Version20240914223731" from schema differences.


The new migration file will look like this

.. code-block:: php

  class Version20240914223731 extends AbstractMigration
  {
      /**
       * @param Schema $schema
       */
      public function up(Schema $schema): void
      {
          $this->addSql('CREATE TABLE users (id INT AUTO_INCREMENT NOT NULL, name VARCHAR(255) NOT NULL, PRIMARY KEY(id)) DEFAULT CHARACTER SET utf8 COLLATE utf8_unicode_ci ENGINE = InnoDB');
      }

      /**
       * @param Schema $schema
       */
      public function down(Schema $schema): void
      {
          $this->addSql('DROP TABLE users');
      }
  }


.. role:: raw-html(raw)
   :format: html

.. include:: footer.rst