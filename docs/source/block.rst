=================
Block Class Usage
=================

Library to work with RecordsKeeper block informaion.

You can collect block information like block's transaction count, blocktime, blockhash, miner of the block by using block class. You just have to pass parameters to invoke the pre-defined functions of Block class.

Libraries
---------

Import these python libraries first to get started with the functionality.

.. code-block:: python

    import requests
    import json
    from requests.auth import HTTPBasicAuth
    import yaml
    import sys


Creating Connection
-------------------

Entry point for accessing Address class resources.

* URL: Url to connect to the chain ([RPC Host]:[RPC Port])
* Chain-name: chain name

.. code-block:: python
    
    with open("config.yaml", 'r') as ymlfile:
        cfg = yaml.load(ymlfile)

.. code-block:: python

    network = cfg['network']  #network variable to store the network that you want to access


.. code-block:: python 

    url = network['url']
    chain = network['chain']


Node Authentication
-------------------

Importing values from config file.

* User name: The rpc user is used to call the APIs.
* Password: The rpc password is used to authenticate the APIs.

Default value of network is **Test-net**, you can change its value to select mainnet or testnet

.. code-block:: python
    
    user = network['rkuser']
    password = network['passwd']

Now we have node authentication credentials.


Block Class
-----------

.. class:: Block

    Block class is used to call block related function like blockinfo which is used to retrieve block details like block's hash value, size, nonce, transaction ids, transaction count, miner address, previous block hash, next block hash, merkleroot, blocktime and difficulty of the block for which you have made the query.

**1. Block info to retrieve block information**

You have to pass block height as the argument to the blockinfo function call:

* Block height: height of the block of which you want to collect info

.. code-block:: python

    blockinfo(block_height)
    result = blockinfo(block_height)

    print result['txcount']      #prints transaction count of the block
    print result['tx']           #prints transaction ids of the block
    print result['size']         #prints size of the block
    print result['blockhash']    #prints hash value of the block
    print result['nonce']        #prints nonce of the block
    print result['miner']        #prints miner's address of the block
    print result['nextblock']    #prints next block's hash
    print result['prevblock']    #prints previous block's hash
    print result['merkleroot']   #prints merkle root of the block
    print result['blocktime']    #prints time at which block is mined
    print result['difficulty']   #prints difficulty of the block

It will return transaction ids, transaction count, nonce, size, hash value, previous block's hash value, next block hash value, merkle root, difficulty, blocktime and miner address of the block.


**2. Retrieve a range of blocks on RecordsKeeper chain**

You have to pass range of blocks i.e. blockrange can be 10-15. It can be passed as the argument to the retrieveBlocks function call:

* Block range: range of the block of which you want to collect info

. code-block:: python

    . code-block:: python

    retrieveBlocks(block_range)
    result = retrieveBlocks(block_range)

    print result['blockhash']    #prints hash of the blocks
    print result['miner']        #prints miner of the blocks
    print result['blocktime']    #prints block time of the blocks
    print result['tx count']     #prints transaction count of the blocks

It will return blockhash, miner address, blocktime and transaction count of the blocks.
