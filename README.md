# Twig view renderer
![Packagist](https://img.shields.io/packagist/v/vintagesucks/twig-renderer.svg) ![Packagist](https://img.shields.io/packagist/dt/vintagesucks/twig-renderer.svg)

This extension allows you to use [Twig 2.x](https://twig.symfony.com/) templates in Yii 1

## Requirements
* Yii 1.1 or above
* PHP 7.0 or above

## Installing

* Install via Composer:

`composer require vintagesucks/twig-renderer`

* Add the following to your config file 'components' section:

```php
'viewRenderer' => [
    'class' => 'root.vendor.vintagesucks.twig-renderer.ETwigViewRenderer',
    'twigPathAlias' => 'root.vendor.twig.twig.lib.Twig',
    'fileExtension' => '.twig',
],
```

### Usage
* See [Twig syntax](https://twig.symfony.com/doc/2.x/templates.html)
* Current controller properties are accessible via `{{ this.pageTitle }}`
* `Yii::app()` object is accessible via `{{ App }}` (Example: `{{ App.name }}`)
* Yii's core static classes (CHtml, for example) are accessible via `{{ C.ClassNameWithoutFirstC.Method }}` (Example: `{{ C.Html.textField(name,'value') }}`)
* To call functions or methods which return non-string results wrap these calls in a `void` function: `{{ void(App.clientScript.registerScriptFile(...)) }}`
