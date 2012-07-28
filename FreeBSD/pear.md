PEAR (PHP Extention and Application Repository) Doesn't Install
========

Environment:
----

* FreeBSD 9.0 amd64
* PHP 5.4.x


Problem:
----

If you try to install PEAR from ports/devel/pear, it fails.

Solution:
----

(re)install the lang/php5 port with the debug option turned on.  If php5 is being reinstalled, all other PHP modules (php5-* and pecl-*) must be recompiled and reinstalled.

Related Issue:
----

If you happen to have databases/php5-pdo_mysql, you will need to recompile and reinstall it with the "mysql native driver" option turned *off*.  Otherwise, the pdo_mysql module will refer to san undefined symbol and fails to load.
