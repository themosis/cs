<!--
SPDX-FileCopyrightText: 2024 Julien Lambé <julien@themosis.com>

SPDX-License-Identifier: GPL-3.0-or-later
-->

Themosis Coding Standard
========================

Themosis CS is the coding standard used by Themosis in its projects and libraries.

The package provides a [PHP Code Sniffer](https://github.com/PHPCSStandards/PHP_CodeSniffer/) rules set that allows anyone
to format their codebase using our coding standards.

The `Themosis` ruleset is following the `PSR-12` ruleset with some refinements:
- Force strict type declaration
- Allow method names with underscore in test files

> The list of rules may change over time...

Usage
-----

First install the package using [Composer](https://getcomposer.org/), as well as the [dealerdirect/phpcodesniffer-composer-installer](https://github.com/PHPCSStandards/composer-installer) plugin like so:

```shell
composer require --dev themosis/cs dealerdirect/phpcodesniffer-composer-installer
```

> Composer may ask to "allow" the `dealerdirect/phpcodesniffer-composer-installer` plugin. Choose `yes` to allow.

The additional plugin will automatically make PHPCS rulesets available in your project.
Upon installation, you should have the `phpcs` and `phpcbf` binary files installed, you can run `php vendor/bin/phpcs -i` to list the available rulesets from the command-line.

### Add Themosis ruleset

Once the packages are installed in your project, create a `phpcs.xml.dist` file at the root of your project and add the following content:

```xml
<?xml version="1.0"?>
<ruleset name="My Application">
    <!-- Files -->
    <file>./src</file>
    <file>./tests</file>

    <!-- Code Rules -->
    <rule ref="Themosis"/>
</ruleset>
```

This is a basic ruleset for your project. The `PHP Code Sniffer` library is using an `xml` configuration file. When running the `phpcs` commands,
it will automatically load the ruleset before execution.

The above files will apply the `Themosis` ruleset against files stored inside the `src` and `tests` directories.

Additional information
----------------------

- [PHP Code Sniffer](https://github.com/PHPCSStandards/PHP_CodeSniffer)
