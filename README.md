# CodeIgniter Composer Project

This package installs the offical [CodeIgniter](https://github.com/bcit-ci/CodeIgniter) (version `3.0.*`) with secure folder structure via Composer.
Also, this package is based on [Kenji´s project](https://github.com/kenjis/codeigniter-composer-installer) (v0.4.2), please check his other project too.

You can update CodeIgniter system folder to latest version with one command.

## Folder Structure

```
codeigniter/
├── application/
├── composer.json
├── composer.lock
├── public/
│   ├── .htaccess
│   └── index.php
└── vendor/
    └── cocur/
        └── slugify/
    └── codeigniter/
        └── framework/
            └── system/
```

## Requirements

* PHP 5.4 or later
* `composer` command (See [Composer Installation](https://getcomposer.org/doc/00-intro.md#installation-linux-unix-osx))
* Git

## How to Use

### Install CodeIgniter Project

```
$ composer create-project Eihror/codeigniter-project project_folder
```

Above command installs `public/.htaccess` to remove `index.php` in your URL. If you don't need it, please remove it.

And it changes `application/config/config.php`:

~~~
$config['composer_autoload'] = FALSE;
↓
$config['composer_autoload'] = realpath(APPPATH . '../vendor/autoload.php');
~~~

~~~
$config['index_page'] = 'index.php';
↓
$config['index_page'] = '';
~~~


#### Install Translation Messages

If you want to install translations for system messages:

```
$ cd /path/to/project_folder
$ php bin/install.php translations 3.0.0
```