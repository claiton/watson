# 1 DOWNLOAD A BUSINESS NETWORK CODE
=============================================================


1. git clone http://github.com/plucena/marbles-network

2. Open marbles-network project and  edit it

![](https://raw.githubusercontent.com/plucena/hyperledger/master/composer/marbles.png)

# 2 CREATE A CONNECTION TO HYPERLEDGER 0.6
============================================================

2.1 mkdir -r /root/.composer-connection-profiles/hlfabric

2.2 cd -r /root/.composer-connection-profiles/hlfabric

2.3 cp /root/marbles-network/connection.json  /root/.composer-connection-profiles/hlfabric


# 3 DEPLOY SMARTCONTRACT TO HYPERLEDGER 0.6
============================================================

3.1 cd /root/marbles-network

3.2 mkdir /root/marbles-network/dist

3.3 composer archive create --sourceType dir --sourceName . -a ./dist/my-network.bna
 
3.4 composer deploy network -a /root/marbles-network/dist/my-network.bna -p hlfabric -i  WebAppAdmin -s DJY27pEnl16d


# 4 CREATE LOOPBACK WEBSERVICE 
============================================================

composer-rest-server -p hlfabric -n marbles-network -i WebAppAdmin -s DJY27pEnl16d -N never -P 3000 -S false


![](https://raw.githubusercontent.com/plucena/hyperledger/master/composer/rest.png)


# 5.0 - OPTIONAL - connect to a Bluemix Hyperledger 0.6 blockchain instance
============================================================

Use Bluemix profile connection.json in this repository
