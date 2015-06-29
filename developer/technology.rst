Technology
==========

PHP
---
Accard runs on all web servers running `PHP`_ 5.3.3 or higher. To use the UPenn
default installtion, the following extensions must be installed and configured.

* OpenSSL
* LDAP (with SSL)
* APC (or simulated on newer versions)

Database
--------
Accard has been tested, and runs correctly on the following database platforms:

* `MySQL`_
* `Postgres`_
* `Oracle`_

Doctrine ORM is used exclusively by Accard, as such, all vendors supported by
this ORM should work properly. However, other vendors have not been tested and
their support can not be confirmed.

Symfony
-------
You must understand The `Symfony`_ Framework. Simply put, Accard is built on
top of `Symfony`_, and utilizes many of it's advanced features in order to
function. Without at least an intermediate understanding of this framework, you
will find it difficult to develop on Accard.

Get familiar with `Symfony's Architecture`_.

.. _Symfony: https://symfony.com
.. _Symfony's Architecture: https://symfony.com/doc/current/quick_tour/the_big_picture.html
.. _PHP: http://php.net
.. _MySQL: http://mysql.com
.. _Postgres: http://www.postgresql.org
.. _Oracle: http://www.oracle.com/database
.. _Doctrine: http://www.doctrine-project.org
