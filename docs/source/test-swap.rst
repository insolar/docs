.. _migration_test:

Test token swap
===============

This test scenario walks you through the process of acquiring test INS tokens and swapping them to test XNS coins on Insolar **TestNet**.

.. warning:: Do not send real INS tokens from the main Ethereum network to Insolar MainNet during the testing period.

.. _needs_for_migration_test:

What you will need
------------------

You need to create two wallets:

* **Ethereum wallet** that supports Ethereum test networks (Ropsten in particular) and custom tokens. This test scenario uses `MetaMask <https://metamask.io/>`_ as an example.
* **Insolar Wallet** in which you can store XNS coins that are native for Insolar MainNet.

Additionally, you need to understand the following:

* **What coins and tokens are**. Coin is a native cryptocurrency of any blockchain and token is a unit of value that may be built on top of it. Coins operate independently, while tokens have specific uses. On the Ethereum network, the coin is the ether (ETH) and the token standard (upon which the INS token is built) is ERC-20. Test tokens and coins are those that operate in test networks. For testing purposes, we are going to use the Ropsten test network.
* **What a crypto faucet is.** The faucet is a quick and easy way of creating and distributing test coins and tokens on test networks.
* **What a token contract is.** Essentially, a token contract is a smart contract that contains a map of account addresses and their balances. The unit of the balance is the token. When tokens are transferred from one account to another, the token contract updates balances of both accounts.

.. _test_overview:

Test scenario overview
----------------------

To grasp what you will be doing, take a look at the steps of the test scenario:

#. Create a MetaMask wallet, switch to Ropsten test network inside it, and add the INS custom token.
#. Get Ropsten test ETH coins.
#. Swap the coins to test INS tokens using the INS token contract.
#. Create a wallet in Insolar Wallet and, automatically, receive a migration address.
#. Send the test INS tokens from the MetaMask wallet to the migration address. They will automatically swap to XNS native coins and appear in Insolar Wallet.

All the above steps are described in detail in subsequent sections.

.. _creating_metamask:

Creating and setting up Ethereum wallet
---------------------------------------

To create and set up a MetaMask Ethereum wallet:

#. Go to `metamask.io <https://metamask.io>`_ and add its extension to your browser.
#. Open the extension, click :guilabel:`Get Started`, :guilabel:`Create a Wallet`, and agree or disagree to help MetaMask improve itself.
#. Create a new password, confirm it, and agree to the "Terms of Use".
#. Reveal the backup phrase, copy it, and click :guilabel:`Next`.
#. Click the words of the backup phrase in correct order and then click :guilabel:`Confirm`.
#. Receive congratulations from MetaMask and click :guilabel:`All Done`. You will see the wallet's user interface.
#. In the top right corner, select :guilabel:`Ropsten Test Network` from the drop-down list:

   .. image:: imgs/mig-test/selecting-ropsten.png
      :width: 700px

#. In the bottom left corner, click :guilabel:`Add Token`:

   .. image:: imgs/mig-test/add-token.png
      :width: 700px

#. On the **Add Tokens** screen, open the :guilabel:`Custom Token` tab:

   .. image:: imgs/mig-test/custom-token.png
      :width: 300px

#. Copy the INS token contract address -- click the copy icon |copy-icon| in the right corner of the following code block:

   .. |copy-icon| image:: imgs/mig-test/copy-icon.png
      :width: 20px

   .. code-block::

      0x7e94f2be613c6846c40325b0f2712269a0d61d10

#. In the :guilabel:`Token Contract Address` field, paste the copied INS token contract address:

   .. image:: imgs/mig-test/ins-token.png
      :width: 300px

   MetaMask will find the INS token symbol and decimals of precision for you. Click :guilabel:`Next`.

#. On the next screen, click :guilabel:`Add Tokens`:

   .. image:: imgs/mig-test/add-ins.png
      :width: 300px

   With that, the MetaMask wallet is set up to operate the test ETH coins and INS tokens:

   .. image:: imgs/mig-test/wallet-setup.png
      :width: 700px

.. _acquire_test_tokens_and_swap:

Acquiring test ETH coins and swapping them to test INS tokens
-------------------------------------------------------------

To acquire, first, test ETH, then swap them to test INS tokens:

#. In the MetaMask wallet, first, click the :guilabel:`ETH` tab, then :guilabel:`Deposit`.

   .. image:: imgs/mig-test/eth-deposit.png
      :width: 700px

#. In the **Deposit Ether** window, click :guilabel:`Get Ether` next to **Test Faucet**:

   .. image:: imgs/mig-test/get-eth-from-faucet.png
      :width: 700px

   This opens the `MetaMask Ether Faucet page <https://faucet.metamask.io/>`_.

#. On the opened page, click :guilabel:`request 1 ether from faucet`:

   .. image:: imgs/mig-test/request-one-eth.png
      :width: 400px

   MetaMask will ask you to connect the request in the newly opened window. Click :guilabel:`Connect`:

   .. image:: imgs/mig-test/connect-request.png
      :width: 300px

   Once connected, you can click :guilabel:`request 1 ether from faucet` several times more (maximum 6). The corresponding transaction entries will appear below:

   .. image:: imgs/mig-test/test-eth-txes.png
      :width: 450px

   Wait several seconds to let the transactions be processed by the test network and return to the MetaMask wallet.

#. In the MetaMask wallet's **History**, the confirmed transactions will appear and your balance will be updated. Click :guilabel:`Send`:

   .. image:: imgs/mig-test/meta-balance.png
      :width: 700px

#. Again, copy the INS token contract address—click the copy icon |copy-icon| in the right corner of the following code block:

   .. code-block::

      0x7e94f2be613c6846c40325b0f2712269a0d61d10

#. On the **Add Recipient** screen, paste the copied address to the search field:

   .. image:: imgs/mig-test/send-search-field.png
      :width: 300px

   The MetaMask wallet will recognize the INS token contract and display the transfer details:

   .. image:: imgs/mig-test/meta-transfer-details.png
      :width: 300px

#. On the **Send ETH** screen, you don't need to send actual ETH to the token contract but a small amount of ETH will be automatically subtracted to pay for transaction processing.
   
   However, setting the correct gas value is required. To set it, click :guilabel:`Advanced Options`:

   .. image:: imgs/mig-test/advanced-options.png
      :width: 300px

#. On the **Customize Gas** screen, set the :guilabel:`Gas Limit` to ``80000`` (eighty thousand) and click :guilabel:`Save`:

   .. image:: imgs/mig-test/gas-limit.png
      :width: 300px

   .. caution:: If the gas limit value is lower than 80,000, the token contract will fail.

#. Back on the **Send ETH** screen, click :guilabel:`Next`:

   .. image:: imgs/mig-test/finally-send-eth.png
      :width: 300px

   And, on the next screen, click :guilabel:`Confirm`:

   .. image:: imgs/mig-test/finally-confirm.png
      :width: 300px

#. Repeat the procedure of sending ETH to INS token contract several more times to acquire enough test INS tokens.

   Once the corresponding transactions are confirmed, the MetaMask wallet is set up to operate test INS tokens:

   .. image:: imgs/mig-test/meta-wallet-setup.png
      :width: 700px

Next, migrate test INS token to the Insolar network. The migration will automatically swap the test INS tokens to test XNS coins.

.. _migrate_test_tokens:

Migrating test INS tokens and swapping them to test XNS coins
-------------------------------------------------------------

To migrate the test INS tokens and swap them to XNS coins:

#. Open the `Insolar Wallet <https://wallet.insolar.io>`_ website and make sure to select :guilabel:`TESTNET` from the drop-down list.

   .. image:: imgs/mig-test/select-testnet.png
      :width: 600px

#. Click :guilabel:`CREATE A NEW WALLET`:

   .. image:: imgs/mig-test/create-test-ins-wlt.png
      :width: 600px

   This opens a **Wallet creation tutorial**. Read through it attentively.

   Upon creation, your wallet takes care of security for you:

   #. Generates a secret backup phrase and private key using randomization. They are synonymous in function.
   #. Encrypts the key with your password and puts it in a keystore file. You can use this file to access your wallet and authorize operations.
   #. Ensures that you make a record of the secret backup phrase. Using this phrase, you can restore access to your wallet in case you lose the private key or the keystore file and your password.

   .. caution:: You are solely responsible for keeping your funds as no one else can restore access to your wallet. Insolar does not store your credentials, encrypted or otherwise.

#. On the **Create a new wallet** page:

   .. image:: imgs/mig-test/ins-wallet-password.png
      :width: 370px

   #. Enter a new password. It should be at least 8 characters long and contain a mix of numbers, uppercase, and lowercase letters.
   #. Re-enter the password to confirm it.
   #. Agree to the "Term of Use".
   #. Allow anonymous data collection if you want to help us improve the service.
   #. Click :guilabel:`NEXT`.

#. On the next screen, click :guilabel:`REVEAL TEXT` to see the backup phrase:

   .. image:: imgs/mig-test/ins-reveal-phrase.png
      :width: 450px

   The secret backup phrase is a series of words that store all the information needed to recover Insolar Wallet. The secret backup phrase and private key are synonymous in function.

   .. warning:: Never disclose your secret backup phrase (or private key).

   .. tip::

      Security tips:

      * Store the phrase in a password manager.
      * Write the phrase down on several pieces of paper and store them in different places.
      * Memorize the phrase.

   Once you have secured the backup phrase, click :guilabel:`NEXT`.

#. On the next screen, enter the requested words in the correct order and click :guilabel:`OPEN MY WALLET`:

   .. image:: imgs/mig-test/ins-word-order.png
      :width: 350px

#. Wait for the wallet validation to complete and all features to become available:

   .. image:: imgs/mig-test/one-more-thing.png
      :width: 400px

#. Once the wallet is created, receive congratulations from Insolar:

   .. image:: imgs/mig-test/ins-congrats.png
      :width: 400px

   And save the keystore file in one of the following ways:

   * Click :guilabel:`SAVE TO BROWSER` to save it to your browser local storage. Keeping the file locally allows easier access from the browser on the device you are using.
   * Click :guilabel:`DOWNLOAD` to save it to your device. In this case, you can later move it to another device via, for example, a USB drive.

   Later, you can log in using one of the following:

   * (Recommended) Your password and the keystore file saved to your browser.
   * Your password and the keystore file saved to your device.
   * Hardware wallet (such as Ledger Nano X or S).
   * (Weakest safety level) Unencrypted private key.

   Either way, Insolar Wallet does not store your private key. Instead, it uses the private key provided every time to authorize login and operations. While logged in, you can copy your unencrypted private key, but keep in mind, this is its most vulnerable form.

#. In Insolar Wallet, open the :guilabel:`SWAP` tab and copy your migration address.

   .. image:: imgs/mig-test/wlt-test-open-swap-tab.png
      :width: 600px

   On the :guilabel:`SWAP` tab, click :guilabel:`Copy migration address`.

   After that, return to the MetaMask wallet.

#. In the MetaMask wallet, open the :guilabel:`INS` tab and click :guilabel:`Send`:

   .. image:: imgs/mig-test/meta-send-ins.png
      :width: 700px

#. On the **Add Recipient** screen, paste the copied migration address to the search field:

   .. image:: imgs/mig-test/send-search-field.png
      :width: 300px

#. On the **Send Tokens** screen, first, click :guilabel:`Max`, then :guilabel:`Next`:

   .. image:: imgs/mig-test/send-ins-to-mig-addr.png
      :width: 300px

   And :guilabel:`Confirm` the transaction:

   .. image:: imgs/mig-test/confirm-send-to-mig-addr.png
      :width: 300px

   The migration process may take some time.

#. Once the transaction is processed by the Ropsten test network, your test XNS coins will appear in Insolar Wallet:

   .. image:: imgs/mig-test/ins-tokens-hold.png
      :width: 300px

This concludes the migration test.
