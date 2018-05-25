==========================
Frequently Asked Questions
==========================

RecordsKeeper FAQ
-----------------

What is RecordsKeeper?
######################

RecordsKeeper is a Open Public Mineable Blockchain for RecordKeeping & Data Security. It can also be seen as an open source platform for private Blockchains, which offers a rich set of features including extensive configurability, rapid deployment, permissions management, native assets and data streams. 

You can publish your data in key-value pair format onto the RecordsKeeper Blockchain.

Is RecordsKeeper a Storage, Database or Blockchain?
###################################################

RecordsKeeper is a key-value pair based database running on Blockchain. It stores every record as a key-value pair as a part of XRK transaction. In another way you can consider it an amalgamation of all the three (Storage, Database & Blockchain) as it offers storage as a Database over the public Blockchain.

How RecordsKeeper is different from traditional storage?
########################################################

Since RecordsKeeper is Public Blockchain it consist of several decentralized nodes (aka Servers) which verify each and every transaction while adding a new Block into the Blockchain. Each node participates in administration: all nodes verify new additions to the blockchain, and are capable of entering new data into the RecordsKeeper. Traditional Database allows the modification of data but with RecordsKeeper Blockchain the data is secured and cannot be tampered, altered or modified once published & confirmed in the RecordsKeeper Blockchain Ledger.


How RecordsKeeper is different from Storj, Filecoin and Siacoin?
################################################################

RecordsKeeper is based on simple mechanism to utilize the transaction size to store your data as compared to other 3rd parties which uses rental of Hard Drives of other users to create a network of storage. RecordsKeeper Blockchain  is based on Key-Value pairs and reduce the overhead to get space from other parties.

How RecordsKeeper is different from Blockchain DB?
##################################################

RecordsKeeper offers an ease of access to the Database. You can use the JSON RPC commands to interact with Blockchain which keeps the RecordsKeeper in line with the Bitcoin Blockchain.

How RecordsKeeper works?
########################

RecordsKeeper allows the user to upload data (in key-value pair format) over the Blockchain with ease and in a single XRK transaction. Users can upload multiple entries in form of key-value pairs but it has to be one pair per transaction. RecordsKeeper is a pubic Blockchain and it also allows the users to retrieve the uploaded data by the users using the key. The cost of Data upload is calculated as per the data size and awarded to the miners in the form of XRK.

What kind of data I can publish on RecordsKeeper?
#################################################

RecordsKeeper allows different format of data ranging from JSON, XML, Hex, Objects to Simple text. Users are allowed to upload data and retrieve upto the maximum size of 2 MB per transaction. Please remember the smaller the data you publish lesse the fees in XRK would be. 


What’s the maximum size of Data I can publish on RecordsKeeper?
###############################################################

RecordsKeeper allows the OP_RETURN transactions of XRK upto 2 MB per transaction and other transactions upto 4 MB. If you are using the Key-Value Database in RecordsKeeper Blockchain then the maximum size allowed is 2 MB per transaction.

Can we upload an entire file on RecordsKeeper?
##############################################

Technically it is possible but it is not recommended. A file can have multiple amount of raw data which will not form the information you need to secure and will cost you a lot in-terms of XRK fees. It is highly recommended to upload the textual juice of the file or record in the structures textual data like JSON/XML. In any case the max size of record published can be upto the maximum size of 2 MB per XRK transaction. Alternatively, If you wish to upload files much much larger like 5 GB etc. then you can upload the hash of the file over the RecordsKeeper Blockchain to publish the proof-of-existence, proof-of-integrity tec. or contact us for further assistance.

What are the Blockchain specifications for RecordsKeeper?
#########################################################

The RecordsKeeper specifications are as follows:

* Avg Block Size: 250 bytes
* Max Block Size: 8 MB
* Avg Block Frequency: 15 seconds
* Mining Algorithm: POW 
* Premined Tokens: 300 Million XRK
* Mining Reward: 10 XRK
* Max Transaction Size: 4 MB
* Max OP_RETURN Transaction Size: 2 MB

What is the maximum Block size for RecordsKeeper Blockchain?
############################################################

The maximum Block size allowed for the RecordsKeeper Blockchain is 8 MB (8388608 bytes)

How many tx/sec RecordsKeeper can confirm?
##########################################

The minimum average size of transaction in RecordsKeeper is 250 bytes and the maximum size of Block is 8 MB (8388608 bytes). Thus you can have upto 33554 transactions per Block on an average. The average Block time is 15 seconds. So you can have upto 2236 transactions/sec. But this is considering if we have all the smallest size transaction. If the transaction size are higher this number can go down.

What are the use cases of RecordsKeeper?
########################################

There are several use cases for RecordsKeeper ranging from KYC verifications, Supplychain, Manufacturing, Health Record Management, Academic Certifications, Employment Credentials, etc. You can view all the use cases at `RecordsKeeper whitepaper <https://www.recordskeeper.co/wp-content/uploads/2016/11/rk_whitepaper.pdf>`_ . 

Is data uploaded in RecordsKeeper encrypted by default?
#######################################################

No, the data uploaded on RecordsKeeper is not encrypted by default. If you wish to encrypt the data to make it available on Blockchain while keeping it private then you can always encrypt it in your application layer. This will ensure the immutability as well as privacy.


Who can retrieve published records?
###################################

Anyone, who have key or the transaction ID of the published records can retrieve data. You can also retrieve records sent to a specific address over the RecordsKeeper Blockchain using Blockchain Explorer or it’s native APIs.

How to verify published records?
################################

To verify the the published records you can get the data using the key from RecordsKeeper Blockchain then compare it with you local stored record. If both the records matches exactly then your records integrity, immutability has been maintained in your local storage. If it is not then it clearly means that someone has tampered the local records.

What is the cost of publishing records?
#######################################

The current fees for publishing records is 0.1 XRK/KByte of data. This can vary as per the supply and demand.

Mining FAQ
----------

Can I mine XRK?
###############

Yes, anyone can become a miner with RecordsKeeper. You need to send us your mining address for permissions and than you can start mining. You can follow the mining guide for further instructions here. (Link to mining guide).

How can I mine XRK?
###################

Follow mining guide instructions from (Link to mining guide) to start mining XRK.

What are the minimum hardware requirements for XRK mining?
##########################################################

Anyone with a personal laptop/computer can enable the mining for XRK. The minimum system requirements are as follows:

* Linux: 64-bit, supports Ubuntu 12.04+, CentOS 6.2+, Debian 7+, Fedora 15+, RHEL 6.2+.
* Windows: 64-bit, supports Windows 7, 8, 10, Server 2008 or later.
* Mac: 64-bit, supports OS X 10.12 (we hope to support earlier versions soon).
* 512 MB of RAM
* 1 GB of disk space


XRK FAQ
-------

What is XRK?
############

XRK are the tokens used in RecordsKeeper Blockchain as an incentive & payment model for uploading the records in open Blockchain. XRK behave as a fees for uploading the records over the RecordsKeeper Blockchain.

What is the use of XRK?
#######################

The main purpose of XRK is upload records over the RecordsKeeper Blockchain. Our Blockchain compute the some fees over the records uploaded and award that fees to miner who confirm the transaction carrying the data. 

What is the value of XRK?
#########################

The current value of XRK is 1 BTC (Bitcoin) = 20,000 XRK. This value is subject to change as per the supply and demand.

How XRK are generated?
######################

The premined XRK coins are in total 300 million which you can buy and use for RecordsKeeper. You can also generate and earn more XRK through mining. Refer the mining guide to set up the mining for XRK (Link to mining guide)

Can XRK tokens be destroyed or burned?
######################################

XRK can not be destroyed or burned. However, you can send XRK to a NOP_RETURN transaction thus making unspendable for further transactions.

How many total XRK are in circulation?
######################################

The premined XRK coins are in total 300 Million. This value keeps on increasing as more XRK coins are added through mining rewards which is 10 XRK per Block

How can I get Testnet XRK?
##########################

Testnet XRK are available for the community to build and deploy applications over the RecordsKeeper. You can get Testnet XRK through `RecordsKeeper faucet <https://faucet.recordskeeper.co/>`_ .


Do I need to buy XRK for demo?
##############################

RecordsKeeper Demo provides the new users with 1 XRK coin over Mainnet which can be used to publish the transaction over RecordsKeeper Blockchain. The maximum size of Data which can be published is based upon the fees. If you want to publish large data, you need to buy more XRK coins. To buy the XRK please contact us here.

Who gets the XRK which are spend as transaction fees?
#####################################################

The miner who confirms the transaction gets the XRK spent in transaction fees.

Where XRK is listed on Exchange?
################################

We have not been listed in any exchange as of now. However, we are in talk with multiple exchanges for the same. Please subscribe our news letter to get updates on Exchange listing.

How can I get XRK in bulk?
##########################

To buy XRK in bulk you can contact us here.

