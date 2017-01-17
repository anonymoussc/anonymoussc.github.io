---
title:  "Components docs"
date:   2017-01-16 05:16:00
categories: Software-Engineering
summary: Components docs
---

Components docs

- [Cli](#cli)
- [Facade](#facade)
- [Entity](#entity)
- [Custom-Namespaces](#custom-namespaces)


---

### Cli
```
php artisan component:setup

php artisan component:make <ComponentName>
php artisan component:make <ComponentName> <ComponentName> <ComponentName>

php artisan component:make <ComponentName> --plain
php artisan component:make <ComponentName> -p

php artisan component:use <ComponentName>

php artisan component:list

php artisan component:make-command CustomCommand <ComponentName>
php artisan component:make-command CustomCommand --command=custom:command <ComponentName>
php artisan component:make-command CustomCommand --namespace=Components\Name\Commands <ComponentName>

php artisan component:make-migration create_users_table <ComponentName>
php artisan component:make-migration create_users_table --fields="username:string, password:string" <ComponentName>
php artisan component:make-migration add_email_to_users_table --fields="email:string:unique" <ComponentName>
php artisan component:make-migration remove_email_from_users_table --fields="email:string:unique" <ComponentName>
php artisan component:make-migration drop_users_table <ComponentName>

php artisan component:migrate-rollback
php artisan component:migrate-reset
php artisan component:migrate-refresh

php artisan component:migrate-rollback <ComponentName>
php artisan component:migrate-reset <ComponentName>
php artisan component:migrate-refresh <ComponentName>

php artisan component:migrate <ComponentName>

php artisan component:migrate

php artisan component:make-seed <seed-name> <ComponentName>
php artisan component:seed <ComponentName>

php artisan component:seed

php artisan component:make-controller <NameController> <ComponentName>

php artisan component:publish-asset <ComponentName>

php artisan component:publish-asset

php artisan component:make-model <ModelName> <ComponentName>
php artisan component:make-model <ModelName> <ComponentName> --fillable="username,email,password"

php artisan component:make-provider <ServiceProviderName> <ComponentName>

php artisan component:publish-migration <ComponentName>

php artisan component:publish-migration

php artisan component:publish-seed <ComponentName>

php artisan component:publish-seed

php artisan component:publish-config <ComponentName>
php artisan component:publish-config
php artisan component:publish-config <ComponentName> --force
php artisan component:publish-config --force

php artisan component:enable <ComponentName>

php artisan component:disable <ComponentName>

php artisan component:make-middleware <MiddlewareName>

php artisan component:make-mail <MailClassName>

php artisan component:make-notification <NotificationClassName>

php artisan component:update <ComponentName>

php artisan component:update

php artisan component:list

```


### Facade

```php
Component::all();

Component::getCached()

Component::getOrdered();

Component::scan();

Component::find('ComponentName'); // Component::get('ComponentName');

Component::findOrFail('ComponentName');

Component::getScanPaths();

Component::toCollection();

Component::getByStatus(1);

Component::has('ComponentName');

Component::enabled();

Component::disabled();

Component::count();

Component::getPath();

Component::register();

Component::boot();

Component::collections();

Component::getComponentPath('ComponentName');

Component::assetPath('ComponentName');

Component::config('composer.vendor');

Component::getUsedStoragePath();

Component::getUsedNow(); // Component::getUsed();

Component::setUsed('ComponentName');

Component::getAssetsPath();

Component::asset('component::img/logo.img');

Component::install('Rad/component');

Component::update('component');
```

### Entity

```php
$component = Component::find('component');

$component->getName();

$component->getLowerName();

$component->getStudlyName();

$component->getPath();

$component->getExtraPath('Assets');

$component->enable();

$component->disable();

$component->delete();
```

### Custom-Namespaces

```php
Lang::get('component::group.name')

View::make('component::index')
View::make('component::partials.sidebar')

Config::get('component.name')
```
