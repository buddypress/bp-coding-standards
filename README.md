# BuddyPress Coding Standards

`PHP_CodeSniffer` rules (sniffs) to enforce BuddyPress minimum coding conventions.

## Minimal requirements

* PHP 5.6+
* [PHPCS 3.5.5+](https://github.com/squizlabs/PHP_CodeSniffer/releases)
* [WPCS 2.3.0+](https://github.com/WordPress-Coding-Standards/WordPress-Coding-Standards/releases)

## Installation

To use this standard in a project, declare it as a dependency.

```bash
composer require buddypress/bp-coding-standards
```

This will install the latest compatible version of PHPCS and WPCS to your vendor directory in order to run sniffs locally.

You can also manually add this to your project's `composer.json` file as part of the `require` property:

```bash
"require": {
    "buddypress/bp-coding-standards": "^0.1.0"
}
```

## Using PHPCS

To use this standard with `phpcs` directly from your command line, use the command:

```bash
vendor/bin/phpcs --standard=BuddyPress .
```

Alternatively, you can set this as a composer script, which will automatically reference the correct version of `phpcs` and the dependent standards.

```bash
"scripts": {
    "phpcs" : "phpcs --standard=BuddyPress ."
}
```

Then use the following command:

```bash
composer run phpcs
```

You can also pass arguments to the composer phpcs script, following a `--` operator like this:

```bash
composer run phpcs -- --report=summary
```

## Extending the ruleset

You can create a custom ruleset for your project that extends or customizes these rules by creating your own  `phpcs.xml` or `phpcs.xml.dist` file in your project, which references these rules, like this:

```xml
<?xml version="1.0"?>
<ruleset>
    <description>Example project ruleset</description>

    <!-- Include BuddyPress Rules -->
    <rule ref="BuddyPress" />

    <!-- Project customizations go here -->

</ruleset>
```

## Change Log

Change log under [CHANGELOG.md](CHANGELOG.md).
