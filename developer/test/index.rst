Testing
=======

.. toctree::
    :hidden:

    components
    bundles
    application

Accard's architecture is logically divided into three main areas, following `Symfony's architecture`_ for consistency. These areas are components, bundles and the application itself. These fundamental blocks just so happen to correspond, one-to-one, with different logical areas of code testing; unit, integration and functional, respectively.

.. note::
    Accard uses the `Codeception`_ testing framework. Codeception is, essentially, a wrapper around `PHPUnit`_ adding BDD style testing as well as other common-use functionality. This enables use to perform various types of testing with one consistent tool. Codeception is loaded as a dev requirement in `Composer`_.

These testing concepts are well documented around the interwebs. We won't be diving into the nuts and bolts of what these testing concepts are; we will just provide a quick overview:

.. todo::
    Add links to "previous documentation" that has not yet been written.

.. note::
    **Unit testing** is a software development process in which the smallest testable parts of an application, called units, are individually and independently scrutinized for proper operation. Unit testing is often automated but it can also be done manually.

    **Integration testing** is the phase in software testing in which individual software modules are combined and tested as a group. It occurs after unit testing and before functional testing.

    **Functional testing** is a quality assurance (QA) process and a type of black box testing that bases its test cases on the specifications of the software component under test.

**Component Testing** (unit):
    Components are single units of functionality modeled around the *resource component*'s design. They do not contain much "useful" code; instead, they provide the structure of the domain and the tools used to manipulate it's target resource. This logically fits with unit testing, as unit tests are required to test an API (the "in's and out's"), and a component is nothing but an API outline.

    :doc:`Read more about component testing <components>`.

**Bundle Testing** (integration, unit):
    Bundles wrap the component's API definition with `Symfony`_ and Application specific code, and are based around the *resource bundle*'s design. You can view them as "glue code" which enables a component to actually do something useful. This creates a need for integration testing, and the new code developed to accommodate the "gluing" will also need unit testing.

    :doc:`Read more about bundle testing <bundles>`.

**Application Testing** (functional):
    The Application takes all of the bundles, and wires them together into a usable application. Typically, this requires adding external dependencies (which *should* be tested elsewhere) and configuring them to work together. The end result of this is a usable application... An application which will needed to be tested in terms of visuals and user interaction, or functional testing.

    :doc:`Read more about application testing <application>`.

.. _Codeception: http://codeception.com/
.. _Composer: http://getcomposer.org/
.. _PHPUnit: https://phpunit.de/
.. _Symfony: http://symfony.com/
.. _Symfony's architecture: http://symfony.com/doc/current/quick_tour/the_architecture.html