# Twig view renderer

[![Build Status](https://github.com/vintagesucks/twig-renderer/workflows/Build/badge.svg)](https://github.com/vintagesucks/twig-renderer/actions) [![Dependabot](https://badgen.net/badge/Dependabot/enabled/green?icon=dependabot)](https://dependabot.com/) [![Packagist](https://img.shields.io/packagist/v/vintagesucks/twig-renderer.svg)](https://packagist.org/packages/vintagesucks/twig-renderer) [![Packagist](https://img.shields.io/packagist/dt/vintagesucks/twig-renderer.svg)](https://packagist.org/packages/vintagesucks/twig-renderer)

This extension allows you to use [Twig 3.x](https://twig.symfony.com/) templates in Yii 1

## Requirements
* Yii 1.1 or above
* PHP 7.2 or above

## Installing

* Install via Composer:

```sh
composer require vintagesucks/twig-renderer
```

* Add the following to your config file 'components' section:

```php
'viewRenderer' => [
    'class' => 'root.vendor.vintagesucks.twig-renderer.ETwigViewRenderer',
    'twigPathAlias' => 'root.vendor.twig.twig.lib.Twig',
    'fileExtension' => '.twig',
],
```

## Usage
* See [Twig syntax](https://twig.symfony.com/doc/3.x/templates.html)
* Current controller properties are accessible via `{{ this.pageTitle }}`
* `Yii::app()` object is accessible via `{{ App }}` (Example: `{{ App.name }}`)
* Yii's core static classes (CHtml, for example) are accessible via `{{ C.ClassNameWithoutFirstC.Method }}` (Example: `{{ C.Html.textField(name,'value') }}`)
* To call functions or methods which return non-string results wrap these calls in a `void` function: `{{ void(App.clientScript.registerScriptFile(...)) }}`

## Development
Run test matrix locally with [`act`](https://github.com/nektos/act):
```sh
act --job build \
  --workflows .github/workflows/build.yml \
  --platform ubuntu-latest=shivammathur/node:latest \
  --container-architecture linux/amd64
```
