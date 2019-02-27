# Symfony coding standard of ProjektMOTOR
Symfony coding standards for ProjektMOTOR enriched by several useful rules.

We at ProjektMOTOR :heart: clean code. So we have a have an internal PHP coding standard based on
symfony coding standard 
used for all our projects. We are using [PHP CodeSniffer][1] with the great [Symfony PHP CodeSniffer Coding Standard
 of djoos][2] and some sniffs of [Slevomat Coding Standard][3], both adopted to our own needs.

## Goals of our coding standard

* Using already existing standards (PSR-1, PSR-2, Symfony).
* Coding standard can be used across different projects.
* Avoid duplications (also between code, CVS history and documentation).
* Ensure code quality across different dev setups (e.g. different IDEs).

## Installation

If you use [Composer][4], you can install ProjektMOTOR Coding Standard in your project with the following
command:

```BASH
composer require --dev projektmotor/symfony-coding-standard
```

## Usage

Just create a `phpcs.xml.dist` in your project's root directory with the following content:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<ruleset name="projektmotor-coding-standard">
    <rule ref="vendor/projektmotor/symfony-coding-standard/ProjektMOTORCodingStandard/ruleset.xml">
        <!-- If the standard is too hard, you can exclude some rules like this: -->
        <!-- <exclude name="Generic.Arrays.DisallowLongArraySyntax.Found" /> -->
        <!-- <exclude name="Generic.Files.LineLength.TooLong" /> -->
    </rule>
    
    <!-- Exclude project specific files if you want -->
    <!-- <exclude-pattern>WakkaFormatter</exclude-pattern> -->
</ruleset>
```

And then you can execute the CodeSniffer like this:

    vendor/bin/phpcs -s -p --colors src/


---
[1]: https://github.com/squizlabs/PHP_CodeSniffer#readme
[2]: https://github.com/djoos/Symfony-coding-standard
[3]: https://github.com/slevomat/coding-standard
[4]: https://getcomposer.org/
