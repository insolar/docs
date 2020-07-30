.. Insolar documentation master file, created by
   sphinx-quickstart on Tue May 14 19:35:14 2019.

Insolar documentation
=====================

Welcome to Insolar documentation.

.. _quick_start:

Developers: Start with a guide
------------------------------

If you are a developer, explore Insolar technologies and run Insolar locally for testing purposes.

.. panels::
    :card: shadow

    .. link-button:: basics
       :type: ref
       :text: Understand Insolar
       :classes: btn-link stretched-link font-weight-bold
    
    .. div:: text-muted

        Take a look at the big picture

    ---

    .. link-button:: architecture
        :type: ref
        :text: Take a deep dive
        :classes: btn-link stretched-link font-weight-bold

    .. div:: text-muted

       Explore the intricacies of Insolar architecture

    ---

    .. link-button:: integration
        :type: ref
        :text: Start step-by-step
        :classes: btn-link stretched-link font-weight-bold

    .. div:: text-muted

       Set up an Insolar network locally

Exchange and wallet developers: Integrate with Insolar
------------------------------------------------------

If you are an exchange or you wish to implement your own wallet for Insolar MainNet, explore the API references and build an API requester.

.. panels::
    :card: shadow

    .. link-button:: exchanges
        :type: ref
        :text: Explore the use cases
        :classes: btn-link stretched-link font-weight-bold

    .. div:: text-muted

        Learn what API requests to invoke and in what sequences

    ---

    .. link-button:: building_requester
        :type: ref
        :text: Build an API requester
        :classes: btn-link stretched-link font-weight-bold

    .. div:: text-muted

        Learn how to form and sign requests to Insolar MainNet API

    ---

    .. link-button:: https://apidocs.insolar.io/platform/latest
        :text: MainNet API reference
        :classes: btn-outline-primary btn-block stretched-link

    .. div:: text-muted

        Explore the MainNet API for creating members and transactions

    ---

    .. link-button:: https://apidocs.insolar.io/observer-services/v1
        :text: Read-only MainNet API reference
        :classes: btn-outline-primary btn-block stretched-link

    .. div:: text-muted

        Explore the read-only MainNet API provided by an Observer node

Users: Swap INS to XNS
----------------------

If you are a user, learn how to swap the token for the coin.

.. panels::
    :card: shadow


    .. link-button:: migration_test
        :type: ref
        :text: Test the swap
        :classes: btn-link stretched-link font-weight-bold

    .. div:: text-muted

        On the TestNet, get test INS tokens and swap them for test XNS coins

    ---

    .. link-button:: swap
        :type: ref
        :text: Perform the swap
        :classes: btn-link stretched-link font-weight-bold

    .. div:: text-muted

        On the MainNet, swap your INS tokens for XNS coins native to MainNet

    ---

    .. link-button:: ledger-nano
        :type: ref
        :text: Use a hardware wallet
        :classes: btn-link stretched-link font-weight-bold

    .. div:: text-muted

        Store and manage XNS via Ledger Nano S or X

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
