# WP Unit Test Project

I created this as an easy way to get a unit test suite started for testing WordPress plugins (and themes, I suppose).

### Getting Started

To create a new project, you'll need [Composer](http://getcomposer.org/). You can use either a global installation or a local one. These instructions will work for global installations, but if you are using the PHAR in this project, just replace `composer` with `php composer.phar` in any commands that use `composer`.

To install, simply run the following command:

```
composer create-project johnpbloch/wp-unit-test-project my-project
```

`my-project` is the name of the directory in which it will install the package.

This installs a base package along with all the necessary dependencies. One of these dependencies is PHPUnit itself. You don't have to use the version installed by the package, but I thought it would be a good idea to include it too. This will work no matter where PHPUnit is installed as long as you are able to invoke it.

To run the tests, simply run PHPUnit:

```
vendor/bin/phpunit
```

I like to add `./vendor/bin` to the front of my environment `$PATH` so that I can omit the path part of the command:

```
phpunit
```

If you're using Windows you might have to run the tests with this command:

```
php vendor/bin/phpunit
```

### Next Steps

After you've installed the package, you'll want to edit `composer.json` to change the name from `johnpbloch/wp-unit-test-project` to something more appropriate to your project.

Now you need to import your project and write some tests for it!

Adding your project's code as a dependency in Composer is the recommended way to include it in this package, but using a git submodule or SVN external would also work.

### Adding Tests to your Test Suite

By default, this package is configured to treat any PHP file in the `tests` directory as a unit test case. If you need to add other PHP files to the repo, either put them in a different directory or use a different file extension (such as `.inc`).

To create a new test, just create a new PHP file in the `tests` directory. This package comes with a custom `TestCase` class that extends PHPUnit's core TestCase. You should use the bundled test case when creating your test classes:

```php
<?php

use JPB\TestTools\TestCase;

class MyNewTest extends TestCase {

}
```

### Other Resources

* [PHPUnit Documentation](http://phpunit.de/manual/current/en/)
* [WP Mock Documentation](https://github.com/10up/wp_mock#use)
* [Mockery Documentation](https://github.com/padraic/mockery#simple-example)