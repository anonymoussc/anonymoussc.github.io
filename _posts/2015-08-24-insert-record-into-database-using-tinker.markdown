---
title:  "Insert record into database using Tinker"
date:   2015-08-24 16:55:32
categories: Software-Engineering Laravel
summary: Using laravel 5.1 we can accessing tinker. Create a model using artisan.
---

Using laravel 5.1 we can accessing tinker. Create a model using artisan : 

    php artisan make:model Todolist

Newly generated file will be located at _/app/ Todolist.php_.

<script src="https://gist-it.appspot.com/https://github.com/apps-libX/aesl5-609/blob/8877db023b70fa06488a253f3c7c1bbfa51eafea/app/Todolist.php?footer=0"></script>

Start Tinker :

    php artisan tinker

Declare namespaces and create new object.

    namespace todos;

    $list = new Todolist;
    
Assuming field record contain id, name, description, timestamps. Assign data into list object as follow.
    
    $list->name = 'Nunquam gratia acipenser';

    $list->description = 'Nunquam captis valebat';
    
Saving.
    
    $list->save();

Check.

    echo $list->id;
    
    echo Todolist::all()->count();

Done.

    exit;


---
> If an NSA, FBI, CIA, DIA, etc analyst has access to query raw SIGINT databases, they can enter and get results for anything they want. Phone number, email, user id, cell phone handset id (IMEI), and so on - it's all the same. 
> <small>- [Edward Snowden](https://www.brainyquote.com/quotes/quotes/e/edwardsnow523864.html)</small>
