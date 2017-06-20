This example describes an issues with Read the Docs based documentation.

What I would like to achive is to have reStructuredText files
containing links to source code files in a GitHub repository.

The next requirements should be met:

1. Links should preferably work both on:

   1. `Github <https://github.com/>`_ (lower priority),
   2. `Read the Docs <https://readthedocs.org/>`_ hosted pages (higher priority).

2. Links should point to the same Git branch as they were built from.

In the next examples a Python source file ``conf.py`` is linked to.
Various approaches are listed to show which work which do not.

-------------
Relative path
-------------

This option **does work on GitHub** and always links to the correct branch.
But it **does not work on Read the Docs**.

Link is codded ass:

.. code-block:: restructuredtext

    See source file `conf.py <conf.py>`_.

See source file `conf.py <conf.py>`_.

---------------------------------------
Absolute path (agains Git project root)
---------------------------------------

This option behaves the same as the option above.
The advantage is the source path file is the same
regardless the position of this documentation file
``/doc/test.rst``

Link is codded ass:

.. code-block:: restructuredtext

    See source file `conf.py </conf.py>`_.

See source file `conf.py </conf.py>`_.

-----------------------
Full URL to github page
-----------------------

A full URL to a GitHub page works both on GitHub and on Read the Docs.
But this solution does not by design point to the same branch as the one
used to build the documentation.

.. code-block:: restructuredtext

    See source file `conf.py <https://github.com/jeras/readthedocs-source-links/blob/master/conf.py>`_

See source file `conf.py <https://github.com/jeras/readthedocs-source-links/blob/master/conf.py>`_

-----------
Custom role
-----------

.. code-block:: restructuredtext

    See source file :source:`/conf.py`

See source file :source:`/conf.py`
