.. _ledger-nano:

Manage XNS via your Ledger Nano hardware wallet
===============================================

`Ledger Nano S <https://shop.ledger.com/products/ledger-nano-s>`_ and `Nano X <https://shop.ledger.com/products/ledger-nano-x>`_ are hardware wallets built by `Ledger <https://www.ledger.com/>`_.

A hardware wallet is a separate device that stores the private keys for your crypto assets. The keys never leave the device and remain secure even if the device is connected to a compromised computer.

The Insolar application for Ledger Nano S and X keeps your Insolar private key on the device and lets you manage XNS coins via `Insolar Wallet <https://wallet.insolar.io>`_.

The application is developed by the Insolar team. To request technical support, send an email to support@insolar.io.

Set up your Ledger Nano
-----------------------

To use the Insolar application on your Ledger Nano S or X hardware wallet, make sure you install and set up the following:

#. `Install Google Chrome <https://www.google.com/chrome/>`_. For the moment, it's the only supported browser.
#. `Install the Ledger Live application <https://support.ledger.com/hc/en-us/articles/360006395553/>`_. It allows you to manage applications on your device.
#. **Initialize your Ledger Nano** in one of two ways depending on whether or not you already have an Insolar Wallet.

   .. tabs::

      .. tab:: If you don't yet have an Insolar Wallet

         .. _no-wallet:

         Set up your `Nano S <https://support.ledger.com/hc/en-us/articles/360000613793>`_ or `Nano X <https://support.ledger.com/hc/en-us/articles/360018784134>`_ as described in the official Ledger documentation (click the links).

         .. caution::

            During the setup, you are required to choose a PIN and write down the recovery phrase for the device. Without the PIN you won't be able to unlock the device and without the recovery phrase you will be unable to restore access to your wallet.

         .. tip::

            You can hold several private keys for several Insolar Wallets on your Ledger Nano. Every key stored in the device has a number. By default, the number of the first key is ``0``.

      .. tab:: If you do have an Insolar Wallet

         .. _have-wallet:

         Initialize your device with the existing secret backup phrase:

         #. Follow the official instructions for `Nano S <https://support.ledger.com/hc/en-us/articles/360005434914>`_ or `Nano X <https://support.ledger.com/hc/en-us/articles/360015132494>`_ to initialize the wallet with the phrase.
         #. At **step 3** of the official instruction, choose the 18-word phrase length and enter your wallet's secret backup phrase.

         .. tip::

            * You can initialize only a new, "clean" Ledger Nano device with the Insolar secret backup phrase. A device can only have one phrase. Devices that already store other crypto assets are "occupied" with other phrases.

            * You can "migrate" only one existing Insolar Wallet to a clean device. Every private key stored on the device has a number. The number of "migrated" private key is ``0``.

            * In addition to the "migrated" wallet, you can create new Insolar Wallets and store their private keys on the device under different numbers, for example, ``1``, ``2``, etc.

#. Next, install the latest firmware on your `Nano S <https://support.ledger.com/hc/en-us/articles/360002731113-Update-Ledger-Nano-S-firmware>`_ or `Nano X <https://support.ledger.com/hc/en-us/articles/360013349800>`_.

Then proceed to installing the Insolar application on your device.

.. _install-ins-app:

Install the Insolar application on Ledger Nano
----------------------------------------------

To install the Insolar application on Ledger Nano:

#. Open Ledger Live, go to :guilabel:`Settings` (|cog-icon|) > :guilabel:`Experimental features`, and enable :guilabel:`Developer mode`.

   .. |cog-icon| image:: imgs/nano/cog-icon.png
      :width: 30px

   .. image:: imgs/nano/ledger-dev-mode-z.png
      :width: 700px

#. Open the :guilabel:`Manager` tab and connect and unlock your Ledger Nano.

   .. image:: imgs/nano/ledger-live-connect.png
      :width: 600px

   .. caution::

      If it's a charge-only cable, your computer won't recognize the device and you won't be able to perform any action.

#. If prompted, press both the :guilabel:`left` and :guilabel:`right` buttons simultaneously on the device to allow the manager connection.

   .. image:: imgs/nano/allow-ledger-live.png
      :width: 300px

#. Find :guilabel:`Insolar` in the application catalog and click :guilabel:`Install` next to it.

   This displays an installation window with a progress bar. Wait for the installation to complete.

   .. image:: imgs/nano/install-insolar-app.png
      :width: 600px

#. On the dashboard of the Ledger Nano device, press the :guilabel:`left` or :guilabel:`right` button to find the Insolar application.

#. Once found, press both the :guilabel:`left` and :guilabel:`right` buttons simultaneously to launch the application.

#. The application may notify you that it's pending the Ledger review. This is temporary.

   .. caution:: Wait for a couple of seconds before pressing any buttons.

      If you press both buttons too early (approximately within 300 milliseconds), your Ledger device may "freeze" on the :guilabel:`Pending Ledger review` screen due to a known bug that will be fixed soon.

      If this happens, reboot the device by unplugging it from the USB port. In case your device is the Nano X, the only way to reboot the device is wait for its battery to run out.

   Then, short-press both the :guilabel:`left` and :guilabel:`right` buttons again. A "short-press" should not last longer than 100 milliseconds.

Once the Insolar application is launched, proceed to creating an Insolar Wallet if you don't have one. Otherwise, :ref:`log in to your wallet <log-in-nano>`.

Create a connected Insolar Wallet
-----------------------------------

To create an Insolar Wallet using the Insolar application on Ledger Nano, complete the following steps:

#. In Google Chrome, open the `Insolar Wallet <https://wallet.insolar.io>`_ website and click :guilabel:`CREATE A NEW WALLET`.

   .. image:: imgs/nano/create-ins-wlt.png
      :width: 400px

#. On the **Create a new wallet** screen, click :guilabel:`USE LEDGER NANO`.

   .. image:: imgs/nano/use-ledger-n.png
      :width: 400px

#. Make sure your Ledger Nano is connected, unlocked, and the Insolar application is launched on it.

   .. _enter_key_number:

#. If required, enter the key number. You can hold several private keys for several Insolar Wallets on your Ledger Nano. Every key stored on the device has a number. By default, the number of the first key is ``0``.

   .. important:: Remember the number of this private key. You are required to specify it upon every login to use a particular Insolar Wallet.

   .. image:: imgs/nano/key-number.png
      :width: 500px

#. Check the boxes to allow anonymous data collection and agree to the terms of use. Then click :guilabel:`CONNECT TO LEDGER NANO`.

   .. image:: imgs/nano/connect-n.png
      :width: 450px

#. In the browser's prompt window, select the :guilabel:`Nano S` or :guilabel:`Nano X` device and click :guilabel:`Connect`.

   .. image:: imgs/nano/select-n.png
      :width: 400px

#. On the dashboard of your Ledger Nano, the Insolar application prompts you to confirm the :guilabel:`Create Account` command.
   
   .. image:: imgs/nano/ledger-s-create-account.png
      :width: 300px

   Press the :guilabel:`right` button to cycle though the command details.

#. On the :guilabel:`Sign transaction` or :guilabel:`Sign command` screen, press both :guilabel:`left` and :guilabel:`right` buttons to sign the command.
      
   .. image:: imgs/nano/ledger-s-create-account-sign.png
      :width: 300px

   This securely stores the private key on your Ledger Nano.

#. Once signed, the Insolar Wallet displays a wallet validation window.

   .. image:: imgs/mig-test/one-more-thing.png
      :width: 400px

#. Wait for the validation to complete and see the congratulation message.

   .. image:: imgs/nano/ledger-n-congrats.png
      :width: 400px

Once the wallet is created, you can manage your XNS with it. Every login and XNS transfer operation requires the associated private key stored on the Ledger Nano, so the device must be connected to confirm these actions.

.. _log-in-nano:

Log in to the connected Wallet and view your balance
----------------------------------------------------

To log in to the Insolar Wallet connected to your Ledger Nano, complete the following steps:

#. In Google Chrome, open the `Insolar Wallet <https://wallet.insolar.io>`_ and click :guilabel:`LOG IN`.
#. In the **Log in** panel, click the :guilabel:`Hardware` tab.

   .. image:: imgs/nano/login-hw.png
      :width: 400px

#. Make sure your Ledger Nano is connected, unlocked, and the Insolar application is launched on it.
#. Specify the key number you chose upon :ref:`wallet creation <enter_key_number>` and click :guilabel:`CONNECT TO LEDGER NANO`.

   .. image:: imgs/nano/enter-key-number.png
      :width: 400px

Insolar Wallet recognizes the launched application on the device and automatically logs in to the wallet. Once logged in, you can see your balance on the :guilabel:`Dashboard` tab.

Receive XNS
-----------

To receive XNS, do the following:

#. On the dashboard of your wallet, click the copy button below :guilabel:`XNS account`. This copies your XNS account address to the clipboard.

   .. image:: imgs/nano/copy-xns-account-address.png
      :width: 200px

#. Reveal the address to anyone who wishes to transfer XNS to you and wait for the incoming transaction.
#. View the incoming transactions: in the navigation panel, click :guilabel:`History`.

   .. image:: imgs/nano/click-history.png
      :width: 200px

#. On the **Transaction history** screen, open the :guilabel:`RECEIVED` tab.

   .. image:: imgs/nano/click-received.png
      :width: 450px

Once you receive the XNS, the balance on the :guilabel:`Dashboard` tab increases.

Send XNS
--------

To send XNS, do the following:

#. Open the :guilabel:`Dashboard` tab in the Insolar Wallet and click :guilabel:`SEND`.

   .. image:: imgs/nano/click-send.png
      :width: 200px

#. On the **Send XNS** screen, fill in the recipient address, amount of XNS to send, and click :guilabel:`NEXT`.

   .. image:: imgs/nano/send-xns.png
      :width: 500px

#. Make sure your Ledger Nano is connected, unlocked, and the Insolar application is launched on it.
#. On the **Send XNS** screen, check the following transaction details and click :guilabel:`SEND`:

   * recipient address,
   * amount of XNS to send,
   * transaction fee,
   * total amount—including the fee.

   .. image:: imgs/nano/check-details.png
      :width: 400px

#. In the dashboard of the Ledger Nano device, the application prompts you to verify the transfer details and sign the :guilabel:`Send XNS` command.

   Press the :guilabel:`right` button to cycle through the details and check that they are the same as in the web wallet.
  
#. On the :guilabel:`Sign transaction` or :guilabel:`Sign command` screen, press both :guilabel:`left` and :guilabel:`right` buttons to sign the :guilabel:`Send XNS` command.

   .. image:: imgs/nano/ledger-s-create-account-sign.png
      :width: 300px

#. View the outgoing transactions: in the navigation panel, click :guilabel:`History`.

   .. image:: imgs/nano/click-history.png
      :width: 200px

#. On the **Transaction history** screen, open the :guilabel:`SENT` tab.

   .. image:: imgs/nano/click-sent.png
      :width: 500px

Once you send XNS, the balance in the :guilabel:`Dashboard` tab decreases.

Transfer swapped XNS from deposit to your main account
------------------------------------------------------

Once you've :ref:`swapped your INS into XNS <swap>`, your XNS are stored in your Insolar Wallet on a deposit account. Each swap operation creates a separate deposit account that goes from the status :guilabel:`ON HOLD` to :guilabel:`RELEASED` upon a successful swap.

You can transfer your released XNS from deposit to your main account to perform further operations with them. 

#. In the Insolar Wallet, open the :guilabel:`SWAP` tab, choose the deposit account, and click :guilabel:`TRANSFER`.

   .. image:: imgs/nano/transfer-xns-deposit-to-main-account.png
      :width: 450px

#. On the :guilabel:`Transfer XNS screen`, choose the amount of XNS you want to transfer or click :guilabel:`Use all` to transfer all XNS from this deposit account. Click :guilabel:`TRANSFER` again. 

   .. image:: imgs/nano/transfer-xns-deposit-to-main-account-use-all.png
      :width: 500px      

#. In the dashboard of your Ledger Nano device, the Insolar application prompts you to verify the transfer details and sign the :guilabel:`Transfer` command. Press the :guilabel:`right` button to cycle through the details.

#. On the :guilabel:`Sign transaction` or :guilabel:`Sign command` screen, press both :guilabel:`left` and :guilabel:`right` buttons to sign the command.

   .. image:: imgs/nano/ledger-s-create-account-sign.png
      :width: 300px

#. View the incoming transactions: in the **Your Wallet** panel, click :guilabel:`Transaction history`.

   .. image:: imgs/nano/transfer-xns-deposit-to-main-transaction-history.png
      :width: 600px

Once the transfer operation finishes, the balance in the :guilabel:`Dashboard` tab increases.
