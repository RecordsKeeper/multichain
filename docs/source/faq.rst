==========================
Frequently Asked Questions
==========================

RecordsKeeper FAQ
-----------------

What is RecordsKeeper?
######################

RecordsKeeper is a public, mineable blockchain for record keeping & data security. It can also be seen as an open-source platform for private blockchains, which offers a rich set of features including extensive configurability, rapid deployment, permissions management, native assets, and data streams. 

You can publish your data in key-value pair format on the RecordsKeeper blockchain.

Is RecordsKeeper a storage, database, or blockchain?
####################################################

RecordsKeeper is a key-value pair based database running on blockchain. It stores every record as a key-value pair as a part of XRK transactions. Alternatively, you can regard it as an amalgamation of all three (storage, database and blockchain) as it offers storage as a database on the public blockchain.

How is RecordsKeeper different from traditional storage systems?
################################################################

Since RecordsKeeper is a public blockchain, it consists of several decentralized nodes (aka servers) which verify each and every transaction while adding new blocks into the blockchain. Each node participates in administration: all nodes verify new additions to the blockchain, and are capable of entering new data into RecordsKeeper. Traditional databases allow the modification of data, but with the RecordsKeeper blockchain the data is secured and cannot be tampered with, altered, or modified once published and confirmed in the RecordsKeeper blockchain ledger.


How is RecordsKeeper different from Storj, Filecoin, and Siacoin?
#################################################################

RecordsKeeper is based on a simple mechanism to utilize transaction size to store data as compared to other 3rd parties which uses the rental of other user's hard drives to create a network of storage. RecordsKeeper blockchain is based on key-value pairs, which reduces the need to source storage space from other parties.

How is RecordsKeeper different from Blockchain DB?
##################################################

RecordsKeeper offers ease of access to the database. You can use the JSON RPC commands to interact with the blockchain, which keeps RecordsKeeper in line with the Bitcoin blockchain.

How does RecordsKeeper work?
############################

RecordsKeeper allows the user to upload data (in key-value pair format) onto the blockchain with ease and in a single XRK transaction. Users can upload multiple entries in the form of key-value pairs, but it has to be one pair per transaction. RecordsKeeper is a public blockchain, and it also allows users to retrieve their uploaded data by the use of a key. The cost of data upload is calculated as per the data size and awarded to the miners in the form of XRK.

What kind of data can I publish on RecordsKeeper?
#################################################

RecordsKeeper allows different data formats, ranging from JSON, XML, Hex, or Objects, to Simple text. Users are allowed to upload data and retrieve data up to the maximum size of 2 MB per transaction. Please remember that the
fees in XRK are determined by how much data you upload.

What’s the maximum amount of data I can publish on RecordsKeeper?
#################################################################

RecordsKeeper allows OP_RETURN transactions of XRK up to 2 MB per transaction and other transactions up to 4 MB. If you are using the key-value database in RecordsKeeper blockchain, then the maximum size allowed is 2 MB per transaction.

Can I upload an entire file on RecordsKeeper?
#############################################

Technically, it is possible but it is not recommended. A file can have a large amount of raw data which does not necessarily need to be kept secure and may cost you a lot in terms of XRK fees. It is highly recommended to upload the textual juice of the file or record in the structures textual data like JSON/XML. In any case, the maximum size of published records can be up to 2 MB per XRK transaction. Alternatively, if you wish to upload larger files upto 5 GB in size, then you can upload the hash of the file over the RecordsKeeper blockchain to publish the proof-of-existence, proof-of-integrity tec. or contact us for further assistance.

What are the blockchain specifications for RecordsKeeper?
#########################################################

The RecordsKeeper specifications are as follows:

* Avg. Block Size: 250 bytes
* Max Block Size: 8 MB
* Avg. Block Frequency: 15 seconds
* Mining Algorithm: PoW 
* Premined Tokens: 300 million XRK
* Mining Reward: 10 XRK
* Max Transaction Size: 4 MB
* Max OP_RETURN Transaction Size: 2 MB

What is the maximum block size for the RecordsKeeper blockchain?
################################################################

The maximum block size on the RecordsKeeper blockchain is 8 MB (8388608 bytes).

How many confirmed tx/sec can RecordsKeeper achieve?
####################################################

The average size of transactions on the RecordsKeeper blockchain is 250 bytes and the maximum size of a block is 8 MB (8388608 bytes). Thus, you can have up to 33554 transactions per block on average. The average block time is 15 seconds, so you can have up to 2236 transactions/sec if they are all small size transactions. If the transaction sizes are larger, the number of transactions decrease accordingly.

What are the use cases of RecordsKeeper?
########################################

There are several use cases for RecordsKeeper ranging from KYC verifications, supply chain management, manufacturing, health record management, academic certifications, and employment credentials verification. You can view all the use cases in the `RecordsKeeper whitepaper <https://www.recordskeeper.co/wp-content/uploads/2016/11/rk_whitepaper.pdf>`_ . 

Is data uploaded to RecordsKeeper encrypted by default?
#######################################################

No. The data uploaded to RecordsKeeper is not encrypted by default. If you wish to encrypt the data to make it available on blockchain while keeping it private, then you can always encrypt it in your application layer. This will ensure its immutability, as well as its privacy.


Who can retrieve published records?
###################################

Anyone who has the key or the transaction ID of the published records can retrieve the data. You can also retrieve records sent to a specific address on the RecordsKeeper blockchain using Blockchain Explorer or its native APIs.

How can I verify published records?
###################################

To verify published records, you can access the data using the key from the RecordsKeeper blockchain, and then compare it with your locally stored record. If both the records match exactly, then your record's integrity and immutability has been maintained in your local storage. If they do not, then it clearly means that someone has tampered with the local records.

What is the cost of publishing records?
#######################################

The current fee for publishing records is 0.1 XRK/KB of data. This can vary due to supply and demand.

Mining FAQ
----------

Can I mine XRK?
###############

Yes. Anyone can become a miner with RecordsKeeper. You need to send us your mining address for permissions, and then you can start mining. You can follow the mining guide for further instructions here. (Link to mining guide).

How can I mine XRK?
###################

Follow the mining guide instructions from (Link to mining guide) to start mining XRK.

What are the minimum hardware requirements for XRK mining?
##########################################################

Anyone with a personal laptop/computer can begin mining for XRK. The minimum system requirements are as follows:

* Linux: 64-bit, supports Ubuntu 12.04+, CentOS 6.2+, Debian 7+, Fedora 15+, RHEL 6.2+.
* Windows: 64-bit, supports Windows 7, 8, 10, Server 2008 or later.
* Mac: 64-bit, supports OS X 10.12 (we hope to support earlier versions soon).
* 512 MB of RAM
* 1 GB of disk space


XRK FAQ
-------

What is XRK?
############

XRK is the name (or ticker) of the tokens which are used as an incentive and payment model for uploading records and data onto the RecordsKeeper blockchain. XRK tokens are used as fees for uploading the records over the RecordsKeeper blockchain.

What is the use of XRK?
#######################

XRK tokens are used to upload records over the RecordsKeeper blockchain. The Blockchain computes the required fees for the uploaded records and awards those fees to miners who confirm the transaction carrying the data. 

What is the value of XRK?
#########################

The current value of XRK is 1 BTC (Bitcoin) = 20,000 XRK. This value is subject to change as per supply and demand.

How are XRK generated?
######################

The premined XRK tokens are in total 300 million which you can buy and use for RecordsKeeper. You can also generate and earn more XRK through mining. Refer the mining guide to set up the mining for XRK (Link to mining guide)

Can XRK tokens be destroyed or burned?
######################################

XRK cannot be destroyed or burned. However, you can send XRK to a NOP_RETURN transaction thus making them ‘un-spendable’ for further transactions.

How many total XRK tokens are in circulation?
#############################################

There are 300 million premined XRK tokens in total 300. Their value keeps increasing as more XRK tokens are added through mining rewards, which are 10 XRK per block.

How can I get Testnet XRK tokens?
#################################

Testnet XRK tokens are available for the community to build and deploy applications on the RecordsKeeper blockchain. You can get Testnet XRK through the `RecordsKeeper faucet <https://faucet.recordskeeper.co/>`_ .


Do I need to buy XRK to use the Demo?
#####################################

The RecordsKeeper Demo provides new users with 1 XRK coin over the mainnet, which can be used to publish transaction on the RecordsKeeper blockchain. The maximum amount of data which can be published is based upon the fees. If you want to publish large amounts of data, you need to buy more XRK tokens. To buy XRK, please contact us here.

Who gets the XRK which are spent as transaction fees?
#####################################################

The miner who confirms the transaction gets the XRK spent in transaction fees.

On which exchanges is XRK listed?
#################################

We have not been listed on any exchange as of now. However, we are in talk with multiple exchanges for this. Please subscribe to our newsletter to get updates on exchange listing.

How can I purchase XRK in bulk?
###############################

To buy XRK in bulk, you can contact us here.

