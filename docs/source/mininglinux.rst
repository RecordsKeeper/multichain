==================================================
Mining Guide for RecordsKeeper Blockchain on Linux
==================================================

The following document helps the users to initiate mining for RecordsKeeper blockchain on the Linux operating system. All the commands and processes displayed in this document have been tested and created on the Ubuntu Operating System. The detailed overview to start mining for RecordsKeeper blockchain is as follows:

* :ref:`linux-systemrequirements`
* :ref:`linux-installingrk`
* :ref:`linux-connectingrk`
* :ref:`linux-miningpermissions`
* :ref:`linux-startrkaftermining`
* :ref:`linux-stoprk`

.. _linux-systemrequirements:

System Requirements
-------------------

* Linux: 64-bit, supports Ubuntu 12.04+, CentOS 6.2+, Debian 7+, Fedora 15+, RHEL 6.2+.
* 512 MB of RAM
* 1 GB of disk space

.. _linux-installingrk:

Installing RecordsKeeper on Linux
---------------------------------

First, install these dependencies by executing the following commands:

.. code-block:: bash

    sudo apt-get update
    sudo apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils
    sudo apt-get install libboost-all-dev
    sudo add-apt-repository ppa:bitcoin/bitcoin
    sudo apt-get update
    sudo apt-get install libdb4.8-dev libdb4.8++-dev

To download the executable directly from the browser `click here <https://github.com/RecordsKeeper/recordskeeper-core/releases/download/v1.0.0/recordskeeper-1.0.0.tar.gz>`_ .

And, if you want to download it from the command line terminal, then use this command:

.. code-block:: bash

    wget https://github.com/RecordsKeeper/recordskeeper-core/releases/download/v1.0.0/recordskeeper-1.0.0.tar.gz

Then, move to the location of the downloaded files and run the following commands from your 
terminal:

.. code-block:: bash

    tar -xvzf recordskeeper-1.0.0.tar.gz
    cd recordskeeper-1.0.0
    mv rkd rk-cli rk-util /usr/local/bin 

Moving the RecordsKeeper files to the bin directory to make them easily accessible from the command line anywhere.

.. note::
    * If you get an error, then run the above commands using “sudo” for root privileges 
    * Use exit command (to return to your regular user)
    * Linux users move directly to the :ref:`connecting-rk` section

.. _linux-connectingrk:

Connecting to RecordsKeeper Blockchain on Linux
-----------------------------------------------

The RecordsKeeper Testnet blockchain is available for users to develop and deploy applications on. XRK Testnet tokens do not hold any value and are only available for testing. You can earn XRK tokens from RecordsKeeper Mainnet mining.

Now, to connect to the RecordsKeeper blockchain, run the following command from the terminal:

**RecordsKeeper Testnet**

.. code-block:: bash

    rkd recordskeeper-test@35.170.155.89:8379

**RecordsKeeper Mainnet**

.. code-block:: bash

    rkd recordskeeper@35.172.1.247:7895


This command will initialize your node.

And, if you want your connection to remain active as a background process then run this command:

**RecordsKeeper Testnet**

.. code-block:: bash

    rkd recordskeeper-test@35.172.1.247:8379 -daemon

**RecordsKeeper Mainnet**

.. code-block:: bash

    rkd recordskeeper@35.172.1.247:7895 -daemon

.. note::
    Linux users can now go to the :ref:`mining-permissions` section.

.. _linux-miningpermissions:

Mining Permissions
------------------

Running RecordsKeeper on Linux
##############################

You will see the following message on your Linux command line terminal after you execute the command to connect to the RecordsKeeper blockchain.

.. image:: _static/LinuxRKD.jpg
   :align: center
   :width: 693.433px

RecordsKeeper Permissions
#########################

**RecordsKeeper Testnet**

The mining for RecordsKeeper Testnet is open for everyone, so when you connect to RecordsKeeper Testnet, you will receive all the permissions for your default address

**RecordsKeeper Mainnet**

For Mainnet, when your node gets connected, you will receive the permissions to connect, send, and receive. Now look for your default XRK address from the command given below, which will display your node’s wallet address. This address is your “default XRK address” or “public address” on the RecordsKeeper blockchain in which you will receive XRK tokens. To check the address, run the following command:

.. code-block:: bash

    rk-cli recordskeeper getaddresses

**Submit the following to receive mining permissions for RecordsKeeper Mainnet.**

.. note::
    Copy the above generated address and send it to us `here <https://docs.google.com/forms/d/e/1FAIpQLSd1Dd2GAggCyom23HgiBhnQIjlLjMgRwf_UOQrHp9BUTRPEYA/viewform>`_ .

Only after the RecordsKeeper team grant mining permissions to your node address will you be able to mine XRK tokens into your default address.

To retreive the private key for your node address, run this command:

.. code-block:: bash

    rk-cli recordskeeper dumpprivkey {default_XRK_address}        #(input node_address without braces)


.. note::
    Please store this private key safely. Losing it will result in the loss of XRK tokens.


After completing the above process, you can check for your node’s information (best block and synced block) by running the following commands:

.. code-block:: bash

    rk-cli recordskeeper getinfo                 #(for synced block)
    rk-cli recordskeeper getblockchaininfo       #(for best block)


Your node will sync with the best block, and then only your node can start mining and your balance will get updated with the mined XRK tokens.

If you have entered the wrong IP-address, then it will report this error:

.. warning::

    Error: Couldn't initialize permission database for blockchain recordskeeper. Probably rkd for this blockchain is already running. Exiting...

Please check the IP address and port properly to connect to the RecordsKeeper blockchain.

.. note::

    If you have already created a wallet address and you want to add it as your miner address then run this command from the command line terminal:
    
    .. code-block:: bash

        rk-cli recordskeeper importprivkey {private_key}      #(include private key without braces)

.. _linux-startrkaftermining:

Connecting to RecordsKeeper Blockchain after Permissions
--------------------------------------------------------

Once the permissions for the RecordsKeeper Mainnet have been granted, you can directly connect to the RecordsKeeper chain and see your mining progress. You can run the following commands to connect to the RecordsKeeper blockchain and view the mining address.

As the IP configuration was already stored with you when you intiated the connection, you can directly run the following command:

.. code-block:: bash

    rkd recordskeeper -daemon

.. image:: _static/LinuxRKAfterMining.png
   :align: center

You can run getinfo command or getaddressbalances command to see the balance in your node or directly the node address.

.. code-block:: bash

    rk-cli recordskeeper getinfo

.. image:: _static/LinuxGetInfoMining.png
   :align: center
   :width: 693.433px

.. note::

    You can view your balances in the balance output of the getinfo command.

OR

.. code-block:: bash

    rk-cli recordskeeper getaddressbalances <Your Node Address Given for Mining>

.. image:: _static/LinuxAddressBalancesAfterMining.png
   :align: center
   :width: 693.433px

.. note::

    Please do not use the address specified above. This address is only available for the demo purpose.


.. _linux-stoprk:

Stopping RecordsKeeper Blockchain
---------------------------------

**RecordsKeeper Mainnet**

    In case you want to stop your running RecordsKeeper node, you can use the following command from your command line terminal:


    .. code-block:: bash

        rk-cli recordskeeper stop


**RecordsKeeper Testnet**

    In case you want to stop your RecordsKeeper-test blockchain node, you can use the following command from your command line terminal:


    .. code-block:: bash

        rk-cli recordskeeper-test stop