# BEdita App

[![Run tests](https://github.com/bedita/app/actions/workflows/php.yml/badge.svg)](https://github.com/bedita/app/actions?query=workflow%3A%22php%22)
[![Code Coverage](https://codecov.io/gh/bedita/app/master/graph/badge.svg)](https://codecov.io/gh/bedita/app/branch/master)

This is the BEdita skeleton web app.

## Requirements

1. PHP 7.4, 8.0, 8.1 or 8.2
1. Download latest [Composer](https://getcomposer.org/doc/00-intro.md) or update via `composer self-update`.

## Installation

Simply run

```bash
composer create-project bedita/app
```

In case you want to use a custom app dir name (e.g. `/myapp/`):

```bash
composer create-project bedita/app myapp
```

You can now either use your machine's webserver to view the default home page, or start
up the built-in webserver with:

```bash
bin/cake server
```

Then visit `http://localhost:8765` to see the welcome page.

## Configuration

Read and edit the environment specific in `config/.env` in particular:

* `BEDITA_API` and `BEDITA_API_KEY` to setup API endpoint
* `DEBUG` set to `"true"` or `"false"`to activate/deactivate debug mode

Other environment agnostic settings can be changed in `config/app.php`.

You may then check `http://localhost:8765/credits` or `http://localhost:8765/{folder}` where `{folder}` is a folder uname on you BEdita4 project.

## Layout

The app skeleton uses [Milligram](https://milligram.io/) (v1.3) minimalist CSS
framework by default. You can, however, replace it with any other library or
custom styles.

## I18n

Internationalization behavior is not enabled by default.

To activate:

* in `config/app.php` uncomment `I18n` key and setup your wanted configuration
* in `src/Application.php` uncomment lines to add `I18nMiddleware` in `::middleware()` method
* in `config/routes.php` ucomment lines with `'routeClass' => 'BEdita/I18n.I18nRoute'` to enable routing rules

After that evey URL path will have a language prefix like `/en` automatically generated.
Using `I18nHelper` methods you may then handle URLs or object properties accordingly.
