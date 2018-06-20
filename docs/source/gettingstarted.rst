===============
Getting Started
===============

This tutorial requires you to setup a RecordsKeeper's public blockchain node on your local machine or remote server. If you have not done so already, please download and install RecordsKeeper's client on a local machine or remote server. If you are using the RecordsKeeper client on Windows, please read the installation instructions specific to Windows on the previous page.

Download the latest `RecordsKeeper <https://github.com/RecordsKeeper/recordskeeper-core/releases>`_ build and put the downlodeded files under the bin folder or any other folder and add its path to the System PATH environment variable so that you can run these commands from anywhere. Alternatively, you can go to the folder which contains RecordsKeeper binaries and execute these commands from there.

Connecting to the RecordsKeeper blockchain
------------------------------------------

To connect to the RecordsKeeper blockchain run the following command in bash or command prompt.

RecordsKeeper Testnet

.. code-block:: bash

    rkd recordskeeper-test@35.170.155.89:8379 -daemon

RecordsKeeper Mainnet

.. code-block:: bash

    rkd recordskeeper@35.172.1.247:7895 -daemon

When you run the above commands, they create a node connected to the RecordsKeeper Main node. The command will automatically set the permissions and consensus required for the blockchain.

RecordsKeeper Testnet is a complete open blockchain. When you connect to the Testnet, you will have the permissions to connect, send, receive and mine, but the RecordsKeeper Mainnet is currently under consensus rule for a certain number of blocks (You can read more about that in the `RecordsKeeper Whitepaper <https://www.recordskeeper.co/wp-content/uploads/2016/11/rk_whitepaper.pdf>`_) to avoid takeovers. When you connect to the RecordsKeeper Mainnet, you will receive an address. You can send that address to us through `RecordsKeeper Mining Permission <https://www.recordskeeper.co/contact-us/>`_ .

Interactive Command Line Mode
-----------------------------

Before we proceed, let’s enter interactive mode so we can issue commands to interact with the RecordsKeeper blockchain.

Testnet

.. code-block:: bash

    rk-cli recordskeeper-test

Mainnet

.. code-block:: bash

    rk-cli recordskeeper

Some Basic Commands
-------------------

Now that your node is up and running you can issue some basic commands in the interactive mode to familiarize yourself with RecordsKeeper.

To access general information about the RecordsKeeper Node:

.. code-block:: bash

    getinfo

See a list of all available commands for the RecordsKeeper Node:

.. code-block:: bash

    help

Create a new address in the RecordsKeeper Node wallet:

.. code-block:: bash

    getnewaddress

List all addresses in the RecordsKeeper Node wallet:

.. code-block:: bash

    getaddresses

Sending a Transaction in RecordsKeeper
--------------------------------------

The RecordsKeeper blockchain works on the same backend as Bitcoin algorithms. Both the RecordsKeeper Testnet and Mainnet can be used to send and receive XRK tokens. Use the following interactive commands to send transactions on RecordsKeeper blockchain.

Send
####

.. code-block:: bash
  
    send address amount (comment) (comment-to)
    Example: send 1KJFg5YLpvYNYZtCM6hhNYW8uBKtc3GHVboXco 10

This command is used to send one or more XRK tokens to an address, returning the txid. The amount field is the quantity of XRK tokens, and the address field is the address where you want to send the XRK tokens. This command will use the node's root address to send the transaction. Please make sure you have sufficient balance in the Node's root address for transactions to propagate over the RecordsKeeper blockchain. You can also provide specific comments for the transaction which are optional. The fees will be applied as per the transaction size.

Send from a Different Address
#############################

.. code-block:: bash

    sendfrom from-address to-address amount
    Example: sendfrom 1KJFg5YLpvYNYZtCM6hhNYW8uBKtc3GHVboXco 17gddiicYtbnwnWuY2ZYvM1Rw9e7t3pPjNJPab 10

This command is also used to send one or more XRK tokens to address, returning the txid. Using this command you can specify the from-address which you want to use to send the transaction. The amount field is the quantity of XRK tokens and the to-address field is the address where you want to send the XRK tokens. Please make sure you have sufficient balance in the from-address for transaction to propagate over the RecordsKeeper blockchain. The from-address used here is also one of the addresses generated for the node. You can also provide specific comments for the transaction which are optional. The fees will be applied as per the transaction size.

Publishing and Retrieving Data in RecordsKeeper
-----------------------------------------------

The RecordsKeeper blockchain is a public key-value based database on the blockchain. You can use the interactive command line to publish and retrieve stored information. As the blockchain is a shared concept, you can view all the published data and retrieve it using only a key or address. RecordsKeeper uses the streams to store the data. RecordsKeeper streams provide a natural abstraction for the RecordsKeeper blockchain, which focuses on general data retrieval, timestamping, and archiving, rather than the transfer of tokens between participants.

The "root" stream is open to all and anyone can publish data into the root stream. The following commands will give you a brief introduction about how to work with data over RecordsKeeper blockchain.

Publish
#######

.. code-block:: bash

    publish stream key data-hex
    Example: publish root rkKey 57687920796f7520636f6e766572746564206d653f

This command publishes an item in a stream. The stream name is passed, with the key provided in text form and a data-hex in hexadecimal format. It returns ref or creation txid. The data is published using the node's address. Use the next command discussed below to publish data from different address. The mining fees are applied as per the transaction size.

Publish from a Different Address
################################

.. code-block:: bash

    publishfrom from-address stream key data-hex
    Example: publishfrom 1KJFg5YLpvYNYZtCM6hhNYW8uBKtc3GHVboXco root rkKey 596f7520636f6e766572746564206d6520616761696e3f

This command works like publish, but publishes the item from the from-address. It is useful if the node has multiple addresses with different amounts. The mining fees are applied as per the transaction size.

Send as a Transaction
#####################

.. code-block:: bash

    sendwithdata/sendwithmetadata address amount data-hex|object
    Example: sendwithdata 1KJFg5YLpvYNYZtCM6hhNYW8uBKtc3GHVboXco 0 {"for":root,"key":"rkKey","data":"506c656173652073746f7020646f696e67207468697321"}

This works similarly to send, but with an additional data-only transaction output. You can pass raw data as data-hex hexadecimal string. It is also used to publish the data to a stream, pass an object like this {"for":StreamName,"key":"KeyName","data":"DataHex"} where stream is a stream name, ref or creation txid, the key is in text form, and the data is hexadecimal. You can pass the amount as 0, if you are only using this to publish the data over the RecordsKeeper stream. You can also send some XRK tokens while publishing the data over the stream. The fees will be applied as per the transaction size.
