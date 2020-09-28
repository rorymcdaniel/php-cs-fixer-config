# PHP CS Fixer Config
This config file was created to match as closely as possible the [PSR-12](https://www.php-fig.org/psr/psr-12/) standard 
since at present, [php-cs-fixer](https://github.com/FriendsOfPHP/PHP-CS-Fixer) does not yet have a preset for PSR-12.

## Installation
`composer require --dev rorymcdaniel/php-cs-config`

## CLI Usage
`php-cs-fixer --config=vendor/rorymcdaniel/php-cs-fixer-config/.php_cs.php --verbose fix path/to/files`

## Creating a PHPStorm File Watcher
* Install PHP-CS-Fixer `brew install php-cs-fixer`
* Preferences -> Tools -> File Watchers
* Click the + at the bottom and choose Custom template
* Name: `php-cs-fixer` (or whatever you like, this is just a label)
* File Type: PHP
* Scope: Current File (this prevents it from changing files you are not working on)
* Program: `/usr/local/bin/php-cs-fixer`
* Arguments: `--config=$ProjectFileDir$/vendor/rorymcdaniel/php-cs-fixer-config/.php_cs.php --verbose fix $FileDir$/$FileName$`
* Output paths to refresh: `$FileDir$/$FileName$`
* Expand Working Directory and Environment Variables
* Working Directory: `$ProjectFileDir$`
* Advanced options: only check `Trigger the watcher on external changes`
* Click OK to save
* Make sure the checkbox for `Enabled` is checked
PHP-CS-Fixer will now run on your code any time you save.