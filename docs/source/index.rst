.. Insolar documentation master file, created by
   sphinx-quickstart on Tue May 14 19:35:14 2019.

.. raw:: html
   :file: landing-page.html

Insolar documentation
=====================

Welcome to Insolar documentation.

.. _quick_start:

Developers: Start with a guide
------------------------------

If you are a developer, explore Insolar technologies and run Insolar locally for testing purposes.

.. raw:: html

   <div class="reduced-width">

.. rst-class:: column column2

:ref:`Understand Insolar <basics>`
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Learn the basics.

.. rst-class:: column column2

:ref:`Explore the architecture <architecture>`
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Take a deep dive.

.. rst-class:: column column2

:ref:`Set up Insolar network locally <integration>`
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Go through step-by-step instructions.

.. rst-class:: row

.. rst-class:: reg-text

Exchange and wallet developers: Integrate with Insolar
-------------------------------------------------------

If you are an exchange or you wish to implement your own wallet for Insolar MainNet, explore the API references and build an API requester.

.. raw:: html

   <div class="reduced-width">

.. rst-class:: column column2

:ref:`Explore the use cases <exchanges>`
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Learn what APIs to invoke and in what sequences.

.. rst-class:: column column2

:ref:`Build an API requester <building_requester>`
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Learn how to form and sign requests to MainNet API.

.. rst-class:: column column2

`MainNet API <https://apidocs.insolar.io/platform/latest>`_
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

API for creating members and transactions on the network.

.. rst-class:: column column2

`MainNet read-only API <https://apidocs.insolar.io/observer/latest>`_
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Read-only API provided by an Observer service that pulls information from the network.

.. rst-class:: row

.. rst-class:: reg-text

Users: Swap INS to XNS
----------------------

If you are a user, learn how to swap the token for the coin.

.. raw:: html

   <div class="reduced-width">

.. rst-class:: column column2

:ref:`Test the swap <migration_test>`
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

On the TestNet.

.. rst-class:: column column2

:ref:`Perform the swap <swap>`
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

On the MainNet.

.. rst-class:: column column2

:ref:`Store XNS in your hardware wallet <ledger-nano>`
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Manage your XNS via Ledger Nano S or X.

.. toctree::
   :hidden:
   :caption: Developers

   basics
   architecture
   integration
   glossary

.. toctree::
   :hidden:
   :caption: Exchange developers

   use-cases
   requester

.. toctree::
   :hidden:
   :caption: Users

   test-swap
   swap
   ledger-nano
