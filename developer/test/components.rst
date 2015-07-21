Component Testing
=================

Installing
----------

.. tip::
    This is only required when creating a new component. You may skip this if you're working with an already existing one.

.. include:: installing.txt

Now that Codeception has been installed, we must bootstrap it. This will create a ``codeception.yml`` file and initialize the directory structure you will need to create and run your tests.

.. note::
    Codeception bootstrap does not completely meet our test requirements, so we simply use it as a code generator and then customize from there.

.. code-block:: bash

    bin/codecept bootstrap --namespace="AccardTest/Component/<component-name>"
    mv tests/ _tests/
    mv _tests/ Tests/
    rm -r Tests/acceptance Tests/acceptance.suite.yml Tests/_support/AcceptanceTester.php Tests/_support/_generated/AcceptanceTesterActions.php
    rm -r Tests/functional Tests/functional.suite.yml Tests/_support/FunctionalTester.php Tests/_support/_generated/FunctionalTesterActions.php
    bin/codecept build

Now, replace your ``codeception.yml`` file with the following code. Make sure you alter the code to suit your component.

.. include:: component-configuration.txt

Initializing
-------------

In order for Codeception to be able to run, the component must have all of its dependencies in place. First, check to see if the component directory has a ``composer.lock`` file. If it does, it's already ready to go; otherwise, run:

.. code-block:: bash

    composer install

Running Tests
-------------

.. tip::
    Learn more about the Codeception runner in the `Codeception documentation <http://codeception.com/docs/02-GettingStarted#Running-Tests>`_.

Ensure that you have properly initialized the component for testing by running ``composer install`` from the component root. Running the test suite requires this simple command:

.. code-block:: bash

    bin/codecept run unit

You may additionally have the test runner return a console code coverage report. This will make the test take longer to run, but will give you data about how much of your code is currently covered by unit tests:

.. code-block:: bash

    bin/codecept run unit --coverage

In addition to console coverage reports, you can choose to have the report rendered into HTML format so that it may be viewed in a browser:

.. code-block:: bash

    bin/codecept run unit --coverage-html

The HTML coverage report will be located at ``./Tests/_output/coverage/index.html``.

Writing Tests
-------------

Writing tests is largely dependent on evaluating just what it is that you are testing. Because of this, it is beyond the scope of this documentation to teach the "how" of unit testing; instead, familiarize yourself with the concepts and tools of which you will be using. The list below contains great resources for learning how to unit test. They've been placed in an order which seems fitting to learning how we do it.

.. tip::
    Codeception is built on the back of PHPUnit, it is just as important that you know how to use that tool as it is to learn Codeception.

* `What is Unit Testing? <https://en.wikipedia.org/wiki/Unit_testing>`_
* `PHPUnit Presentations <https://phpunit.de/presentations.html>`_
* `Codeception Introduction <http://codeception.com/docs/01-Introduction>`_
* `PHPUnit Documentation <https://phpunit.de/manual/current/en/index.html>`_
