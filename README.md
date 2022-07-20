# Welcome

All of your clases can be found in the /classes folder

Before you can use them, you need to configure the database settings.

The database settings can be found in /core/init.php

From there

- Set the host variable to your database, and don't forget the port number if there is one. If you are hosting an sql server on a local machine, use `127.0.0.1`
- Set the username varibale to your database username.
- Set the password variable to your database password.
- Set the db variable to the database you want to use.


# Classes

Now we will go over the classes


- `/Check.php` is used for input checking.
- `/Config.php` is used to store the config.
- `/Cookie.php` is used to generate cookies and validate them.
- `/DB.php` is used to perform all database operations.
- `/Hasher.php` is used to generate hashes.
- `/Input.php` is used to handle input for the server.
- `/Session.php` is used to handle sessions.
- `Token.php` is used to generate tokens.
- `/User.php` contanis many functions for creating, managing and deleting users.







```
<?php

session_start();
ini_set("display_errors",1);
$GLOBALS['config'] = array(
    'mysql' => array(
        'host'      => '127.0.0.1',
        'username'  => 'root',
        'password'  => 'your password',
        'db'        => 'database',
		'charset' => 'utf8mb4',
    ),
    'remember' => array(
        'cookie_name'   => 'hash',
        'cookie_expiry' => 604800,
    ),
    'session' => array(
        'session_name'  => 'user',
        'token_name'    => 'token',
    ),
);

spl_autoload_register(function($class) {
    require_once 'classes/' . $class . '.php';
});

?>
```
`