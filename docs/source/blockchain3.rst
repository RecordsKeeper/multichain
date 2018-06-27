======================
Blockchain Class Usage
======================

Library to work with Blockchain class in RecordsKeeper Blockchain.

You can get chain information, node information, node's permissions, pending transaction information and node balance by using Blockchain class. You just have to pass parameters to invoke the pre-defined functions of Blockchain class.

Libraries
---------

Import these python libraries first to get started with the functionality.

.. code-block:: python

    import requests
    import json
    from requests.auth import HTTPBasicAuth
    import yaml
    import sys
    import binascii


Creating Connection
-------------------

Entry point for accessing Address class resources.

* URL: Url to connect to the chain ([RPC Host]:[RPC Port])
* Chain-name: chain name

.. code-block:: python
    
    with open("config.yaml", 'r') as ymlfile:
        cfg = yaml.load(ymlfile)

.. code-block:: python

    network = cfg['network']                    #network variable to store the network that you want to access


.. code-block:: python 

    url = network['url']
    chain = network['chain']


Node Authentication
-------------------

Importing values from config file.

* User name: The rpc user is used to call the APIs.
* Password: The rpc password is used to authenticate the APIs.

.. code-block:: python
    
    user = network['rkuser']
    password = network['passwd']

Now we have node authentication credentials.

Blockchain Class
----------------

.. class:: Blockchain

Blockchain class is used to call blockchain related functions like retrieving blockchain parameters, retrieving node's information, retrieving mempool's information, retrieving node's permissions and check node's balance functions which are used on the RecordsKeeeper Blockchain. 


**1. Retrieve Blockchain parameters of RecordsKeeper Blockchain**

getChainInfo() function is used to retrieve Blockchain parameters.

.. code-block:: python

    getChainInfo()  

    result = getChainInfo()                 #getChainInfo() function call   

    print result['chain-protocol']          #prints blockchain's protocol
    print result['chain-description']       #prints blockchain's description
    print result['root-stream-name']        #prints blockchain's root stream
    print result['maximum-blocksize']      #prints blockchain's maximum block size
    print result['default-network-port']    #prints blockchain's default network port
    print result['default-rpc-port']        #prints blockchain's default rpc port
    print result['mining-diversity']        #prints blockchain's mining diversity
    print result['chain-name']              #prints blockchain's name

It will return the information about RecordsKeeper blockchain's parameters.


**2. Retrieve node's information on RecordsKeeper Blockchain**

getNodeInfo() function is used to retrieve node's information on RecordsKeeper Blockchain.

.. code-block:: python

    getNodeInfo()  
    result = getNodeInfo()       #getNodeInfo() function call
  
    print result['node balance']      #prints balance of the node
    print result['synced blocks']      #prints no of synced blocks
    print result['node address']      #prints node's address
    print result['difficulty']      #prints node's difficulty 

It will return node's balance, no of synced blocks, node's address and node's difficulty.


**3. Retrieve permissions given to the node on RecordsKeeper Blockchain**

permissions() function is used to retrieve node's permissions. 

.. code-block:: python

    permissions()  
    allowed_permissions = permissions()                #permissions() function call 
  
    print allowed_permissions      # prints permissions available to the node

It will return the permissions available to the node.


**4. Retrieve pending transaction's information on RecordsKeeper Blockchain**

getpendingTransactions() function is used to retrieve pending transaction's information like no of pending transactions and the pending transactions. 

.. code-block:: python

    getpendingTransactions() 
    result = getpendingTransactions(address)   #getpendingTransactions() function call
    
    print result['tx']              #prints pending transactions
    print result['tx_count']        #prints pending transaction count

It will return the information of pending transactions on Recordskeeper Blockchain.


**5. Check node's total balance**

checkNodeBalance() function is used to check the total balance of the node. 

.. code-block:: python

    checkNodeBalance()
    node_balance = checkNodeBalance()     #checkNodeBalance() function call
  
    print node_balance          #prints total balance of the node

It will return the total balance of the node on RecordsKeeper Blockchain.

