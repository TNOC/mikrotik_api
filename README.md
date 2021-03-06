RouterOS API
============

About
-----
- A composer package for Mikrotik / Router OS API
- Originally from: http://wiki.mikrotik.com/wiki/API_PHP_class

Installation
-----

###Composer

Incorperate the following to your `composer.json` file
```json
"repositories": [
    {
        "type": "git",
        "name": "tnoc/routeros",
        "url": "http://github.com/TNOC/routeros_api"
    }
],
"require": {
    "tnoc/routeros": "dev-master"
}
```

Then update your dependencies: `php composer.phar update`

Usage
------

Example index.php

```php
<?php

require_once "vendor/autoload.php";

use \RouterOS;

$api = new RouterOS\Core();

if ($api->connect('111.111.111.111', 'LOGIN', 'PASSWORD')) {

   $api->write('/interface/getall');

   $READ = $api->read(false);
   $ARRAY = $api->parse_response($READ);

   print_r($ARRAY);

   $api->disconnect();

}
```

Executables
----

###./bin/routeros-test.php

RouterOS Test is a script to test that a Mikrotik is accessable through API

<b>Usage:</b>
- `php ./bin/routeros-test.php --help`
- `php ./bin/routeros-test.php -h 111.111.111.111 -u username`

Examples
----

Examples are from http://wiki.mikrotik.com/wiki/API_PHP_class

- [Example 1](https://github.com/TNOC/routeros_api/wiki/Example-1)
- [Example 2](https://github.com/TNOC/routeros_api/wiki/Example-2)
- [Example 3](https://github.com/TNOC/routeros_api/wiki/Example-3)
- [Example 4](https://github.com/TNOC/routeros_api/wiki/Example-4)
- [Example 5](https://github.com/TNOC/routeros_api/wiki/Example-5)
