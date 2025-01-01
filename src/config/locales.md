# Locales and Translations

`glibc` supports setting the system locale whereas `musl` does not; both support
setting the language for applications.

## Listing locales

For a list of currently enabled locales, run:

```
$ locale -a
```

## Enabling locales

To enable a certain locale, un-comment or add the relevant lines in
`/etc/default/libc-locales` and [force-reconfigure](../xbps/index.md) the
`glibc-locales` package.

## Setting the system language

Set `LANG=xxxx` in `/etc/locale.conf`.

## Application locale

Some programs have their translations in a separate package that must be
installed in order to use them. You can
[search](../xbps/index.md#finding-files-and-packages) for the desired language
(e.g. "german" or "portuguese") in the package repositories and install the
packages relevant to the applications you use. An especially relevant case is
when installing individual packages from the LibreOffice suite, such as
`libreoffice-writer`, which require installing at least one of the
`libreoffice-i18n-*` packages to work properly. This isn't necessary when
installing the `libreoffice` meta-package, since doing so will install the most
common translation packages.
