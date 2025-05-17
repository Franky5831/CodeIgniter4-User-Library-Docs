# Codeigniter 4 User Management Library

Checkout the documentation [here](https://franky5831.github.io/CodeIgniter4-User-Library-Docs/).

This is a library developed for Codeigniter 4 that will make the management of users in your application easier and more secure.

The library will automatically manage the registration and login process, with security measures in pace.

## The security measures:
- [x] [Captchas](security-tools?id=captchas)
- [x] [Xss prevention](security-tools?id=xss-prevention)
- [x] [SQL Injections prevention](security-tools?id=sql-injections-prevention)
- [x] [Session Hijacking prevention](security-tools?id=session-hijacking-prevention)
- [x] [Brute force attacks prevention](security-tools?id=brute-force-attacks-prevention)


## How to install the library:
1. Run the following command in the root of your CodeIgniter 4 project:
```bash
composer require franky5831/codeigniter4-user-library
```

2. Copy the configurations you wish to override from the `franky5831/codeigniter4-user-library/src/Config/App.php` file to the `app/Config/App.php` file. The configurations that will not be copied will take the default values from the vendor file, you don't want to copy the `__construct` method from the vendor file.

For any issues or questions, please open an issue on the [GitHub repository](https://github.com/Franky5831/CodeIgniter4-User-Library).
