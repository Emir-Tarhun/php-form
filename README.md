# PHP Form

Lightweight form validation library for PHP, with a concise syntax and powerful use of closures.

[![Build Status](https://travis-ci.org/rlanvin/php-form.svg?branch=master)](https://travis-ci.org/rlanvin/php-form)

## Basic example

```php
// create the form with rules
$form = new Form([
    'name' => ['required', 'trim', 'max_length' => 255],
    'email' => ['required', 'email']
]);

if ( $form->validate($_POST) ) {
    // $_POST data is valid
    save_to_db_or_something($form->getValues());
}
else {
   // $_POST data is not valid
   display_errors_or_something($form->getErrors());
   // $form->getValues() can be used to repopulate the form
}
```

Complete doc is available in [the wiki](https://github.com/rlanvin/php-form/wiki).

## Requirements

- PHP >= 5.3
- mbstring extension (http://www.php.net/manual/en/book.mbstring.php)

## Installation

The recommended way is to install the lib [through Composer](http://getcomposer.org/).

Just add this to your `composer.json` file:

```JSON
{
    "require": {
        "rlanvin/php-form": "1.*"
    }
}
```

Then run `composer install` or `composer update`.

Now you can use the autoloader, and you will have access to the library:

```php
<?php
require 'vendor/autoload.php';
```

### Alternative method

- Download the files in [src/](https://github.com/rlanvin/php-form/tree/master/src)
- (optional) Merge them into one
- Put them in a folder that is autoloaded, or `inclure` or `require` them
- Done

However be sure to come back regulary and check for updates.

## Documentation

Complete doc is available in [the wiki](https://github.com/rlanvin/php-form/wiki).

## Contribution

Feel free to contribute! Just create a new issue or a new pull request.

## License

This library is released under the MIT License.
