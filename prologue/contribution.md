# Contribution Guide

## Bug Reports

To be able to track bug reports directly, we recommends pull-request before
posting in the issue tracker. If you have difficulties reproducing the bug for a
pull request, issue reports are of course welcome.

## Support Questions

The GitHub issue tracker is reserved for bugs reports or feature requests. If
you have questions, feel free to post them on
[stackoverflow](https://stackoverflow.com/) or our
[discord chanel](https://discord.gg/u4qpb5P).

::: tip

Please keep in mind that the community will benefit if a **solved problem** can
be found via google on stackoverflow.

:::

## Compiled Assets

If you are submitting a change that will affect a compiled file, such as most of
the files in `resources/sass` or `resources/js` of any litstack repository, do
not commit the compiled files. Due to their large size, they cannot
realistically be reviewed by a maintainer. This could be exploited as a way to
inject malicious code into Litstack. In order to defensively prevent this, all
compiled files will be generated and committed by Litstack maintainers.

## Security Vulnerabilities

If you discover a security vulnerability within Litstack, please send an email
to Lennart Carstens-Behrens at lennart.carbe@gmail.com or Jannes Behrens at
jannes@aw-studio.de. All security vulnerabilities will be promptly addressed.

## Coding Style

Litstack follows the PSR-2 coding standard as laravel. The
[Style CI](https://styleci.io/) included in the repository uses the
[laravel preset](https://docs.styleci.io/presets#laravel) to keep the code in a
familiar laravel standard.

::: tip

Checkout an example of an example of a laravel PHPDoc on the
[laravel website](https://laravel.com/docs/7.x/contributions#phpdoc).

:::

### PHP CS Fixer

Litstack uses a [PHP CS Fixer](https://github.com/FriendsOfPHP/PHP-CS-Fixer)
config whose goal is to closely match the coding standard of laravel. The fixer
can be executed with the following composer command.

```shell
composer style
```
