# User attributes

you might want to add some attributes to your users, the library only comes with email and password, but you can add as many as you want.

Add the following code to your `config/App.php` file:
```php
public array $userExtraAttributes = [
	"name" => [ // The name of the attribute, the same name as the column in the database.
		"label" => "Name", // The label of the attribute, this will be displayed in the registration and login forms.
		"type" => "text", // The type of the attribute, ex. text, email, password, etc.
		"rules" => "required|max_length[255]", // The validation rules for the attribute.
	]
];
```
This is an example:
```php
	public array $userExtraAttributes = [
		"name" => [
			"label" => "Name",
			"type" => "text",
			"rules" => "required|max_length[255]",
		],
		"username" => [
			"label" => "Username",
			"type" => "text",
			"rules" => "required|max_length[255]",
		],
		"phone" => [
			"label" => "Phone",
			"type" => "text",
			"rules" => "required|max_length[255]|regex_match[/^[0-9]{10}$/]",
		]
	];
```