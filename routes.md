# Routes

The library comes with the following routes:
1. /register => GET, POST
2. /login => GET, POST
3. /logout => GET

All 3 routes can be disabled by adding the following code to your `config/App.php` file:
```php
	/*
	* Enable the routes for login, register, logout
	*/
	public bool $setUserLibRoutes = false;
```

You can just override the routes and serve your own controllers, if you want you also can extend the classes from the library to inherit the methods you need and override the ones you wish to change.
```php
	class User extends \Franky5831\CodeIgniter4UserLibrary\Controllers\User
	{
		// Your code goes here.
	}
```

Login and registration can be disabled by adding the following code to your `config/App.php` file:
```php
		/*
	* Enable Registration
	*/
	public bool $userCanRegister = true;

	/*
	* Enable Login
	*/
	public bool $userCanLogin = true;
```
This will throw a `404 Not Found` error by the individual controller methods if the client tries to access the route.