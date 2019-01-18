---
title:  "Components v0.5 docs"
date:   2018-10-10 22:03:00
categories: Software-Engineering
summary: Legacy.
---

{: .center-text}
![Black Flames](https://raw.githubusercontent.com/7cdn/images/gh-pages/blog/posts/blackflames.png)

- [Install](#install)
- [Cli](#cli)
- [Facade](#facade)
- [Entity](#entity)
- [Custom-Namespaces](#custom-namespaces)


### Install

``` bash
composer require onsigbaar/components
```

Add service provider.

``` bash
'providers' => [
  Onsigbaar\Components\ServiceProvider::class,
],
```

Add facade aliases.

``` bash
'aliases' => [
  'Component' => Onsigbaar\Components\Facades\Component::class),
],
```

Publish the package's configuration file.

``` bash
php artisan vendor:publish --provider="Onsigbaar\Components\ServiceProvider"
```


### Cli
``` bash
php artisan apic:setup

php artisan apic:make <ComponentName>
php artisan apic:make <ComponentName> <ComponentName> <ComponentName>

# do composer dump-autoload after apic:make

composer dump-autoload

php artisan apic:make <ComponentName> --plain
php artisan apic:make <ComponentName> -p

php artisan apic:use <ComponentName>

php artisan apic:list

php artisan apic:make-command CustomCommand <ComponentName>
php artisan apic:make-command CustomCommand --command=custom:command <ComponentName>
php artisan apic:make-command CustomCommand --namespace=Components\Name\Commands <ComponentName>

php artisan apic:make-migration create_users_table <ComponentName>
php artisan apic:make-migration create_users_table --fields="username:string, password:string" <ComponentName>
php artisan apic:make-migration add_email_to_users_table --fields="email:string:unique" <ComponentName>
php artisan apic:make-migration remove_email_from_users_table --fields="email:string:unique" <ComponentName>
php artisan apic:make-migration drop_users_table <ComponentName>

php artisan apic:migrate-rollback
php artisan apic:migrate-reset
php artisan apic:migrate-refresh

php artisan apic:migrate-rollback <ComponentName>
php artisan apic:migrate-reset <ComponentName>
php artisan apic:migrate-refresh <ComponentName>

php artisan apic:migrate <ComponentName>

php artisan apic:migrate

php artisan apic:make-seed <seed-name> <ComponentName>
php artisan apic:seed <ComponentName>

php artisan apic:seed

php artisan apic:make-controller <NameController> <ComponentName>

php artisan apic:publish-asset <ComponentName>

php artisan apic:publish-asset

php artisan apic:make-model <ModelName> <ComponentName>
php artisan apic:make-model <ModelName> <ComponentName> --fillable="username,email,password"

php artisan apic:make-provider <ServiceProviderName> <ComponentName>

php artisan apic:publish-migration <ComponentName>

php artisan apic:publish-migration

php artisan apic:publish-seed <ComponentName>

php artisan apic:publish-seed

php artisan apic:publish-config <ComponentName>
php artisan apic:publish-config
php artisan apic:publish-config <ComponentName> --force
php artisan apic:publish-config --force

php artisan apic:enable <ComponentName>

php artisan apic:disable <ComponentName>

php artisan apic:make-middleware <MiddlewareName> <ComponentName>

php artisan apic:make-mail <MailClassName> <ComponentName>

php artisan apic:make-notification <NotificationClassName> <ComponentName>

php artisan apic:update <ComponentName>

php artisan apic:update

```


### Facade

``` bash
Component::all();

Component::getCached()

Component::getOrdered();

Component::scan();

Component::find('ComponentName'); # Component::get('ComponentName');

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

Component::getUsedNow(); # Component::getUsed();

Component::setUsed('ComponentName');

Component::getAssetsPath();

Component::asset('component::img/logo.img');

Component::install('vendor/component');

Component::update('component');
```

### Entity

``` bash
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

```bash
Lang::get('component::group.name')

View::make('component::index')
View::make('component::partials.sidebar')

Config::get('component.name')
```


---
> Good, better, best. Never let it rest. 'Til your good is better and your better is best.
> <small>- [St. Jerome](https://www.brainyquote.com/quotes/st_jerome_389605)</small>