.. _exchanges:

=================
Explore use cases
=================

In short, to integrate with Insolar MainNet, do the following:

#. Create an Insolar wallet to keep the users' XNS coins. See the use cases: :ref:`Create a Wallet <create_wallet>` and :ref:`Get the Wallet's Balance <get_balance>`.
#. Let the users deposit XNS coins to your wallet—provide them with the wallet address. See the use cases: :ref:`Deposit Funds to Exchange <deposit_funds_to_ex>` and :ref:`Deposit Coins to Exchange <deposit_coins_to_ex>`.
#. Let the users withdraw XNS coins. They must create their own wallets on the MainNet and provide you with addresses of these wallets. See the use cases: :ref:`Create a Wallet <create_wallet>` and :ref:`Withdraw Coins from Exchange <withdraw_coins_from_ex>`.
#. Transfer XNS coins between wallets on the MainNet. See the use case: :ref:`Transfer Coins <transfer_coins>`.
#. Get information on transactions on the MainNet. See the corresponding `API request <https://apidocs.insolar.io/observer/latest/#operation/transactions-search>`_.

To invoke APIs correctly, familiarize yourself with:

* General API invocation sequence.
* List of API integration use cases. Each use case describes a sequence of steps and a list of corresponding API requests used in those steps.

The requests themselves are described in detail in the Insolar's API specifications — `MainNet API <https://apidocs.insolar.io/platform/latest>`_ and `Observer API <https://apidocs.insolar.io/observer/latest>`_.

To simplify testing, Insolar can provide a testing environment on demand.

.. _general_API_invocation:

General API invocation sequence
-------------------------------

The general API invocation sequence is as follows:

.. uml::

   @startuml
   skinparam componentStyle uml2
   skinparam shadowing false

   title Invoking Insolar API

   actor "Exchange" as E
   control "insolar-api\nEndpoint" as Ins
   control "insolar-observer-api\nEndpoint" as Obs

   group insolar-api\n(wallet creation, transfers)
   	E -> Ins : RPC API POST\n\t<b>node.getSeed</b>()
   	activate Ins
   	return <color:blue><b>seed</b></color>\n\t(used to identify individual RPC API request)

   	E -> Ins : RPC API POST\n\t<b>contract.call</b>(\n\t\t<color:blue><b>seed</b></color>,\n\t\tother params\n\t)
   	activate Ins
   	Ins -> Ins : handling\nAPI request
   	return result
   end

   group insolar-observer-api\n(reading wallet balance and other info)
   	E -> Obs: REST GET\n\t<b>endpoint</b>/{params}
   	activate Obs
   	Obs -> Obs : handling\nAPI request
   	return result
   end

   @enduml

.. _integration_use_cases:

Integration use cases
---------------------

Below is the list of integration use cases.

.. _create_wallet:

Use case: Create a wallet
~~~~~~~~~~~~~~~~~~~~~~~~~

To create a wallet:

#. Generate a private/public key pair.
#. Invoke Insolar's API:

   #. Provide the public key.
   #. Receive a reference to the new member—address on the Insolar network.

The wallet creation sequence is as follows:

.. uml::

   @startuml
   skinparam componentStyle uml2
   skinparam shadowing false

   title Wallet Creation

   actor "User" as U
   control "insolar-api\nEndpoint" as RPC
   entity "Insolar" as Ins

   activate U
   U -> U : generate new private/public key pair\n\t(<b>publicKey</b> used later\n\tto create & identify Insolar user)

   U -> RPC : RPC API POST\n\tnode.getSeed()
   activate RPC
   return <b>seed</b>
   U -> RPC : RPC API POST\n\tmember.create(\n\t\tsignature,\n\t\t<b>seed</b>,\n\t\t<b>publicKey</b>\n\t)
   activate RPC
   RPC -> Ins : invoke the MainNet
   activate Ins
   Ins -> Ins : create new \n\tuser & wallet
   return
   return <b>memberReference</b>\n\t(used later to identify\n\tInsolar member & wallet)
   deactivate U

   @enduml

API requests used:

* ``node.getSeed``
* ``member.create``

.. _get_balance:

Use case: Get the wallet balance
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

To view the balance, a user (exchange service or any other user) can either:

* Use their Insolar Wallet web interface.
* Or invoke the API using their Insolar's credentials (``memberReference`` or ``publicKey``).

The viewing sequence is as follows:

.. uml::

   @startuml
   skinparam componentStyle uml2
   skinparam shadowing false

   title Get Balance

   actor "Exchange" as E
   control "insolar-api\nEndpoint" as RPC
   control "insolar-observer-api\nEndpoint" as REST
   entity "Insolar" as Ins

   == Identifying a User (if memberReference not provided) ==
   E -> RPC : RPC API POST\n\tnode.getSeed()
   activate RPC
   return <b>seed</b>
   E -> RPC : RPC API POST\n\t<b>member.get</b>(\n\t\tsignature,\n\t\t<b>seed</b>,\n\t\t<b>publicKey</b>\n\t)
   activate RPC
   RPC -> Ins
   activate Ins
   Ins -> Ins : identify the user
   return
   return memberReference


   == Getting Wallet Info ==
   Ins <--> REST : stay in sync
   activate Ins
   activate REST
   deactivate REST
   deactivate Ins
   E -> REST: REST GET\n\t<b>member</b>/{<b>memberReference</b>}
   activate E
   activate REST
   return {\n\tbalance,\n\tdeposits\n}
   E -> REST: REST GET\n\t<b>balance</b>/{<b>memberReference</b>}
   activate E
   activate REST
   return balance
   deactivate E

   @enduml

API requests used:

* ``node.getSeed``
* ``member.get``

API endpoints used:

* GET ``<observer_URL>/member/{memberReference}``
* GET ``<observer_URL>/member/{memberReference}/balance``

.. _transfer_coins:

Use case: Transfer coins
~~~~~~~~~~~~~~~~~~~~~~~~

To transfer XNS coins to another user, a user (exchange or any other) can either:

* Use their Insolar Wallet.
* Or invoke the API.

To transfer coins via API, provide:

#. Sender's ``memberReference``, so Insolar can identify the sender.
#. ``toMemberReference``—recipient's reference.
#. An ``amount`` of XNS coins to transfer.

.. note:: To retrieve the ``memberReference``, invoke the relevant API and provide a public key.

The transfer sequence is as follows:

.. uml::

   @startuml
   skinparam componentStyle uml2
   skinparam shadowing false

   title Coin Transfer

   actor "Exchange" as E
   control "insolar-api\nEndpoint" as RPC
   entity "Insolar" as Ins

   == Identifying a User (if memberReference not provided) ==
   E -> RPC : RPC API POST\n\tnode.getSeed()
   activate RPC
   return <b>seed</b>
   E -> RPC : RPC API POST\n\t<b>member.get</b>(\n\t\tsignature,\n\t\t<b>seed</b>,\n\t\t<b>publicKey</b>\n\t)
   activate RPC
   RPC -> Ins
   activate Ins
   Ins -> Ins : identify the user
   return
   return memberReference

   == Performing Transfer ==
   E -> RPC : RPC API POST\n\tnode.getSeed()
   activate RPC
   return <b>seed</b>
   E -> RPC : RPC API POST\n\t<b>member.transfer</b>(\n\t\tsignature,\n\t\t<b>seed</b>,\n\t\tpublicKey,\t\t\t\t// user performing the transfer\n\t\tmemberReference,\t// user performing the transfer\n\t\t<b>amount</b>,\n\t\t<b>toMemberReference</b>\t// the recipient\n\t)
   activate RPC
   RPC -> Ins
   activate Ins
   Ins -> Ins : perform transfer
   return
   return {\n\tfee,\t// transfer's fee value\n\trequestReference\n}

   @enduml

API requests used:

* ``node.getSeed``
* (optional) ``member.get``
* ``member.transfer``

.. _deposit_funds_to_ex:

Use case: Deposit funds to an exchange
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

When a user deposits funds to the exchange and immediately converts them to XNS, an accompanying transfer between wallets should be performed.

This case is similar to :ref:`coin transfer <transfer_coins>`, where:

* ``memberReference`` is the reference to the owner of the wallet the coins are withdrawn from.
* ``toMemberReference`` is the reference to the exchange's wallet.

.. _deposit_coins_to_ex:

Use case: Deposit coins to an exchange
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

When a user deposits XNS coins to the exchange, an accompanying transfer between wallets should be performed.

This case is similar to :ref:`coin transfer <transfer_coins>`, where:

* ``memberReference`` is the reference to the owner of the wallet the coins are withdrawn from.
* ``toMemberReference`` is the reference to the exchange's wallet.

.. _withdraw_coins_from_ex:

Use case: Withdraw coins from an exchange
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Prerequisite: the recipient must have an Insolar's wallet created as described in :ref:`wallet creation <create_wallet>`.

This case is similar to :ref:`coin transfer <transfer_coins>`, where:

* ``memberReference`` is the reference to the owner of the wallet the coins are withdrawn from.

  .. note:: This can be either a wallet opened by the exchange for the user, or the exchange's wallet.

* ``toMemberReference`` is the reference to the recipient.
