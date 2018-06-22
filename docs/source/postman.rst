============================
Getting Started with Postman
============================

This tutorial requires you to setup a RecordsKeeper blockchain and run the APIs through the Postman client. If you have not done so already, please download and install RecordsKeeper on a server. If you are using the RecordsKeeper blockchain on Windows, please read the Installation of Windows notes to adapt the instructions below.

Download the latest `RecordsKeeper <https://github.com/RecordsKeeper/recordskeeper-core/releases>`_ build and put the downloded files under the root folder. You can also run these commands from the folder where the files are present.

Download the `Postman client <https://www.getpostman.com/apps>`_ from here.

Postman client Settings
-----------------------

Set the following parameters to request JSON RPC commands for RecordsKeeper.

Request-type
############

Select POST method in Postman client for using RecordsKeeper JSON RPC APIs.

Endpoint
########

Enter the following endpoint in the url:

.. code-block:: bash

		35.170.155.89:8378/


Authorization
#############

To setup authorization parameters, first select the type of Authentication to: **Basic Auth**. You have to enter the username and password for your node for authorization, which you can access through rk.conf built in your recordskeeper directory.


**Linux (Ubuntu):**

From your terminal run following commands:

.. code-block:: bash

		cd ~/.rk/recordskeeper/
		cat rk.conf

It will open the configuration file from where you can copy rpcuser and rpcpassword for your node. Enter these in username and password textbox of the postman client.

**Windows:**

Go to the directory:

.. code-block:: bash

		AppData > Roaming > Rk > recordskeeper

Then look for the rk.conf file and open it in any text editor. It will display rpcuser and rpcpassword for your node. Enter these in username and password textbox of the postman client.


Headers
#######

Headers are used to specify the metadata for the request type. It is a key-value based entry. Enter the following key-value entries in your header:

.. code-block:: bash

		Content-type : application/json
		Cache-control : no-cache

Body
####

Select the **Raw** type in your request. The Post API request will be in the following format, which is to be added inside the body of the request:

.. code-block:: bash

		{"method":"method_name","params":[],"id":1,"chain_name":"recordskeeper-test"}

.. image:: _static/Postman-request.png
   		:align: center
   		:width: 693.433px

Running API Commands through Postman
------------------------------------

Now your Postman client is set up and running, so you can use JSON RPC API commands to extract information, send transactions, and publish data over the RecordsKeeper node. Some of the important requests are as follows:

* Get general information about the RecordsKeeper node:

.. code-block:: bash

	{"method":"getinfo","params":[],"id":1,"chain_name":"recordskeeper-test"}

The following result will be displayed:

.. image:: _static/getinfo.png
   			:align: center
   			:width: 693.433px


* Create a new address in the RecordsKeeper Node wallet:

.. code-block:: bash

	{"method":"getnewaddress","params":[],"id":1,"chain_name":"recordskeeper-test"}

The following result will be displayed:

.. image:: _static/getnewaddress.png
   			:align: center
   			:width: 693.433px


* List all addresses in the RecordsKeeper node wallet:

.. code-block:: bash

	{"method":"getaddresses","params":[],"id":1,"chain_name":"recordskeeper-test"}

The following result will be displayed:

.. image:: _static/getaddresses.png
   			:align: center
   			:width: 693.433px


Sending a Transaction in RecordsKeeper
--------------------------------------

The RecordsKeeper blockchain works on the same backend as Bitcoin algorithms. Both the RecordsKeeper Testnet and Mainnet can be used to send and receive XRK tokens. Use the following API commands to send transactions on the RecordsKeeper blockchain.

Send
####

.. code-block:: bash
  
	{"method":"send","params":["1KJFg5YLpvYNYZtCM6hhNYW8uBKtc3GHVboXco", 10],"id":1,"chain_name":"recordskeeper-test"}

The following result will be displayed:

.. image:: _static/send.png
   			:align: center
   			:width: 693.433px

This command is used to send one or more XRK tokens to an address, returning the txid. The amount field is the quantity of XRK tokens and the address field is the address where you want to send the XRK tokens. This command will use the node's root address to send the transaction. Please make sure you have sufficient balance in the node's root address for transactions to propagate over the RecordsKeeper blockchain. You can also provide specific comments for the transaction, which are optional. The fees will be applied as per the transaction size.



Send from a Different Address
#############################

.. code-block:: bash

	{"method":"sendfrom","params":["17gddiicYtbnwnWuY2ZYvM1Rw9e7t3pPjNJPab","1KJFg5YLpvYNYZtCM6hhNYW8uBKtc3GHVboXco", 10],"id":1,"chain_name":"recordskeeper-test"}


The following result will be displayed:

.. image:: _static/sendfrom.png
   			:align: center
   			:width: 693.433px


This command is also used to send one or more XRK tokens to an address, returning the txid. Using this command you can specify the from-address which you want to use to send the transaction. The amount field is the quantity of XRK tokens, and the to-address field is the address where you want to send the XRK tokens. Please make sure you have sufficient balance in the from-address for transactions to propagate over the RecordsKeeper blockchain. The from-address used here is also one of the addresses generated for the node. You can also provide specific comments for the transaction which are optional. The fees will be applied as per the transaction size.


Publishing and Retrieving Data in RecordsKeeper
-----------------------------------------------

The RecordsKeeper blockchain is a public key-value based database on the blockchain. You can use the interactive command line to publish and retrieve stored information. As the blockahin is a shared concept, you can view all the published data and retrieve it using only a key or address. RecordsKeeper uses the streams to store the data. RecordsKeeper streams provide a natural abstraction for RecordsKeeper blockchain, which focus on general data retrieval, timestamping, and archiving, rather than the transfer of tokens between participants.

The "root" stream is open to all and anyone can publish data into the root stream. The following commands will give you a brief introduction about how to work with the data over RecordsKeeper blockchain.

Publish
#######

.. code-block:: bash

	{"method":"publish","params":["root","rkkey", "57687920796f7520636f6e766572746564206d653f"],"id":1,"chain_name":"recordskeeper-test"}

The following result will be displayed:

.. image:: _static/publish.png
   			:align: center
   			:width: 693.433px


This command publishes an item in a stream. The stream name is passed, with the key provided in text form and a data-hex in hexadecimal format. It returns ref or creation txid. The data is published using the node’s address. Use the next command discussed below to publish data from different address. The mining fees are applied as per the transaction size.

Publish from a Different Address
################################

.. code-block:: bash

	{"method":"publishfrom","params":["17gddiicYtbnwnWuY2ZYvM1Rw9e7t3pPjNJPab","root","rkkey", "57687920796f7520636f6e766572746564206d653f"],"id":1,"chain_name":"recordskeeper-test"}

The following result will be displayed:

.. image:: _static/publishfrom.png
   			:align: center
   			:width: 693.433px

This command works like publish, but publishes the item from the from-address. It is useful if the node has multiple addresses with different amounts. The mining fees are applied as per the transaction size.

Send as a Transaction
#####################

.. code-block:: bash

    {"method":"sendwithdata","params":["1KJFg5YLpvYNYZtCM6hhNYW8uBKtc3GHVboXco",10, "57687920796f7520636f6e766572746564206d653f"],"id":1,"chain_name":"recordskeeper-test"}

The following result will be displayed:

.. image:: _static/sendwithdata.png
   			:align: center
   			:width: 693.433px


This works similarly to send, but with an additional data-only transaction output. You can pass raw data as data-hex hexadecimal string. It is also used to publish the data to a stream, pass an object like this {“for”:StreamName,”key”:”KeyName”,”data”:”DataHex”} where stream is a stream name, ref, or creation txid, the key is in text form, and the data is hexadecimal. You can pass the amount as 0, if you are only using this to publish the data over the RecordsKeeper stream. You can also send some XRK tokens while publishing the data over the stream. The fees will be applied as per the transaction size.

.. note::
   The address displayed here is a demo address. Please don't use this address in your transactions. You can create a new wallet or address by using the `RecordsKeeper Wallet <https://wallet.recordskeeper.co/>`_