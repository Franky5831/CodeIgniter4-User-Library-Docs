# Security tools
The library comes with a few security tools that can be used to prevent bots from registering and logging in to your application.


## Captchas
Captchas are a security measure that can be used to prevent bots from registering and logging in to your application.

### How to use the captcha:
The library supports both reCaptcha V3 by Google and Cloudflare Turnstile.
- [x] [Cloudflare Turnstile](security-tools?id=cloudflare-turnstile)
- [x] [reCaptcha V3](security-tools?id=recaptcha-v3)
- [ ] reCaptcha V2

### ReCaptcha V3
1. Generate the credentials for your application in the [Google dashboard](https://www.google.com/recaptcha/admin/create), make sure to choose reCaptcha V3 as V2 is currently not supported (but will be soon).
2. Add the following code to your `config/App.php` file:
```php
	// Enables captchas for the user registration and login process.
	public bool $userLibCaptcha = true;

	// Chooses the captcha type to use, currently supports 'recaptcha-v3' and 'cloudflare'.
	public string $userLibCaptchaType = 'recaptcha-v3';

	// The options for the captcha, depending on the type chosen.
	public array $userLibCaptchaOptions = [
		"recaptcha-v3" => [
			"siteKey" => "{Your site key goes here}",
			"secretKey" => "{Your secret key goes here}",
		]
	];
```

### Cloudflare Turnstile
1. Generate the credentials for your application in the [Cloudflare dashboard](https://www.cloudflare.com/application-services/products/turnstile/).
2. Add the following code to your `config/App.php` file:
```php
	// Enables captchas for the user registration and login process.
	public bool $userLibCaptcha = true;

	// Chooses the captcha type to use, currently supports 'recaptcha-v3' and 'cloudflare'.
	public string $userLibCaptchaType = 'cloudflare';

	// The options for the captcha, depending on the type chosen.
	public array $userLibCaptchaOptions = [
		"cloudflare" => [
			"siteKey" => "{Your site key goes here}",
			"secretKey" => "{Your secret key goes here}",
		]
	];
```


## XSS prevention
The library uses the composer package [voku/anti-xss](https://github.com/voku/anti-xss) to prevent Xss attacks.
The library creates the validation rule `validate_xss` which sets a validation error if the input contains any HTML tags, this validation rule can be used in other custom POST requests you may want to create.


## SQL Injections prevention
The library doesn't came with any protection against SQL Injections, it actually uses the [Query Builder](https://codeigniter.com/user_guide/database/query_builder.html) built in the CodeIgniter framework to prevent them during the registration and login process.


## Session Hijacking prevention
The library cames with some protection against session hijacking, when setting the session it saves the user's IP address and the user agent, this is a rudimentary protection against session hijacking, I'm still working on it.
To enable the feature, add the following code to your `config/App.php` file:
```php
	// Enables the session hijacking protection.
	public bool $userLibSessionHijackingProtection = true;
```


## Brute force attacks prevention
The library comes with some built in protection against brute force attacks, those features can be enabled by adding the following code to your `config/App.php` file:
```php
	// Enables the brute force attacks protection.
	public bool $userPostErrorLogger = true;

	// The maximum number of errors allowed in a row.
	public int $maxPostErrors = 10;

	// The time in seconds that the user will be blocked for.
	public int $userErrorTimeout = 300;
```
The feature is based on the IP address of the user, if the user tries to register or login more than 10 times in a row from the same IP address, the user will be blocked for 5 minutes.
The data is stored in the codeigniter cache.