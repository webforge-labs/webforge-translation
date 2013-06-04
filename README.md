# webforge-translation

Wrapper around the symfony translator for standalone use

## installation
Use [Composer](http://getcomposer.org) to install.
```
composer require -v --prefer-source webforge/testplate:dev-master
```

to run the tests use:
```
phpunit
```

## usage

```php
<?php

use Webforge\Translation\ArrayTranslator;

$translations = Array(
  'de'=>Array(
    'hello'=>'Hallo Welt!'
  ),

  'en'=>Array(
    'hello'=>'Hello World!',
    'how'=>'How are you?'
  ),
);

$translator = new ArrayTranslator('de', $translations, $fallback = array('en'));

print $translator->trans('hello')."\n"; // Hallo Welt!
print $translator->trans('how')."\n"; // How are you?

$translator->setLocale('en');
print $translator->trans('hello')."\n"; // Hello World!
```