==================
Wallet Class Usage
==================

Library to work with RecordsKeeper wallet class.

You can create wallet, dump wallet into a file, backup wallet into a file, import wallet from a file, lock wallet, unlock wallet, change wallet's password, retrieve private key, retrieve wallet's information, sign and verify message by using wallet class. You just have to pass parameters to invoke the pre-defined functions.

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

Wallet Class
------------

.. class:: Wallet

Wallet class is used to call wallet related functions like create wallet, retrieve private key of wallet address, retrieve wallet's information, dump wallet, lock wallet, unlock wallet, change wallet's password, create wallet's backup, import wallet's backup, sign message and verify message functions on RecordsKeeeper Blockchain. 


**1. Create wallet on RecordsKeeper blockchain**

createWallet() function is used to create wallet on RecordsKeeper blockchain

.. code-block:: python

    createWallet()  

    result = createWallet()   

    print result['public address']        #prints public address of the wallet
    print result['private key']           #prints private key of the wallet
    print result['public key']            #prints public key of the wallet

It will return the public address, public key and private key.


**2. Retrieve private key of an address**

You have to pass address argument to the getPrivateKey function call:

* Public Address: address whose private key is to be retrieved

getPrivateKey() function is used to retrieve private key of the given address.

.. code-block:: python

    getPrivateKey(public_address)  
    privkey = getPrivateKey(public_address) 
  
    print privkey        #prints private key of the given address

It will return private key of the given address.


**3. Retrieve node wallet's information**

retrieveWalletinfo() function is used to retrieve node wallet's information. 

.. code-block:: python

    retrieveWalletinfo()  
    result = retrieveWalletinfo() 
  
    print result['balance']      #prints wallet's balance
    print result['tx count']     #prints wallet transaction count
    print result['unspent tx']   #prints unspent wallet transactions

It will return wallet's balance, transaction count and unspent transactions.


**4. Create wallet's backup**

You have to pass these three arguments to the backupWallet function call:

* Filename: wallet's backup file name 

backupWallet() function is used to create backup of the wallet.dat file. 

.. code-block:: python

    backupWallet(filename)  
    result = backupWallet(filename) 
  
    print result      #prints result

It will return the response of the backup wallet function. The backup of the wallet is created in your chain's directory and you can simply access your file by using same filename that you have passed with the backupwallet function. Creates a backup of the wallet.dat file in which the node’s private keys and watch-only addresses are stored. The backup is created in file filename. Use with caution – any node with access to this file can perform any action restricted to this node’s addresses.


**5. Import backup wallet**

You have to pass these three arguments to the importWallet function call:

* Filename: wallet's backup file name  

importWallet() function is used to import wallet's backup file. 

.. code-block:: python

    importWallet(filename)  
    result = importWallet(filename) 
  
    print result    #prints result

It will return the response of the import wallet function. It will import the entire set of private keys which were dumped (using dumpwallet) into file filename. 


**6. Dump wallet on RecordsKeeper blockchain**

You have to pass these three arguments to the dumpWallet function call:

* Filename: file name to dump wallet in

dumpWallet() function is used to retrieve transaction's information by passing transaction id to the function.

.. code-block:: python

    dumpWallet(filename)
    result = dumpWallet(filename)

    print (result)    #prints result
    
It will return the response of the dump wallet function. Dumps the entire set of private keys in the wallet into a human-readable text format in file filename. Use with caution – any node with access to this file can perform any action restricted to this node’s addresses.


**7. Locking wallet with a password on RecordsKeeper Blockchain**

You have to pass password as an argument to the lockWallet function call:

* Password: password to lock the wallet

lockWallet() function is used to verify transaction's information by passing transaction id and sender's address to the function.

.. code-block:: python

    lockWallet(password)
    result = lockWallet(password)

    print (result)     #prints result

It will return the the response of the lock wallet function. This encrypts the node’s wallet for the first time, using passphrase as the password for unlocking. Once encryption is complete, the wallet’s private keys can no longer be retrieved directly from the wallet.dat file on disk, and chain will stop and need to be restarted. Use with caution – once a wallet has been encrypted it cannot be permanently unencrypted, and must be unlocked for signing transactions with the unlockwallet function.


**8. Unlocking wallet with the password on RecordsKeeper Blockchain**

You have to pass these two arguments to the unlockWallet function call:

* Password: password to unlock the wallet 
* unlocktime: seconds for which wallet remains unlock

unlockWallet() function is used to verify transaction's information by passing transaction id and sender's address to the function.

.. code-block:: python

    unlockWallet(password, unlock_time)
    result = unlockWallet(password, unlock_time)

    print (result)      #prints result

It will return the response of the unlock wallet function. This uses passphrase to unlock the node’s wallet for signing transactions for the next timeout seconds. This will also need to be called before the node can connect to other nodes or sign blocks that it has mined.


**9. Change wallet's password**

You have to pass these two arguments to the changeWalletPassword function call:

* Old Password: old password of the wallet
* New Password: new password of the wallet

changeWalletPassword() function is used to change wallet's password and set new password.

.. code-block:: python

    changeWalletPassword(old_password, new_password)
    result = changeWalletPassword(password, new_password)

    print (result)     #prints result

This changes the wallet’s password from old-password to new-password.


**10. Sign Message on RecordsKeeper Blockchain**

You have to pass these two arguments to the signMessage function call:

* Message: message to send
* Private Key: private key of the sender's wallet address

signMessage() function is used to change wallet's password and set new password.

.. code-block:: python

    signMessage(private_key, message)
    signedMessage = signMessage(priavte_key, message)

    print (signedMessage)   #prints signed message

It will return the signed message.


**11. Verify Message on RecordsKeeper Blockchain**

You have to pass these three arguments to the verifyMessage function call:

* Message: message to send
* Private Key: private key of the sender's wallet address

verifyMessage() function is used to change wallet's password and set new password.

.. code-block:: python

    verifyMessage(address, signedMessage, message)
    validity = verifyMessage(address, signedMessage, message)

    print (validity)     #prints validity of the message

It will return the validity of the message.