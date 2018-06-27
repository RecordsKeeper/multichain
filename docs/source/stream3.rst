==================
Stream Class Usage
==================

Library to work with RecordsKeeper streams.

You can publish, retrieve and verify stream data by using Stream class. You just have to pass parameters to invoke the pre-defined functions of Stream class.

Libraries
---------

Import these python libraries first to get started with the functionality.

.. code-block:: python

    import requests
    import json
    from requests.auth import HTTPBasicAuth
    import yaml
    import binascii
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

Stream Class
------------

.. class:: Stream

Stream class to call stream related functions like publish, retrievewithtxid, retrieveWithAddress, retrieveWithKey and verify data functions which are used to publish data into the stream, retrieve data from the stream and verify data from the stream. 

**1. Publish**

You have to pass these four arguments to the publish function call:

* Data Hex of the data to be published
* Address of the publihser
* Stream to which you want your data to be published
* key Value for the data to be published


The **data.hex()** will convert the data into a hex value

.. code-block:: python

    publish(address, stream, key, data)   

    txid = publish(address, stream, key, data)    

    print txid    #prints the transaction id of the data published

It will return the transaction id of the published data, use this information to retrieve the particular data from the stream.


**2. Retrieve an existing item from a particular stream against a transaction id**

You have to pass these two arguments to the retrieve function call:

* Stream name: which you want to access
* Transaction id: id of the data you want to retrieve

.. code-block:: python

    retrieve(stream, txid)          #call retrieve function with stream and txid as the required parameters
    result = retrieve(stream, txid) 
  
    print result    #prints info of the transaction 

It will return the item's details like publisher address, key value, confirmations, hexdata and transaction id.


**3. Retrieve an item against a particular publisher address**

You have to pass these three arguments to the retrieveWithAddress function call:

* Stream name: which you want to access
* Publisher address: address of the data publisher you want to verify
* Count: no of items you want to retrieve

.. code-block:: python

    retrieveWithAddress(stream, address, count)
    result = retrieveWithAddress(stream, address, count)

    print result['key']      #prints key value of the data
    print result['txid']     #prints transaction id of the data
    print result['data']     #prints raw data 

It will return the key value, raw data and transaction id of the published item.

**4. Retrieve an item against a particular key value**

You have to pass these three arguments to the retrieveWithKey function call:

* Stream name: which you want to access
* Key: key value of the published data you want to verify
* Count: no of items you want to retrieve

.. code-block:: python

    retrieveWithKey(stream, key, count)
    result = retrieveWithKey(stream, key, count)

    print result['publisher']    #prints publisher's address of the published data
    print result['txid']         #prints transaction id of the data
    print result['data']         #prints raw data 

It will return the key value, raw data and transaction id of the published item.

**5. Verify an data item on a particular stream of RecordsKeeper Blockchain**

You have to pass these three arguments to the retrieveWithKey function call:

* Stream name: which you want to access
* Data: against which you want to make a query
* Count: count of items which will be queried

.. code-block:: python

    verifyData(stream, data, count)
    result = verifyData(stream, data, count)

    print result                #prints if verification is successful or not

It will return the result if verification is successful or not.


**6. Retrieve data items on a particular stream of RecordsKeeper Blockchain**

You have to pass these two arguments to the verifyWithKey function call:

* Stream name: which you want to access
* Count: count of items which will be queried

.. code-block:: python

    retrieveItems(stream, count)
    result = retrieveItems(stream, count)

    print result['address']    #prints address of the publisher of the item
    print result['key']        #prints key value of the stream itme
    print result['data']       #prints raw data published
    print result['txid']       #prints transaction id of the item published 

It will return the address, key value, data and transaction id of the stream item published.