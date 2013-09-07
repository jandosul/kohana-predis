# Kohana module for Predis client
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