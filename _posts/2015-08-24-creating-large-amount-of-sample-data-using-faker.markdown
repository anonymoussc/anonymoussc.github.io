---
title:  "Creating large amounts of sample data using Faker"
date:   2015-08-24 21:00:35
categories: Software-Engineering Laravel
---

Require __Laravel 5.1__.

Faker package is included by default in _require-dev_ composer.json as of laravel 5.1.

Create the class table seeder (format _modelNameTableSeeder.php_) in _/database/seeds/_ directory, put the example 
code bellow in the _run()_ method of the class.

    $faker = \Faker\Factory::create();
    
    Todolist::truncate();

    foreach (range(1, 50) as $index) {
        Todolist::create([
            'name'        => $faker->sentence(2),
            'description' => $faker->sentence(4),
        ]);
    }

This will truncate (remove) the table record then it will loop (_foreach_) to create 50 new record for _name_ field it 
will contain a sentence with 2 words and _descripton_ field with a sentence of 4 words.

Faker can be useful for many task related to sample data, [Faker documentation](https://github.com/fzaninotto/Faker).

The working example of code snipet above as follow. File located at _/database/seeds/ TodolistTableSeeder.php_

<script src="http://gist-it.appspot.com/https://github.com/apps-libX/aesl5-609/blob/53e84915e9dc0cc47226ef25101daea13a6bb800/database/seeds/TodolistTableSeeder.php?footer=0"></script>

It need to be called from the database seeder class ( _/database/seeds/ DatabaseSeeder.php_ ) using : 

    $this->call('TodolistTableSeeder');

Again, an example bellow. File located at _/database/seeds/ DatabaseSeeder.php_

<script src="http://gist-it.appspot.com/https://github.com/apps-libX/aesl5-609/blob/53e84915e9dc0cc47226ef25101daea13a6bb800/database/seeds/DatabaseSeeder.php?footer=0"></script>

Rebuild class map, run :

    composer dump-autoload
    
Seeding the database :    

    php artisan db:seed


---
> The key to good decision making is evaluating the available information - the data - and combining it with your own estimates of pluses and minuses. As an economist, I do this every day. 
> <small>- Emily Oster</small>
