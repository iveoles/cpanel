cPanel API package for Laravel 4
======
originally forked from https://github.com/joselara/cpanel-laravel


## Installation

Begin by installing this package through Composer. Edit your project's `composer.json` file to require `iveoles/cpanel-laravel`.

    "require": {
		"iveoles/cpanel-laravel": "dev-master"
	}

Next, update Composer from the Terminal:

    composer update

Once this operation completes add the service provider, aliases and configuration file.

1 - Provider: Open `app/config/app.php`, and add a new item to the providers array.

    'Iveoles\Cpanel\CpanelServiceProvider'

2 - Provider: Open `app/config/app.php`, and add a new item to the facade array.

    'Cpanel' => 'Iveoles\Cpanel\Facades\Cpanel',

3 - Publish Config

    php artisan config:publish iveoles/cpanel-laravel

That's it! You're all set to go.

## Usage

```php
<?php

class CpanelController extends Controller {

    public function getListAccounts()
    {
         try {

                $listaccts = array(json_decode(Cpanel::listaccts(), true));
                return $listaccts;

         } catch (Exception $e) {
                return 'Exception: ' .$e->getMessage();
         }

    }

}
```


