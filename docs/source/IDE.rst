=================
Working with an IDE
=================

Although not necessarily required, you can also configure an IDE in order to more comfortably work with ms-van3t.

The suggested IDE, which has also been used for the development of ms-van3t, is _QtCreator_.

You can find all the instructions for setting up QtCreator with ns-3 (and the same applies to ms-van3t, as it is based on ns-3) on the `official ns-3 Wiki <https://www.nsnam.org/wiki/HOWTO_configure_QtCreator_with_ns-3>`_.

QtCreator can be installed on Debian/Ubuntu with:

.. code-block:: bash

   sudo apt install qtcreator

You need also to install the `libclang-common-8-dev` package (the command for Debian/Ubuntu is reported below):

.. code-block:: bash

   sudo apt install libclang-common-8-dev

Not installing `libclang-common-8-dev` may result in QtCreator wrongly highlighting several errors and not recognizing some types, when opening any source or header file, even if the code compiles correctly.

**Important**: if `libclang-common-8-dev` is not available, you can try installing a newer version. For example, on Ubuntu 22, we verified that `libclang-common-15-dev` works well too.
