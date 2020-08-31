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
        :text: Start step by step
        :classes: btn-link stretched-link font-weight-bold

    .. div:: text-muted

        Set up an Insolar network locally

Exchange and wallet developers: Integrate with Insolar
------------------------------------------------------

Just like the rest of the world, Insolar is moving along the path towards decentralization.

.. panels::
    :card: shadow
    :column: col-lg-12 p-2

    .. link-button:: decentralization
        :type: ref
        :text: Trace Insolar’s path to decentralization
        :classes: btn-link stretched-link font-weight-bold

    .. div:: text-muted

       Learn what is Insolar MainNet, what infrastructure powers it, and how it is decentralized

To integrate with Insolar MainNet at the current state of development, follow these steps:

.. panels::
    :card: shadow
    :column: col-lg-4 col-md-4 col-sm-6 col-xs-12 p-2

    .. link-button:: exchanges
        :type: ref
        :text: Follow integration scenarios
        :classes: btn-link stretched-link font-weight-bold text-left

    .. div:: text-muted

        Explore integration scenarios for various use cases

    ---

    .. link-button:: building_requester
        :type: ref
        :text: Build an API requester
        :classes: btn-link stretched-link font-weight-bold

    .. div:: text-muted

        :opticon:`code-square` Learn how to form and sign requests to Insolar MainNet API

    ---

    .. link-button:: https://github.com/insolar/observer
        :type: url
        :text: Run your own Observer node
        :classes: btn-link stretched-link font-weight-bold
        :tooltip: GitHub repository

    .. div:: text-muted

        :opticon:`mark-github` Deploy a node that replicates MainNet data

Consult the MainNet API references for implementation details:

.. panels::
    :card: shadow

    .. link-button:: https://apidocs.insolar.io/platform/latest
        :type: url
        :text: Smart contract API reference
        :classes: btn-link stretched-link font-weight-bold

    .. div:: text-muted

        :opticon:`link-external` Explore the MainNet API for creating members and transactions

    ---

    .. link-button:: https://apidocs.insolar.io/observer-services/v1
        :type: url
        :text: Read-only API reference
        :classes: btn-link stretched-link font-weight-bold

    .. div:: text-muted

        :opticon:`link-external` Explore the read-only MainNet API provided by an Observer node

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
   :caption: Exchanges

   decentralization
   use-cases
   requester
   Smart contract API reference <https://apidocs.insolar.io/platform/v1>
   Read-only API reference <https://apidocs.insolar.io/observer-services/v1>

.. toctree::
   :hidden:
   :caption: Users

   test-swap
   swap
   ledger-nano
