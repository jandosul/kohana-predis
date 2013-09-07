# Kohana module for Predis
Using redis as session handler.

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
For php 5.4 only, for php 5.3 replace line 36 in init.php

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