---
title:  "Structure"
date:   2015-03-28 05:00:00
summary: Directory structure, css framework, interoperability.
---

## Directory structure

Directory structure or type of package, distributed through composer (at development phase reside in app-components directory, or anywhere set in the config). The service components can also be distributed through npm or bower.

1. Operational system (laravel as a restful backend API and angularjs)
2. applications package - as a business process layer, bridge / layer between components and operational system, no business logic required, reason was code reuseability.
3. components package
4. service components (library/ helper)
5. theme

Components can act as a single responsibility package, but also capable to became full blown application by itself, example cms, accounting information system, geographical information system etc. Service components are recommended to respect single responsibility principle, for code reusability reason. Above architecture was scalable, if wasnt enough :

6.Enterprise - more than one business process layer tied together, enterprise will became bridge between business process layer and operational system.

## css framework

All

## Interoperability

By cast aside the NIH (Never Invented Here) syndrome.

More than 250.000 package strong (packalyst, packagist, ngmodules, npm, bower). Browserify can be used to bring NodeJS server side package to be able to be used on the client side.

