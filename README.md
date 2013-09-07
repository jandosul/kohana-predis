# Kohana module for Predis
Using redis as session handler. Works on kohana 3.2, other versions not tested.

[Predis](https://github.com/nrk/predis) is an no-install object oriented Redis client library built using PHP5.

## Installation from zip file

Extract files to modules folder. Add extra line with module in bootstrap.php 

```php
<?php
	// Other modules
	 'redis'	  => MODPATH.'redis',  // Predis session manager
	// Other modules
```

## Caution
For php __5.4__ only, for php 5.3 replace line 36 in init.php

```php
<?php
        session_set_save_handler($this, true);
```
with
```php
        session_set_save_handler(
            array(&$this, "open"),
            array(&$this, "close"),
            array(&$this, "read"),
            array(&$this, "write"),
            array(&$this, "destroy"),
            array(&$this, "gc")
        );
```


## Dependencies ##

- Kohana >=3.2, not tested other branches of 3.x, maybe works
- PHP >= 5.4, 5.3

## Links ##

### Related ###
- [Source code](https://github.com/jandosul/kohana32-predis)
- [Predis](http://github.com/nrk/predis/)
- [Redis](http://redis.io/)
- [PHP](http://php.net/)
- [Git](http://git-scm.com/)

## Author ##

- [Zhandos Ulan](mailto:jandosul@gmail.com) ([twitter](http://twitter.com/jandosul))