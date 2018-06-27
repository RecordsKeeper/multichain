==================
Assets Class Usage
==================

Library to work with RecordsKeeper assets.

You can create new assets, send assets and list all assets by using Assets class. You just have to pass parameters to invoke the pre-defined functions of Assets class.

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

    network = cfg['network']  #network variable to store the network that you want to access


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

Assets Class
------------

.. class:: Assets

Assets class is used to call assets related functions like create assets and list assets functions which are used on the RecordsKeeeper Blockchain. 


**1. Create Assets on the RecordsKeeper Blockchain**

createAsset() function is used to create or issue an asset.

.. code-block:: python

    createAsset(address, asset_name, asset_qty)  

    txid = createAsset(address, asset_name, asset_qty)          #createAsset() function call   

    print txid                  # prints transaction id of the issued asset

It will return the transaction id of the issued asset.

**2. Send Assets to a particular address on the RecordsKeeper Blockchain**

You have to pass these three arguments to the createAsset function call:

* address: address which will send the asset
* asset_name: name of the asset
* qty: quantity of asset to be sent

sendAsset() function is used to send an asset.

.. code-block:: python

    sendAsset(address, assetname, qty)  

    txid = sendAsset(address, assetname, qty)              #sendAsset() function call   

    print txid                  # prints transaction id of the sent asset

It will return the transaction id of the sent asset.

**3. List all assets on the RecordsKeeper Blockchain**

retrieveAssets() function is used to list all assets, no of assets, issued quantity and issued transaction id of all the assets on RecordsKeeper Blockchain.

.. code-block:: python

    retrieveAssets()  
    result = retrieveAssets()       #retrieveAssets() function call
  
    print result['name']            #prints name of all the assets
    print result['asset count']     #prints total asset count
    print result['id']              #prints assets issued quantity
    print result['qty']             #prints assets issued transaction id

It will return all the assets, the count of the assets, issued quantity of assets and issued transaction id of the asset on the RecordsKeeper Blockchain.


