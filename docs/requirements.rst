.. _requirements:

Requirements
============

You need a Linux machine or Unix-like setup (theoretically an Apple machine
should work) that has the following software installed on it:

* `Python3`_ (with development libraries, pip and virtualenv)
* `GNU Privacy Guard`_
* `Tesseract`_
* `Imagemagick`_

.. _Python3: https://python.org/
.. _GNU Privacy Guard: https://gnupg.org
.. _Tesseract: https://github.com/tesseract-ocr
.. _Imagemagick: http://imagemagick.org/

Notably, you should confirm how you access your Python3 installation.  Many
Linux distributions will install Python3 in parallel to Python2, using the names
``python3`` and ``python`` respectively.  The same goes for ``pip3`` and
``pip``.  Using Python2 will likely break things, so make sure that you're using
the right version.

For the purposes of simplicity, ``python`` and ``pip`` is used everywhere to
refer to their Python 3 versions.

In addition to the above, there are a number of Python requirements, all of
which are listed in a file called ``requirements.txt`` in the project root.

If you're not working on a virtual environment (like Vagrant or Docker), you
should probably be using a virtualenv, but that's your call.  The reasons why
you might choose a virtualenv or not aren't really within the scope of this
document.  Needless to say if you don't know what a virtualenv is, you should
probably figure that out before continuing.


.. _requirements-baremetal:

Python-specific Requirements: No Virtualenv
-------------------------------------------

If you don't care to use a virtual env, then installation of the Python
dependencies is easy:

.. code:: bash

    $ pip install --user --requirement /path/to/paperless/requirements.txt

This should download and install all of the requirements into
``${HOME}/.local``.  Remember that your distribution may be using ``pip3`` as
mentioned above.


.. _requirements-virtualenv:

Python-specific Requirements: Virtualenv
----------------------------------------

Using a virtualenv for this is pretty straightforward: create a virtualenv,
enter it, and install the requirements using the ``requirements.txt`` file:

.. code:: bash

    $ virtualenv --python=/path/to/python3 /path/to/arbitrary/directory
    $ . /path/to/arbitrary/directory/bin/activate
    $ pip install  --requirement /path/to/paperless/requirements.txt

Now you're ready to go.  Just remember to enter your virtualenv whenever you
want to use *Paperless*.


.. _requirements-documentation:

Documentation
-------------

As generation of the documentation is not required for use of *Paperless*,
dependencies for this process are not included in ``requirements.txt``.  If
you'd like to generate your own docs locally, you'll need to:

.. code:: bash

    $ pip install sphinx

and then cd into the ``docs`` directory and type ``make html``.
