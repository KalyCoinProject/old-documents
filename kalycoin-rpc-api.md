# Kalycoin -RPC-API

**Kalycoin -RPC-API**

**This document includes the full list of Kalycoin RPCs based on Kalycoin core v0.17.6. According to this document you can learn how to use Kalycoin RPC API.**

****

### Tables of Contents

* [Blockchain](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#blockchain)
  * [callcontract](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#callcontract)
  * [getaccountinfo](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getaccountinfo)
  * [getbestblockhash](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getbestblockhash)
  * [getblock](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getblock)
  * [getblockchaininfo](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getblockchaininfo)
  * [getblockcount](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getblockcount)
  * [getblockhash](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getblockhash)
  * [getblockheader](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getblockheader)
  * [getblockstats](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getblockstats)
  * [getchaintips](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getchaintips)
  * [getchaintxstats](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getchaintxstats)
  * [getdifficulty](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getdifficulty)
  * [getmempoolancestors](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getmempoolancestors)
  * [getmempooldescendants](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getmempooldescendants)
  * [getmempoolentry](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getmempoolentry)
  * [getmempoolinfo](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getmempoolinfo)
  * [getrawmempool](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getrawmempool)
  * [getstorage](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getstorage)
  * [gettransactionreceipt](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#gettransactionreceipt)
  * [gettxout](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#gettxout)
  * [gettxoutproof](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#gettxoutproof)
  * [gettxoutsetinfo](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#gettxoutsetinfo)
  * [listcontracts](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#listcontracts)
  * [preciousblock](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#preciousblock)
  * [pruneblockchain](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#pruneblockchain)
  * [savemempool](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#savemempool)
  * [scantxoutset](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#scantxoutset)
  * [searchlogs](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#searchlogs)
  * [verifychain](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#verifychain)
  * [verifytxoutproof](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#verifytxoutproof)
  * [waitforlogs](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#waitforlogs)
* [Control](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#control)
  * [getmemoryinfo](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getmemoryinfo)
  * [help](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#help)
  * [logging](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#logging)
  * [stop](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#stop)
  * [uptime](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#uptime)
* [Generating](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#Generating)
  * [generate](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#generate)
  * [generatetoaddress](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#generatetoaddress)
* [Mining](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#mining)
  * [getblocktemplate](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getblocktemplate)
  * [getmininginfo](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getmininginfo)
  * [getnetworkhashps](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getnetworkhashps)
  * [getstakinginfo](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getstakinginfo)
  * [getsubsidy](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getsubsidy)
  * [prioritisetransaction](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#prioritisetransaction)
  * [submitblock](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#submitblock)
* [Network](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#network)
  * [addnode](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#addnode)
  * [clearbanned](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#clearbanned)
  * [disconnectnode](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#disconnectnode)
  * [getaddednodeinfo](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getaddednodeinfo)
  * [getconnectioncount](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getconnectioncount)
  * [getnettotals](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getnettotals)
  * [getnetworkinfo](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getnetworkinfo)
  * [getpeerinfo](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getpeerinfo)
  * [listbanned](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#listbanned)
  * [ping](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#ping)
  * [setban](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#setban)
  * [setnetworkactive](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#setnetworkactive)
* [Rawtransactions](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#rawtransactions)
  * [combinepsbt](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#combinepsbt)
  * [combinerawtransaction](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#combinerawtransaction)
  * [converttopsbt](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#converttopsbt)
  * [createpsbt](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#createpsbt)
  * [createrawtransaction](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#createrawtransaction)
  * [decodepsbt](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#decodepsbt)
  * [decoderawtransaction](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#decoderawtransaction)
  * [decodescript](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#decodescript)
  * [finalizepsbt](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#finalizepsbt)
  * [fromhexaddress](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#fromhexaddress)
  * [fundrawtransaction](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#fundrawtransaction)
  * [gethexaddress](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#gethexaddress)
  * [getrawtransaction](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getrawtransaction)
  * [sendrawtransaction](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#sendrawtransaction)
  * [signrawtransaction](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#signrawtransaction)
  * [signrawtransactionwithkey](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#signrawtransactionwithkey)
  * [testmempoolaccept](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#testmempoolaccept)
* [Util](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#util)
  * [createmultisig](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#createmultisig)
  * [estimatesmartfee](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#estimatesmartfee)
  * [signmessagewithprivkey](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#signmessagewithprivkey)
  * [validateaddress](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#validateaddress)
  * [verifymessage](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#verifymessage)
* [Wallet](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#wallet)
  * [abandontransaction](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#abandontransaction)
  * [abortrescan](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#abortrescan)
  * [addmultisigaddress](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#addmultisigaddress)
  * [backupwallet](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#backupwallet)
  * [bumpfee](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#bumpfee)
  * [createcontract](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#createcontract)
  * [createwallet](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#createwallet)
  * [dumpprivkey](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#dumpprivkey)
  * [dumpwallet](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#dumpwallet)
  * [encryptwallet](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#encryptwallet)
  * [getaddressesbylabel](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getaddressesbylabel)
  * [getaddressinfo](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getaddressinfo)
  * [getbalance](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getbalance)
  * [getnewaddress](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getnewaddress)
  * [getrawchangeaddress](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getrawchangeaddress)
  * [getreceivedbyaddress](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getreceivedbyaddress)
  * [gettransaction](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#gettransaction)
  * [getunconfirmedbalance](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getunconfirmedbalance)
  * [getwalletinfo](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getwalletinfo)
  * [importaddress](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#importaddress)
  * [importmulti](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#importmulti)
  * [importprivkey](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#importprivkey)
  * [importprunedfunds](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#importprunedfunds)
  * [importpubkey](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#importpubkey)
  * [importwallet](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#importwallet)
  * [keypoolrefill](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#keypoolrefill)
  * [listaccounts](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#listaccounts)
  * [listaddressgroupings](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#listaddressgroupings)
  * [listlabels](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#listlabels)
  * [listlockunspent](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#listlockunspent)
  * [listreceivedbyaddress](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#listreceivedbyaddress)
  * [listsinceblock](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#listsinceblock)
  * [listtransactions](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#listtransactions)
  * [listunspent](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#listunspent)
  * [listwallets](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#listwallets)
  * [loadwallet](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#loadwallet)
  * [lockunspent](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#lockunspent)
  * [removeprunedfunds](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#removeprunedfunds)
  * [rescanblockchain](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#rescanblockchain)
  * [reservebalance](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#reservebalance)
  * [sendmany](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#sendmany)
  * [sendmanywithdupes](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#sendmanywithdupes)
  * [sendtoaddress](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#sendtoaddress)
  * [sendtocontract](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#sendtocontract)
  * [sethdseed](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#sethdseed)
  * [settxfee](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#settxfee)
  * [signmessage](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#signmessage)
  * [signrawtransactionwithwallet](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#signrawtransactionwithwallet)
  * [unloadwallet](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#unloadwallet)
  * [walletcreatefundedpsbt](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#walletcreatefundedpsbt)
  * [walletlock](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#walletlock)
  * [walletpassphrase](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#walletpassphrase)
  * [walletpassphrasechange](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#walletpassphrasechange)
  * [walletprocesspsbt](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#walletprocesspsbt)
* [Zmq](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#zmq)
  *   [getzmqnotifications](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getzmqnotifications)

      ### Tables of Contents

      * [Blockchain](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#blockchain)
        * [callcontract](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#callcontract)
        * [getaccountinfo](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getaccountinfo)
        * [getbestblockhash](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getbestblockhash)
        * [getblock](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getblock)
        * [getblockchaininfo](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getblockchaininfo)
        * [getblockcount](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getblockcount)
        * [getblockhash](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getblockhash)
        * [getblockheader](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getblockheader)
        * [getblockstats](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getblockstats)
        * [getchaintips](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getchaintips)
        * [getchaintxstats](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getchaintxstats)
        * [getdifficulty](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getdifficulty)
        * [getmempoolancestors](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getmempoolancestors)
        * [getmempooldescendants](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getmempooldescendants)
        * [getmempoolentry](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getmempoolentry)
        * [getmempoolinfo](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getmempoolinfo)
        * [getrawmempool](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getrawmempool)
        * [getstorage](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getstorage)
        * [gettransactionreceipt](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#gettransactionreceipt)
        * [gettxout](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#gettxout)
        * [gettxoutproof](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#gettxoutproof)
        * [gettxoutsetinfo](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#gettxoutsetinfo)
        * [listcontracts](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#listcontracts)
        * [preciousblock](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#preciousblock)
        * [pruneblockchain](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#pruneblockchain)
        * [savemempool](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#savemempool)
        * [scantxoutset](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#scantxoutset)
        * [searchlogs](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#searchlogs)
        * [verifychain](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#verifychain)
        * [verifytxoutproof](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#verifytxoutproof)
        * [waitforlogs](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#waitforlogs)
      * [Control](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#control)
        * [getmemoryinfo](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getmemoryinfo)
        * [help](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#help)
        * [logging](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#logging)
        * [stop](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#stop)
        * [uptime](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#uptime)
      * [Generating](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#Generating)
        * [generate](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#generate)
        * [generatetoaddress](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#generatetoaddress)
      * [Mining](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#mining)
        * [getblocktemplate](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getblocktemplate)
        * [getmininginfo](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getmininginfo)
        * [getnetworkhashps](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getnetworkhashps)
        * [getstakinginfo](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getstakinginfo)
        * [getsubsidy](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getsubsidy)
        * [prioritisetransaction](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#prioritisetransaction)
        * [submitblock](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#submitblock)
      * [Network](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#network)
        * [addnode](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#addnode)
        * [clearbanned](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#clearbanned)
        * [disconnectnode](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#disconnectnode)
        * [getaddednodeinfo](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getaddednodeinfo)
        * [getconnectioncount](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getconnectioncount)
        * [getnettotals](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getnettotals)
        * [getnetworkinfo](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getnetworkinfo)
        * [getpeerinfo](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getpeerinfo)
        * [listbanned](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#listbanned)
        * [ping](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#ping)
        * [setban](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#setban)
        * [setnetworkactive](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#setnetworkactive)
      * [Rawtransactions](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#rawtransactions)
        * [combinepsbt](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#combinepsbt)
        * [combinerawtransaction](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#combinerawtransaction)
        * [converttopsbt](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#converttopsbt)
        * [createpsbt](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#createpsbt)
        * [createrawtransaction](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#createrawtransaction)
        * [decodepsbt](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#decodepsbt)
        * [decoderawtransaction](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#decoderawtransaction)
        * [decodescript](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#decodescript)
        * [finalizepsbt](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#finalizepsbt)
        * [fromhexaddress](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#fromhexaddress)
        * [fundrawtransaction](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#fundrawtransaction)
        * [gethexaddress](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#gethexaddress)
        * [getrawtransaction](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getrawtransaction)
        * [sendrawtransaction](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#sendrawtransaction)
        * [signrawtransaction](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#signrawtransaction)
        * [signrawtransactionwithkey](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#signrawtransactionwithkey)
        * [testmempoolaccept](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#testmempoolaccept)
      * [Util](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#util)
        * [createmultisig](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#createmultisig)
        * [estimatesmartfee](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#estimatesmartfee)
        * [signmessagewithprivkey](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#signmessagewithprivkey)
        * [validateaddress](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#validateaddress)
        * [verifymessage](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#verifymessage)
      * [Wallet](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#wallet)
        * [abandontransaction](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#abandontransaction)
        * [abortrescan](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#abortrescan)
        * [addmultisigaddress](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#addmultisigaddress)
        * [backupwallet](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#backupwallet)
        * [bumpfee](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#bumpfee)
        * [createcontract](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#createcontract)
        * [createwallet](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#createwallet)
        * [dumpprivkey](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#dumpprivkey)
        * [dumpwallet](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#dumpwallet)
        * [encryptwallet](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#encryptwallet)
        * [getaddressesbylabel](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getaddressesbylabel)
        * [getaddressinfo](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getaddressinfo)
        * [getbalance](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getbalance)
        * [getnewaddress](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getnewaddress)
        * [getrawchangeaddress](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getrawchangeaddress)
        * [getreceivedbyaddress](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getreceivedbyaddress)
        * [gettransaction](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#gettransaction)
        * [getunconfirmedbalance](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getunconfirmedbalance)
        * [getwalletinfo](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getwalletinfo)
        * [importaddress](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#importaddress)
        * [importmulti](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#importmulti)
        * [importprivkey](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#importprivkey)
        * [importprunedfunds](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#importprunedfunds)
        * [importpubkey](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#importpubkey)
        * [importwallet](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#importwallet)
        * [keypoolrefill](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#keypoolrefill)
        * [listaccounts](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#listaccounts)
        * [listaddressgroupings](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#listaddressgroupings)
        * [listlabels](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#listlabels)
        * [listlockunspent](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#listlockunspent)
        * [listreceivedbyaddress](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#listreceivedbyaddress)
        * [listsinceblock](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#listsinceblock)
        * [listtransactions](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#listtransactions)
        * [listunspent](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#listunspent)
        * [listwallets](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#listwallets)
        * [loadwallet](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#loadwallet)
        * [lockunspent](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#lockunspent)
        * [removeprunedfunds](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#removeprunedfunds)
        * [rescanblockchain](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#rescanblockchain)
        * [reservebalance](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#reservebalance)
        * [sendmany](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#sendmany)
        * [sendmanywithdupes](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#sendmanywithdupes)
        * [sendtoaddress](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#sendtoaddress)
        * [sendtocontract](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#sendtocontract)
        * [sethdseed](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#sethdseed)
        * [settxfee](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#settxfee)
        * [signmessage](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#signmessage)
        * [signrawtransactionwithwallet](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#signrawtransactionwithwallet)
        * [unloadwallet](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#unloadwallet)
        * [walletcreatefundedpsbt](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#walletcreatefundedpsbt)
        * [walletlock](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#walletlock)
        * [walletpassphrase](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#walletpassphrase)
        * [walletpassphrasechange](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#walletpassphrasechange)
        * [walletprocesspsbt](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#walletprocesspsbt)
      * [Zmq](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#zmq)
        * [getzmqnotifications](https://github.com/KalyCoinProject/old-documents/tree/main/en/KalyCoin-RPC-API#getzmqnotifications)

**Blockchain**

**callcontract**

callcontract "address" "data" ( address )

**Argument:**

1\. "address" (string, required) The account address

2\. "data"    (string, required) The data hex string

3\. address   (string, optional) The sender address hex string

4\. gasLimit  (string, optional) The gas limit for executing the contract

**Test example:**

./ Kalycoin -cli callcontract "74045ec0dc26ec1861473828bc140ebc4c1f3eff" "00000000000000000000000000000000000000000000000000000000000000a9"

**Test result:**

{

&#x20; "address": "74045ec0dc26ec1861473828bc140ebc4c1f3eff",

&#x20; "executionResult": {

&#x20; "gasUsed": 39999999,

&#x20; "excepted": "None",

&#x20; "newAddress": "74045ec0dc26ec1861473828bc140ebc4c1f3eff",

&#x20; "output": "",

&#x20; "codeDeposit": 0,

&#x20; "gasRefunded": 0,

&#x20; "depositSize": 0,

&#x20; "gasForDeposit": 0

&#x20; },

&#x20; "transactionReceipt":

&#x20; {

&#x20;   "stateRoot": "1253c56cf79597e89ce179f14e6a86a493356dac410c30efc576503687ad2670",

&#x20;   "gasUsed": 39999999,

&#x20;   "bloom": "00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000",

&#x20;   "log": \[

&#x20; ]

&#x20; }

}

**getaccountinfo**

Contract details including balance, storage data and code

**Argument:**

1\. "address"(string, required) The contract address

**Result:**

Contract details including balance, storage data and code

**Test example:**

./ Kalycoin -cli getaccountinfo "fdb9d0873ba524ef3ea67c1719666968e1eeb110"

**getbestblockhash**

Returns the hash of the best (tip) block in the longest blockchain.

**Result:**

"hex" (string) the block hash hex encoded

**Examples:**

\> Kalycoin -cli getbestblockhash&#x20;

&#x20;

\>curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getbestblockhash", "params": \[] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**Test example:**

./ Kalycoin -cli getbestblockhash

**Test result:**

e006ada4d1b7caf1559cc1b5b520ab8c54f51486230f2ea18d2692d3a095ba03

**getblock**

According the blockhash returns the info of the corresponding block If verbosity is 0, returns a string that is serialized, hex-encoded data for block 'hash'. If verbosity is 1, returns an Object with information about block . If verbosity is 2, returns an Object with information about block and information about each transaction.

**Arguments:**

1\. "blockhash" (string, required) The block hash

2\. verbosity (numeric, optional, default=1) 0 for hex encoded data, 1 for a json object, and 2 for json object with transaction data

**Result (for verbosity = 0):**

"data" (string) A string that is serialized, hex-encoded data for block 'hash'.

**Result (for verbosity = 1):**

{

&#x20; "hash" : "hash",       (string) the block hash (same as provided)

&#x20; "confirmations" : n,   (numeric) The number of confirmations, or -1 if the block is not on the main chain

&#x20; "size" : n,            (numeric) The block size

&#x20; "strippedsize" : n,    (numeric) The block size excluding witness data

&#x20; "weight" : n           (numeric) The block weight as defined in BIP 141

&#x20; "height" : n,          (numeric) The block height or index

&#x20; "version" : n,         (numeric) The block version

&#x20; "versionHex" : "00000000", (string) The block version formatted in hexadecimal

&#x20; "merkleroot" : "xxxx", (string) The merkle root

&#x20; "tx" : \[               (array of string) The transaction ids

&#x20;    "transactionid"     (string) The transaction id

&#x20;    ,...

&#x20; ],

&#x20; "time" : ttt,          (numeric) The block time in seconds since epoch (Jan 1 1970 GMT)

&#x20; "mediantime" : ttt,    (numeric) The median block time in seconds since epoch (Jan 1 1970 GMT)

&#x20; "nonce" : n,           (numeric) The nonce

&#x20; "bits" : "1d00ffff",   (string) The bits

&#x20; "difficulty" : x.xxx,  (numeric) The difficulty

&#x20; "chainwork" : "xxxx",  (string) Expected number of hashes required to produce the chain up to this block (in hex)

&#x20; "nTx" : n,             (numeric) The number of transactions in the block.

&#x20; "previousblockhash" : "hash",  (string) The hash of the previous block

&#x20; "nextblockhash" : "hash"       (string) The hash of the next block

}

**Result (for verbosity = 2):**

{

&#x20;   ..., Same output as verbosity = 1.

&#x20;   "tx" : \[ (array of Objects) The transactions in the format of the getrawtransaction RPC. Different from verbosity = 1 "tx" result.

&#x20;   ,...

&#x20;   ],

&#x20;   ,... Same output as verbosity = 1.

}

**Examples:**

\> Kalycoin -cli getblock "00000000c937983704a73af28acdec37b049d214adbda81d7e2a3dd146f6ed09"

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getblock", "params": \["00000000c937983704a73af28acdec37b049d214adbda81d7e2a3dd146f6ed09"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**test examples:**

./ Kalycoin -cli getblock “eeab43864b89c15bd1ffad21eaabc97f4fa4a576a71b46c9d512afc26168569f”

**Test result:**

{

&#x20; "hash": "eeab43864b89c15bd1ffad21eaabc97f4fa4a576a71b46c9d512afc26168569f",

&#x20; "confirmations": 2,

&#x20; "strippedsize": 846,

&#x20; "size": 882,

&#x20; "weight": 3420,

&#x20; "height": 402359,

&#x20; "version": 536870912,

&#x20; "versionHex": "20000000",

&#x20; "merkleroot": "359698a4d0e24baadfe9892b56bb5a6090830aea9fe1bf221f4766d7d552eeff",

&#x20; "hashStateRoot": "6099ad48961a320b62cc29ba3d89dcbd8bbc0e33069f6c7169ba008039cbc44f",

&#x20; "hashUTXORoot": "9e729950c184acd011471252a0c1a4bc279cd4c1e86d543bead4af6df787b2dd",

&#x20; "tx": \[

&#x20;   "9cd9f5e952988cd88c73b7cd172cc17f7ba6ec7c34918b50fbfa3901251cbc2f",

&#x20;   "49260697a2d127541cfd5190fc18a5193f118d4b1cc23504a520983ad7f0ee35"

&#x20; ],

&#x20; "time": 1562145008,

&#x20; "mediantime": 1562144608,

&#x20; "nonce": 0,

&#x20; "bits": "1a037540",

&#x20; "difficulty": 4851625.823213781,

&#x20; "chainwork": "000000000000000000000000000000000000000000000114688c263219ba17a6",

&#x20; "nTx": 2,

&#x20; "previousblockhash": "dd7ccce7a7b419874dac6097c6505c3b00efdce9336aa9ad79363c81d8a05e26",

&#x20; "nextblockhash": "60ef2b919581b7d7f684e6e2de574ee72ac94cb924770988d2686ca4c3b6e24a",

&#x20; "flags": "proof-of-stake",

&#x20; "proofhash": "000001199a996fef47845c16830c9187ed076dea11d34ba734201a011945c962",

&#x20; "modifier": "148572257a37c882895429d69b15d8a2446be5ad5f0d74237ecf621841164990",

&#x20; "signature": "304402204fe60e75699f3773e3c1d86281f2e7cf17268d23e40628622b3a215fea299e68022041c767b4e2ede77311aeaca2dfafc8f9066f628d2aa3234a57604cebc976c311"

}

**getblockchaininfo**

Returns an object containing various state info regarding blockchain processing.

**Result:**

{

&#x20; "chain": "xxxx",              (string) current network name as defined in BIP70 (main, test, regtest)

&#x20; "blocks": xxxxxx,             (numeric) the current number of blocks processed in the server

&#x20; "headers": xxxxxx,            (numeric) the current number of headers we have validated

&#x20; "bestblockhash": "...",       (string) the hash of the currently best block

&#x20; "difficulty": xxxxxx,         (numeric) the current difficulty

&#x20; "mediantime": xxxxxx,         (numeric) median time for the current best block

&#x20; "verificationprogress": xxxx, (numeric) estimate of verification progress \[0..1]

&#x20; "initialblockdownload": xxxx, (bool) (debug information) estimate of whether this node is in Initial Block Download mode.

&#x20; "chainwork": "xxxx"           (string) total amount of work in active chain, in hexadecimal

&#x20; "size\_on\_disk": xxxxxx,       (numeric) the estimated size of the block and undo files on disk

&#x20; "pruned": xx,                 (boolean) if the blocks are subject to pruning

&#x20; "pruneheight": xxxxxx,        (numeric) lowest-height complete block stored (only present if pruning is enabled)

&#x20; "automatic\_pruning": xx,      (boolean) whether automatic pruning is enabled (only present if pruning is enabled)

&#x20; "prune\_target\_size": xxxxxx,  (numeric) the target size used by pruning (only present if automatic pruning is enabled)

&#x20; "softforks": \[                (array) status of softforks in progress

&#x20;    {

&#x20;       "id": "xxxx",           (string) name of softfork

&#x20;       "version": xx,          (numeric) block version

&#x20;       "reject": {             (object) progress toward rejecting pre-softfork blocks

&#x20;          "status": xx,        (boolean) true if threshold reached

&#x20;       },

&#x20;    }, ...

&#x20; ],

&#x20; "bip9\_softforks": {           (object) status of BIP9 softforks in progress

&#x20;    "xxxx" : {                 (string) name of the softfork

&#x20;       "status": "xxxx",       (string) one of "defined", "started", "locked\_in", "active", "failed"

&#x20;       "bit": xx,              (numeric) the bit (0-28) in the block version field used to signal this softfork (only for "started" status)

&#x20;       "startTime": xx,        (numeric) the minimum median time past of a block at which the bit gains its meaning

&#x20;       "timeout": xx,          (numeric) the median time past of a block at which the deployment is considered failed if not yet locked in

&#x20;       "since": xx,            (numeric) height of the first block to which the status applies

&#x20;       "statistics": {         (object) numeric statistics about BIP9 signalling for a softfork (only for "started" status)

&#x20;          "period": xx,        (numeric) the length in blocks of the BIP9 signalling period

&#x20;          "threshold": xx,     (numeric) the number of blocks with the version bit set required to activate the feature

&#x20;          "elapsed": xx,       (numeric) the number of blocks elapsed since the beginning of the current period

&#x20;          "count": xx,         (numeric) the number of blocks with the version bit set in the current period

&#x20;          "possible": xx       (boolean) returns false if there are not enough blocks left in this period to pass activation threshold

&#x20;       }

&#x20;    }

&#x20; }

&#x20; "warnings" : "...",           (string) any network and blockchain warnings.

}

**Test example:**

./ Kalycoin -cli getblockchaininfo

**Test result:**

{

&#x20; "chain": "main",

&#x20; "blocks": 401574,

&#x20; "headers": 401574,

&#x20; "bestblockhash": "be4cb62080f36d2c3a45127e016460aca82ea1de17af4166ad9341d1a18e00cc",

&#x20; "difficulty": 1699339.658646735,

&#x20; "moneysupply": 101586296,

&#x20; "mediantime": 1562032592,

&#x20; "verificationprogress": 0.9999994694221126,

&#x20; "initialblockdownload": false,

&#x20; "chainwork": "000000000000000000000000000000000000000000000113f4c983f14834f842",

&#x20; "size\_on\_disk": 1939468044,

&#x20; "pruned": false,

&#x20; "softforks": \[

&#x20; {

&#x20;   "id": "bip34",

&#x20;   "version": 2,

&#x20;   "reject": {

&#x20;   "status": true

&#x20;   }

&#x20; },

&#x20; {

&#x20;   "id": "bip66",

&#x20;   "version": 3,

&#x20;   "reject": {

&#x20;   "status": true

&#x20;   }

&#x20; },

&#x20; {

&#x20;   "id": "bip65",

&#x20;   "version": 4,

&#x20;   "reject": {

&#x20;   "status": true

&#x20;   }

&#x20; }

&#x20; ],

&#x20; "bip9\_softforks": {

&#x20; "csv": {

&#x20;   "status": "active",

&#x20;   "startTime": 0,

&#x20;   "timeout": 999999999999,

&#x20;   "since": 6048

&#x20; },

&#x20; "segwit": {

&#x20;   "status": "active",

&#x20;   "startTime": 0,

&#x20;   "timeout": 999999999999,

&#x20;   "since": 6048

&#x20; }

&#x20; },

&#x20; "warnings": ""

}

**getblockcount**

Returns the number of blocks in the longest blockchain.

**Result:**

n (numeric) The current block count

**Examples:**

\> Kalycoin -cli getblockcount

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getblockcount", "params": \[] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**Test example:**

./ Kalycoin -cli getblockcount

**Test result:**

395049

**getblockhash**

`Returns` hash of block in best-block-chain at height provided.

**Arguments:**

1\. height         (numeric, required) The height index

**Result:**

"hash"         (string) The block hash&#x20;

**Examples:**

\> Kalycoin -cli getblockhash 1000&#x20;

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getblockhash", "params": \[1000] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**Test example:**

./ Kalycoin -cli getblockhash 1

**Test result:**

0000d5dab5e76310ae640e9bcfa270c2eb23a1e5948bdf01fc7ed1f157110ab7

**getblockheader**

Returns the corresponding block header information according to the given index If verbose is false, returns a string that is serialized, hex-encoded data for blockheader 'hash'. If verbose is true, returns an Object with information about blockheader .

**Arguments:**

1\. "hash"  (string, required) The block hash

2\. verbose (boolean, optional, default=true) true for a json object, false for the hex encoded data

**Result (for verbose = true):**

{

&#x20; "hash" : "hash",               (string) the block hash (same as provided)

&#x20; "confirmations" : n,           (numeric) The number of confirmations, or -1 if the block is not on the main chain

&#x20; "height" : n,                  (numeric) The block height or index

&#x20; "version" : n,                 (numeric) The block version

&#x20; "versionHex" : "00000000",     (string) The block version formatted in hexadecimal

&#x20; "merkleroot" : "xxxx",         (string) The merkle root

&#x20; "time" : ttt,                  (numeric) The block time in seconds since epoch (Jan 1 1970 GMT)

&#x20; "mediantime" : ttt,            (numeric) The median block time in seconds since epoch (Jan 1 1970 GMT)

&#x20; "nonce" : n,                   (numeric) The nonce

&#x20; "bits" : "1d00ffff",           (string) The bits

&#x20; "difficulty" : x.xxx,          (numeric) The difficulty

&#x20; "chainwork" : "0000...1f3"     (string) Expected number of hashes required to produce the current chain (in hex)

&#x20; "nTx" : n,                     (numeric) The number of transactions in the block.

&#x20; "previousblockhash" : "hash",  (string) The hash of the previous block

&#x20; "nextblockhash" : "hash",      (string) The hash of the next block

}

**Result (for verbose = false):**

"data" (string) A string that is serialized, hex-encoded data for block 'hash'.

**Examples:**

\> Kalycoin -cli getblockheader "00000000c937983704a73af28acdec37b049d214adbda81d7e2a3dd146f6ed09"

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getblockheader", "params": \["00000000c937983704a73af28acdec37b049d214adbda81d7e2a3dd146f6ed09"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**Test example:**

./ Kalycoin -cli getblockheader

“ebd10c9b338247a9ccfd45493b484ae5638a5d97ddaa68c44c6ef214ea443c19”

**Test result:**

&#x20;{

&#x20;   "hash": "ebd10c9b338247a9ccfd45493b484ae5638a5d97ddaa68c44c6ef214ea443c19",

&#x20;   "confirmations": -1,

&#x20;   "height": 388910,

&#x20;   "version": 536870912,

&#x20;   "versionHex": "20000000",

&#x20;   "merkleroot": "b1a21dd48f978ea8671383f9454d058d2047d19666348340bea543cf89e31aca",

&#x20;   "time": 1560222144,

&#x20;   "mediantime": 1560221568,

&#x20;   "nonce": 0,

&#x20;   "bits": "1a097561",

&#x20;   "difficulty": 1773742.122273433,

&#x20;   "chainwork": "00000000000000000000000000000000000000000000010ca5944ed9b867aaef",

&#x20;   "nTx": 7,

&#x20;   "hashStateRoot": "10504057696a3ad9f96254b86424cc8f49f3ef2b271893f933b18174e538b828",

&#x20;   "hashUTXORoot": "9e729950c184acd011471252a0c1a4bc279cd4c1e86d543bead4af6df787b2dd",

&#x20;   "previousblockhash": "56044826105d66a95ab6f97f945a7cd18eef7109c59da64a7b6c57c377eaf4bb",

&#x20;   "flags": "proof-of-stake",

&#x20;   "proofhash": "0000000000000000000000000000000000000000000000000000000000000000",

&#x20;   "modifier": "1551ed22c1a43da60aebcb2d66a1e42d9bf6a007276367a4a189325ea37a1f91"

&#x20;}

**getblockstats**

Compute per block statistics for a given window. All amounts are in satoshis. It won't work for some heights with pruning. It won't work without -txindex for utxo\_size\_inc, _fee or_ feerate stats.

**Arguments:**

1\. "hash\_or\_height"     (string or numeric, required) The block hash or height of the target block

2\. "stats"              (array,  optional) Values to plot, by default all values (see result below)

&#x20;   \[

&#x20;     "height",         (string, optional) Selected statistic

&#x20;     "time",           (string, optional) Selected statistic

&#x20;     ,...

&#x20;   ]

**Result:**

&#x20;{                          &#x20;

&#x20; "avgfee": xxxxx,          (numeric) Average fee in the block

&#x20; "avgfeerate": xxxxx,      (numeric) Average feerate (in satoshis per virtual byte)

&#x20; "avgtxsize": xxxxx,       (numeric) Average transaction size

&#x20; "blockhash": xxxxx,       (string) The block hash (to check for potential reorgs)

&#x20; "feerate\_percentiles": \[  (array of numeric) Feerates at the 10th, 25th, 50th, 75th, and 90th percentile weight unit (in satoshis per virtual byte)

&#x20;     "10th\_percentile\_feerate",      (numeric) The 10th percentile feerate

&#x20;     "25th\_percentile\_feerate",      (numeric) The 25th percentile feerate

&#x20;     "50th\_percentile\_feerate",      (numeric) The 50th percentile feerate

&#x20;     "75th\_percentile\_feerate",      (numeric) The 75th percentile feerate

&#x20;     "90th\_percentile\_feerate",      (numeric) The 90th percentile feerate

&#x20; ],

&#x20; "height": xxxxx,          (numeric) The height of the block

&#x20; "ins": xxxxx,             (numeric) The number of inputs (excluding coinbase)

&#x20; "maxfee": xxxxx,          (numeric) Maximum fee in the block

&#x20; "maxfeerate": xxxxx,      (numeric) Maximum feerate (in satoshis per virtual byte)

&#x20; "maxtxsize": xxxxx,       (numeric) Maximum transaction size

&#x20; "medianfee": xxxxx,       (numeric) Truncated median fee in the block

&#x20; "mediantime": xxxxx,      (numeric) The block median time past

&#x20; "mediantxsize": xxxxx,    (numeric) Truncated median transaction size

&#x20; "minfee": xxxxx,          (numeric) Minimum fee in the block

&#x20; "minfeerate": xxxxx,      (numeric) Minimum feerate (in satoshis per virtual byte)

&#x20; "mintxsize": xxxxx,       (numeric) Minimum transaction size

&#x20; "outs": xxxxx,            (numeric) The number of outputs

&#x20; "subsidy": xxxxx,         (numeric) The block subsidy

&#x20; "swtotal\_size": xxxxx,    (numeric) Total size of all segwit transactions

&#x20; "swtotal\_weight": xxxxx,  (numeric) Total weight of all segwit transactions divided by segwit scale factor (4)

&#x20; "swtxs": xxxxx,           (numeric) The number of segwit transactions

&#x20; "time": xxxxx,            (numeric) The block time

&#x20; "total\_out": xxxxx,       (numeric) Total amount in all outputs (excluding coinbase and thus reward \[ie subsidy + totalfee])

&#x20; "total\_size": xxxxx,      (numeric) Total size of all non-coinbase transactions

&#x20; "total\_weight": xxxxx,    (numeric) Total weight of all non-coinbase transactions divided by segwit scale factor (4)

&#x20; "totalfee": xxxxx,        (numeric) The fee total

&#x20; "txs": xxxxx,             (numeric) The number of transactions (excluding coinbase)

&#x20; "utxo\_increase": xxxxx,   (numeric) The increase/decrease in the number of unspent outputs

&#x20; "utxo\_size\_inc": xxxxx,   (numeric) The increase/decrease in size for the utxo index (not discounting op\_return and similar)

}

**Examples:**

\> Kalycoin -cli getblockstats 1000 '\["minfeerate","avgfeerate"]'

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getblockstats", "params": \[1000 '\["minfeerate","avgfeerate"]'] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**getchaintips**

Return information about all known tips in the block tree, including the main chain as well as orphaned branches.

**Result:**

&#x20;\[

&#x20;   {

&#x20;     "height": xxxx,    (numeric) height of the chain tip

&#x20;     "hash": "xxxx",    (string) block hash of the tip

&#x20;     "branchlen": 0     (numeric) zero for main chain

&#x20;     "status": "active" (string) "active" for the main chain

&#x20;   },

&#x20;   {

&#x20;     "height": xxxx,

&#x20;     "hash": "xxxx",

&#x20;     "branchlen": 1     (numeric) length of branch connecting the tip to the main chain

&#x20;     "status": "xxxx"   (string) status of the chain (active, valid-fork, valid-headers, headers-only, invalid)

&#x20;   }

&#x20; ]

**Possible values for status:**

1\.    "invalid" This branch contains at least one invalid block

2\.    "headers-only" Not all blocks for this branch are available, but the headers are valid

3\.    "valid-headers" All blocks are available for this branch, but they were never fully validated

4\.    "valid-fork" This branch is not part of the active chain, but is fully validated

5\.    "active" This is the tip of the active main chain, which is certainly valid

**Examples:**

\> Kalycoin -cli getchaintips

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getchaintips", "params": \[] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**Test example:**

./ Kalycoin -cli getchaintips

**Result:**

\[

&#x20; {

&#x20;   "height": 353464,

&#x20;   "hash": "342e378ff153232fb08efe61ceb2fc00e28b1569aa0de97d031ba0bab98387be",

&#x20;   "branchlen": 2,

&#x20;   "status": "invalid"

&#x20; },

&#x20; {

&#x20;   "height": 353415,

&#x20;   "hash": "f1748f4c718cf5d36bab1dc7f4199e0e0379a338e6ea55fb18860daa0bc0c604",

&#x20;   "branchlen": 1,

&#x20;   "status": "valid-fork"

&#x20; },

&#x20; {

&#x20;   "height": 353388,

&#x20;   "hash": "1fbd1234497731d8f3296c60e9d21cc5c8d57b19d4fe7f154b4aa17e47b526b8",

&#x20;   "branchlen": 1,

&#x20;   "status": "valid-headers"

&#x20; },

&#x20; {

&#x20;   "height": 353103,

&#x20;   "hash": "583b2cd790cc493390474306cb78de68e4ba2f0bfdae852ab36c240fb058c559",

&#x20;   "branchlen": 1,

&#x20;   "status": "valid-fork"

&#x20; },...

]

**getchaintxstats**

Compute statistics about the total number and rate of transactions in the chain.

**Arguments:**

1\. nblocks     (numeric, optional) Size of the window in number of blocks (default: one month).

2\. "blockhash" (string, optional) The hash of the block that ends the window.

**Result:**

&#x20;{

&#x20; "time": xxxxx,                         (numeric) The timestamp for the final block in the window in UNIX format.

&#x20; "txcount": xxxxx,                      (numeric) The total number of transactions in the chain up to that point.

&#x20; "window\_final\_block\_hash": "...",      (string) The hash of the final block in the window.

&#x20; "window\_block\_count": xxxxx,           (numeric) Size of the window in number of blocks.

&#x20; "window\_tx\_count": xxxxx,              (numeric) The number of transactions in the window. Only returned if "window\_block\_count" is > 0.

&#x20; "window\_interval": xxxxx,              (numeric) The elapsed time in the window in seconds. Only returned if "window\_block\_count" is > 0.

&#x20; "txrate": x.xx,                        (numeric) The average rate of transactions per second in the window. Only returned if "window\_interval" is > 0.

}

**Examples:**

\> Kalycoin -cli getchaintxstats

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getchaintxstats", "params": \[2016] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**Test result:**

{

&#x20; "time": 1561602624,

&#x20; "txcount": 866823,

&#x20; "window\_final\_block\_hash": "ea6b26303facc34404da3174962a5c1d8d00369a3ff27aa50238ba8f24170280",

&#x20; "window\_block\_count": 20250,

&#x20; "window\_tx\_count": 41012,

&#x20; "window\_interval": 2655920,

&#x20; "txrate": 0.01544173017259556

}

**getdifficulty**

Returns the proof-of-work difficulty as a multiple of the minimum difficulty.

Returns the proof-of-stake difficulty as a multiple of the minimum difficulty.

**Result:**

n.nnn (numeric) the proof-of-work difficulty as a multiple of the minimum difficulty.

**Examples:**

\> Kalycoin -cli getdifficulty

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getdifficulty", "params": \[] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**Test example:**

./ Kalycoin -cli getdifficulty

**Test result:**

{

&#x20; "proof-of-work": 1.52587890625e-05,

&#x20; "proof-of-stake": 7022116.100551808

}

**getmempoolancestors**

If txid is in the mempool, returns all in-mempool ancestors.

**Arguments:**

1\. "txid"  (string, required) The transaction id (must be in mempool)

2\. verbose (boolean, optional, default=false) True for a json object, false for array of transaction ids

**Result (for verbose = false):**

&#x20; \[

&#x20;   "transactionid" (string) The transaction id of an in-mempool ancestor transaction

&#x20;   ,...

&#x20; ]

**Result (for verbose=true):**

{                         &#x20;

&#x20; "transactionid" : {     &#x20;

&#x20;   "size" : n,             (numeric) virtual transaction size as defined in BIP 141. This is different from actual serialized size for witness transactions as witness data is discounted.

&#x20;   "fee" : n,              (numeric) transaction fee in KLC (DEPRECATED)

&#x20;   "modifiedfee" : n,      (numeric) transaction fee with fee deltas used for mining priority (DEPRECATED)

&#x20;   "time" : n,             (numeric) local time transaction entered pool in seconds since 1 Jan 1970 GMT

&#x20;   "height" : n,           (numeric) block height when transaction entered pool

&#x20;   "descendantcount" : n,  (numeric) number of in-mempool descendant transactions (including this one)

&#x20;   "descendantsize" : n,   (numeric) virtual transaction size of in-mempool descendants (including this one)

&#x20;   "descendantfees" : n,   (numeric) modified fees (see above) of in-mempool descendants (including this one) (DEPRECATED)

&#x20;   "ancestorcount" : n,    (numeric) number of in-mempool ancestor transactions (including this one)

&#x20;   "ancestorsize" : n,     (numeric) virtual transaction size of in-mempool ancestors (including this one)

&#x20;   "ancestorfees" : n,     (numeric) modified fees (see above) of in-mempool ancestors (including this one) (DEPRECATED)

&#x20;   "wtxid" : hash,         (string) hash of serialized transaction, including witness data

&#x20;   "fees" : {

&#x20;       "base" : n,         (numeric) transaction fee in KLC

&#x20;       "modified" : n,     (numeric) transaction fee with fee deltas used for mining priority in Kalycoin

&#x20;       "ancestor" : n,     (numeric) modified fees (see above) of in-mempool ancestors (including this one) in Kalycoin

&#x20;       "descendant" : n,   (numeric) modified fees (see above) of in-mempool descendants (including this one) in Kalycoin

&#x20;   }

&#x20;   "depends" : \[           (array) unconfirmed transactions used as inputs for this transaction

&#x20;       "transactionid",    (string) parent transaction id

&#x20;      ... ]

&#x20;   "spentby" : \[           (array) unconfirmed transactions spending outputs from this transaction

&#x20;       "transactionid",    (string) child transaction id

&#x20;      ... ]

&#x20; }, ...

}

**Examples:**

\> Kalycoin -cli getmempoolancestors "mytxid"

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getmempoolancestors", "params": \["mytxid"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**Test example:**

./ Kalycoin -cli getmempoolancestors a957d309824b760814feb6426ba386d082f3b8bc95837e3e7ebada6538cf7e2c   &#x20;

**Test result:**

\[

&#x20; "c3d044940534fd94fd0c901a895f62505e7beba0dfa44b1563c7aea980279135"   &#x20;

]

**getmempooldescendants**

If txid is in the mempool, returns all in-mempool descendants.

**Arguments:**

1\. "txid"   (string, required) The transaction id (must be in mempool)

2\.  verbose (boolean, optional, default=false) True for a json object, false for array of transaction ids

**Result (for verbose = false):**

\[

&#x20; "transactionid" (string) The transaction id of an in-mempool descendant transaction

&#x20; ,...

]

**Result (for verbose=true):**

&#x20;{                         &#x20;

&#x20; "transactionid" : {     &#x20;

&#x20;   "size" : n,             (numeric) virtual transaction size as defined in BIP 141. This is different from actual serialized size for witness transactions as witness data is discounted.

&#x20;   "fee" : n,              (numeric) transaction fee in KLC (DEPRECATED)

&#x20;   "modifiedfee" : n,      (numeric) transaction fee with fee deltas used for mining priority (DEPRECATED)

&#x20;   "time" : n,             (numeric) local time transaction entered pool in seconds since 1 Jan 1970 GMT

&#x20;   "height" : n,           (numeric) block height when transaction entered pool

&#x20;   "descendantcount" : n,  (numeric) number of in-mempool descendant transactions (including this one)

&#x20;   "descendantsize" : n,   (numeric) virtual transaction size of in-mempool descendants (including this one)

&#x20;   "descendantfees" : n,   (numeric) modified fees (see above) of in-mempool descendants (including this one) (DEPRECATED)

&#x20;   "ancestorcount" : n,    (numeric) number of in-mempool ancestor transactions (including this one)

&#x20;   "ancestorsize" : n,     (numeric) virtual transaction size of in-mempool ancestors (including this one)

&#x20;   "ancestorfees" : n,     (numeric) modified fees (see above) of in-mempool ancestors (including this one) (DEPRECATED)

&#x20;   "wtxid" : hash,         (string) hash of serialized transaction, including witness data

&#x20;   "fees" : {

&#x20;       "base" : n,         (numeric) transaction fee in KLC

&#x20;       "modified" : n,     (numeric) transaction fee with fee deltas used for mining priority in Kalycoin

&#x20;       "ancestor" : n,     (numeric) modified fees (see above) of in-mempool ancestors (including this one) in Kalycoin

&#x20;       "descendant" : n,   (numeric) modified fees (see above) of in-mempool descendants (including this one) in Kalycoin

&#x20;   }

&#x20;   "depends" : \[           (array) unconfirmed transactions used as inputs for this transaction

&#x20;       "transactionid",    (string) parent transaction id

&#x20;      ... ]

&#x20;   "spentby" : \[           (array) unconfirmed transactions spending outputs from this transaction

&#x20;       "transactionid",    (string) child transaction id

&#x20;      ... ]

&#x20; }, ...

}

**Examples:**

\> Kalycoin -cli getmempooldescendants "mytxid"

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getmempooldescendants", "params": \["mytxid"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**Test result:**

\[

&#x20; "9d980a4fcdf13fb2c9a5c7769ad6f3e8668aba1f0608be09ef84a11afaf3d03f",

&#x20; "89874d6f44bb3b8a526c50cecda1cbe06c6c6e8107623b79222ee75b79f91d5a",

&#x20; "0c2d893fdc510a6fddb18fc3d441b02d5b6050b754dc6f5d5ddd251707c3d995"

]

**getmempoolentry**

Returns mempool data for given transaction

**Arguments:**

1\. "txid" (string, required) The transaction id (must be in mempool)

**Result:**

{                         &#x20;

&#x20;   "size" : n,             (numeric) virtual transaction size as defined in BIP 141. This is different from actual serialized size for witness transactions as witness data is discounted.

&#x20;   "fee" : n,              (numeric) transaction fee in KLC (DEPRECATED)

&#x20;   "modifiedfee" : n,      (numeric) transaction fee with fee deltas used for mining priority (DEPRECATED)

&#x20;   "time" : n,             (numeric) local time transaction entered pool in seconds since 1 Jan 1970 GMT

&#x20;   "height" : n,           (numeric) block height when transaction entered pool

&#x20;   "descendantcount" : n,  (numeric) number of in-mempool descendant transactions (including this one)

&#x20;   "descendantsize" : n,   (numeric) virtual transaction size of in-mempool descendants (including this one)

&#x20;   "descendantfees" : n,   (numeric) modified fees (see above) of in-mempool descendants (including this one) (DEPRECATED)

&#x20;   "ancestorcount" : n,    (numeric) number of in-mempool ancestor transactions (including this one)

&#x20;   "ancestorsize" : n,     (numeric) virtual transaction size of in-mempool ancestors (including this one)

&#x20;   "ancestorfees" : n,     (numeric) modified fees (see above) of in-mempool ancestors (including this one) (DEPRECATED)

&#x20;   "wtxid" : hash,         (string) hash of serialized transaction, including witness data

&#x20;   "fees" : {

&#x20;       "base" : n,         (numeric) transaction fee in KLC

&#x20;       "modified" : n,     (numeric) transaction fee with fee deltas used for mining priority in Kalycoin

&#x20;       "ancestor" : n,     (numeric) modified fees (see above) of in-mempool ancestors (including this one) in Kalycoin

&#x20;       "descendant" : n,   (numeric) modified fees (see above) of in-mempool descendants (including this one) in Kalycoin

&#x20;   }

&#x20;   "depends" : \[           (array) unconfirmed transactions used as inputs for this transaction

&#x20;       "transactionid",    (string) parent transaction id

&#x20;      ... ]

&#x20;   "spentby" : \[           (array) unconfirmed transactions spending outputs from this transaction

&#x20;       "transactionid",    (string) child transaction id

&#x20;      ... ]

}

**Examples:**

\> Kalycoin -cli getmempoolentry "mytxid"

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getmempoolentry", "params": \["mytxid"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**getmempoolinfo**

Returns details on the active state of the TX memory pool.

**Result:**

{

&#x20; "size": xxxxx, (numeric) Current tx count&#x20;

&#x20; "bytes": xxxxx, (numeric) Sum of all virtual transaction sizes as defined in BIP 141. Differs from actual serialized size because witness data is discounted&#x20;

&#x20; "usage": xxxxx, (numeric) Total memory usage for the mempool&#x20;

&#x20; "maxmempool": xxxxx, (numeric) Maximum memory usage for the mempool&#x20;

&#x20; "mempoolminfee": xxxxx (numeric) Minimum fee rate in KLC /kB for tx to be accepted. Is the maximum of minrelaytxfee and minimum mempool fee&#x20;

&#x20; "minrelaytxfee": xxxxx (numeric) Current minimum relay fee for transactions&#x20;

}

**Examples:**

\> Kalycoin -cli getmempoolinfo

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getmempoolinfo", "params": \[] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**Test example:**

./ Kalycoin -cli getmempoolinfo

**Test result:**

{

&#x20; "size": 10,

&#x20; "bytes": 3582,

&#x20; "usage": 14176,

&#x20; "maxmempool": 300000000,

&#x20; "mempoolminfee": 0.00400000,

&#x20; "minrelaytxfee": 0.00400000

}

**getrawmempool**

Returns all transaction ids in memory pool as a json array of string transaction ids.

Hint: use getmempoolentry to fetch a specific transaction from the mempool.

**Arguments:**

1\. verbose (boolean, optional, default=false) True for a json object, false for array of transaction ids

**Result: (for verbose = false):**

{                         &#x20;

&#x20; "transactionid" : {     &#x20;

&#x20;   "size" : n,             (numeric) virtual transaction size as defined in BIP 141. This is different from actual serialized size for witness transactions as witness data is discounted.

&#x20;   "fee" : n,              (numeric) transaction fee in kLC (DEPRECATED)

&#x20;   "modifiedfee" : n,      (numeric) transaction fee with fee deltas used for mining priority (DEPRECATED)

&#x20;   "time" : n,             (numeric) local time transaction entered pool in seconds since 1 Jan 1970 GMT

&#x20;   "height" : n,           (numeric) block height when transaction entered pool

&#x20;   "descendantcount" : n,  (numeric) number of in-mempool descendant transactions (including this one)

&#x20;   "descendantsize" : n,   (numeric) virtual transaction size of in-mempool descendants (including this one)

&#x20;   "descendantfees" : n,   (numeric) modified fees (see above) of in-mempool descendants (including this one) (DEPRECATED)

&#x20;   "ancestorcount" : n,    (numeric) number of in-mempool ancestor transactions (including this one)

&#x20;   "ancestorsize" : n,     (numeric) virtual transaction size of in-mempool ancestors (including this one)

&#x20;   "ancestorfees" : n,     (numeric) modified fees (see above) of in-mempool ancestors (including this one) (DEPRECATED)

&#x20;   "wtxid" : hash,         (string) hash of serialized transaction, including witness data

&#x20;   "fees" : {

&#x20;       "base" : n,         (numeric) transaction fee in KLC

&#x20;       "modified" : n,     (numeric) transaction fee with fee deltas used for mining priority in Kalycoin

&#x20;       "ancestor" : n,     (numeric) modified fees (see above) of in-mempool ancestors (including this one) in Kalycoin

&#x20;       "descendant" : n,   (numeric) modified fees (see above) of in-mempool descendants (including this one) in Kalycoin

&#x20;   }

&#x20;   "depends" : \[           (array) unconfirmed transactions used as inputs for this transaction

&#x20;       "transactionid",    (string) parent transaction id

&#x20;      ... ]

&#x20;   "spentby" : \[           (array) unconfirmed transactions spending outputs from this transaction

&#x20;       "transactionid",    (string) child transaction id

&#x20;      ... ]

&#x20; }, ...

}

**Examples:**

\> Kalycoin -cli getrawmempool true

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getrawmempool", "params": \[true] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**Test example:**

./ Kalycoin -cli getrawmempool

**Test result:**

\[

&#x20; "d4e995b2e0b5ef44f90659323e662f408f7938b5b97c345a40192ca6d0b06704",

&#x20; "9e41daae52ece96732305cb0873b8528e7011c866eb7c3c9bee2c22c03e5bf65",

&#x20; "354297aef68f48044af17c3f01616597dad298304e34728fa9894b3ff73a0f33",

&#x20; "e2c407e5468a3e885b73760e3c6115d6d493786fff5ec070e91ad9b4db58b2ef",

&#x20; "15f9f80b536041ebf5c3958c7b7d9bab72c800882235fc782925137c2addbdd2",

&#x20; "109483b1b06746cf4215f3786907b26213adc71a14145acccbba4f0952a751a3",

&#x20; "b49e03dd14a242803bf8108a10a9f82120e21e7d4b0a9255c632e7b92d879136",

&#x20; "40a295fa44931750c048feb817fad96e079ce193c4eda0770d68be6c1f7241c3",

&#x20; "f1e4f8814a404adce808e9b0aed56f61ec151c745cba3a6ac1f0a917884adb59",

&#x20; "b6772f160e21c4633f95b1c5831c6d0451cab1501c375730ea32de64860f1809",

&#x20; "65894a5fcf0e19e13375ba0d0f2afa6e73f52512bc69cf8225c40af824f740d9",

&#x20; "8199c4f6c9f8be79fff4fc9664755bc0502de92d9856083112e55caaa2cb1974",

&#x20; "c3fb5ef13f87f2988c879c274cfbc1613240a12a66e9259388101d82364f1934",

&#x20; "ca78e53edcfba07d4eee2a1bbfc07e26e79e5677104399c794e51d098c735056",

&#x20; "7f66e7f6443ebd0d3a3a8e6bd83e3a5ffc6d32ef5a1ee6487c7abb5cfae7d409",

&#x20; "97966a9f3baeac334cb547d553baf71bf7c68720f350444d7411e0855f39a574",

&#x20; "78285303f6deef553cd5fcd5084db0bae3ccf504ac66f614cb29a5a6f6b5e815",

&#x20; "e5ae989b9782c1afd2c6f71379e46d162ffbe804c5b8db70b7bc85d939df2efe",

&#x20; "2f09732e25eab121a347471a91be55c798cde96aa7f8009da51c2a2d322e6410",

&#x20; "c302d3177a64a4a3c7f2ba1ea196b69754475192afa8249eb18f6f055556c8e1",

&#x20; "7f1de19f02347ea3744bcb11364c9883b91e4f4883b13f15e9e9f52595c1d3d6",

&#x20; "c241f5896723fec65b3af4f94491679ae8a79c434b2e0749651cf416952abac0",

&#x20; "4d8932af7a7073e2c4a5527767215f7bf5b8c7759a5b49d976f0031d5184fd18"

]

**getstorage**

Get data stored by smart contracts

**Argument:**

&#x20;1\. "address"  (string, required) The address to get the storage from

&#x20;2\. "blockNum" (string, optional) Number of block to get state from,  "latest" keyword supported. Latest if not passed.

&#x20;3\. "index"    (number, optional) Zero-based index position of the storage

**Examples:**

\> Kalycoin -cli getstorage “contract address”

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getstorage", "params": \["address"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**Test example:**

getstorage "fdb9d0873ba524ef3ea67c1719666968e1eeb110"

**Test result:**

{

&#x20; "000756ed9982214a7ba55dbe32d0321f5891e75d3c3c467d4b575d55991e03b1":

&#x20; {

&#x20;   "52adc13b5e472402f13052709f282024cc52e564f96b2183a5737c545229228d": "0000000000000000000000000000000000000000000000000000000000000001"

&#x20; },

}

**gettransactionreceipt**

requires -logevents to be enabled

**Argument:**

1\. "hash" (string, required) The contract transaction hash

**Result:**

{

&#x20; "blockHash":  "XXX"        (String), 32 bytes, the blockhash included this tx.

&#x20; "blockNumber": n           (Number), the blocknumber included this transaction.

&#x20; "transaction": "XXX":      (String), 32 bytes，the hash of this transaction.

&#x20; "transactionIndex": n      (numberic), the index in the block for this tx.

&#x20; "from": "XXX"              (String), 20 bytes，the sender address of this tx.

&#x20; "to"  : "XXXX"             (String), 20 bytes，the receiver address of this tx. if this  address is created by a contract,return null.

&#x20; "cumulativeGasUsed": n     (numberic), The total amount of gas used after execution of the current transaction

&#x20; "gasUsed": n (numberic), The gas cost alone to execute the current transaction。

&#x20; "contractAddress": "XXX"   (String), 20 bytes，the created contract address.

&#x20;  if this tx is created by the contract, return the contract address. else return null.

&#x20; "logs": \[]

}

**Test result:**

\[

&#x20; {

&#x20;   "blockHash": "1e34edb316f9c442d1db71ad5bd5376650387c6deb275c63c459b6624880180b",

&#x20;   "blockNumber": 196529,

&#x20;   "transactionHash": "acccfb57aaeb94127560f4762d5372af3dcb4faddf9de3b2ce6bde0fdd1d57d5",

&#x20;   "transactionIndex": 2,

&#x20;   "from": "83c2436854450b0895d4c1d965720ef5e6a125be",

&#x20;   "to": "74045ec0dc26ec1861473828bc140ebc4c1f3eff",

&#x20;   "cumulativeGasUsed": 23619,

&#x20;   "gasUsed": 23619,

&#x20;   "contractAddress": "74045ec0dc26ec1861473828bc140ebc4c1f3eff",

&#x20;   "excepted": "None",

&#x20;   "log": \[

&#x20;   ]

&#x20; }

]

**gettxout**

Returns details about an unspent transaction output.

**Arguments:**

1\. "txid"            (string, required) The transaction id

2\. "n"               (numeric, required) vout number

3\. "include\_mempool" (boolean, optional) Whether to include the mempool. Default: true. Note that an unspent output that is spent in the mempool won't appear.

**Result:**

{

&#x20; "bestblock": "hash",    (string) The hash of the block at the tip of the chain

&#x20; "confirmations" : n,    (numeric) The number of confirmations

&#x20; "value" : x.xxx,        (numeric) The transaction value in KLC

&#x20; "scriptPubKey" :

&#x20; {

&#x20;   "asm" : "code",       (string)

&#x20;   "hex" : "hex",        (string)

&#x20;   "reqSigs" : n,        (numeric) Number of required signatures

&#x20;   "type" : "pubkeyhash",(string) The type, eg pubkeyhash

&#x20;   "addresses" : \[ (array of string) array of Kalycoin addresses

&#x20;   "address"             (string) Kalycoin address

&#x20;   ,...

&#x20;   ]

&#x20;  },

&#x20; "coinbase" : true|false (boolean) Coinbase or not

}

**Examples:**

Get unspent transactions

\> Kalycoin -cli listunspent

View the details

\> Kalycoin -cli gettxout "txid" 1

As a json rpc call

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "gettxout", "params": \["txid", 1] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**gettxoutproof**

Returns a hex-encoded proof that "txid" was included in a block.

NOTE: By default this function only works sometimes. This is when there is an unspent output in the utxo for this transaction. To make it always work, you need to maintain a transaction index, using the -txindex command line option or specify the block in which the transaction is included manually (by blockhash).

**Arguments:**

1\. "txids" (string,required) A json array of txids to filter

&#x20; \[

&#x20;   "txid" (string) A transaction hash

&#x20;   ,...

&#x20; ]

2\. "blockhash" (string, optional) If specified, looks for txid in the block with this hash

**Result:**

"data" (string) A string that is a serialized, hex-encoded data for the proof.

**Test example:**

./ Kalycoin -cli gettxoutproof \[\\"5caa24c8c78f441a5c37dff602cdacc27b4530b03c09569f62dc3cd20e674918\\"]

**Test result:**

0000002081d3145a457b724b725171603a991b8d8186f0506c65722e436a6a33d039690ed689a1e4bdea746f8a3c47d6856765282fb5f7f20c9c43cc9e0170b6ba1214076010135d8683001b0000000052ef386ec7ae80719e408c3ea4193583bd0665fffd633d5e10b19e26375ac9b6386faa7484bfd98fc4789fd584229d5c20f72f772a8b3024ea94d1563e84e964b7e989413b1f509a5c14f24dadcf6da7e4f9e8559e5f6ff185cbc978fa1693fc0100000046304402205c0fbeff48e49b24848fba7428ea1c821ef4942135d60f51f6a4260e76941ac5022012a051fc518ec6b684a49eaf75631cdfa5574b170ccab6a0612da44585eab5600300000002fc77727661996828f410e89871d981a1c37f951d35d4ed196745d348cc74ca611849670ed23cdc629f56093cb030457bc2accd02f6df375c1a448fc7c824aa5c010d

**gettxoutsetinfo**

Returns statistics about the unspent transaction output set. Note this call may take some time.

**Result:**

{

&#x20; "height":n,                  (numeric) The current block height (index)

&#x20; "bestblock": "hex",          (string) The hash of the block at the tip of the chain

&#x20; "transactions": n,           (numeric) The number of transactions with unspent outputs

&#x20; "txouts": n,                 (numeric) The number of unspent transaction outputs

&#x20; "bogosize": n,               (numeric) A meaningless metric for UTXO set size

&#x20; "hash\_serialized\_2": "hash", (string) The serialized hash

&#x20; "disk\_size": n,              (numeric) The estimated size of the chainstate on disk

&#x20; "total\_amount": x.xxx        (numeric) The total amount

}

**Examples:**

\> Kalycoin -cli gettxoutsetinfo

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "gettxoutsetinfo", "params": \[] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**listcontracts**

list all the contracts and default accounts is 20

**Argument:**

1\. start (numeric or string, optional) The starting account index, default 1

2\. maxDisplay (numeric or string, optional) Max accounts to list, default 20

**Test example:**

\> ./ Kalycoin -cli listcontracts 1 5

**Result:**

&#x20;{

&#x20; "82155d35dc1e0b5dc3d6ca7e536af42394a7003c": 0.00000000,

&#x20; "c50116ca622b4dbd12205fb9cc61a64f7b63cb8a": 0.00000000,

&#x20; "28d1140499604664be0037272eb287e1742dcafe": 0.00000000,

&#x20; "b9fe4ba102c33ba078d90a2cb6fe8fa94fd114a1": 0.00000000,

&#x20; "954999d28fd46c6de806f9587a82321437771ab2": 0.00000000

}

**preciousblock**

Treats a block as if it were received before others with the same work.

A later preciousblock call can override the effect of an earlier one.

The effects of preciousblock are not retained across restarts.

**Arguments:**

1\. "blockhash" (string, required) the hash of the block to mark as precious

**Examples:**

\> Kalycoin -cli preciousblock "blockhash"

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "preciousblock", "params": \["blockhash"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**pruneblockchain**

prune the spend tx to reduce the size of the block

**Arguments:**

1\. "height" (numeric, required) The block height to prune up to. May be set to a discrete height, or a unix timestamp to prune blocks whose block time is at least 2 hours older than the provided timestamp.

**Result:**

n (numeric) Height of the last block pruned.

**Examples:**

\> Kalycoin -cli pruneblockchain 1000

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "pruneblockchain", "params": \[1000] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**savemempool**

Dumps the mempool to disk. It will fail until the previous dump is fully loaded.

**Examples:**

\> Kalycoin -cli savemempool

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "savemempool", "params": \[] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**scantxoutset**

EXPERIMENTAL warning: this call may be removed or changed in future releases.

Scans the unspent transaction output set for entries that match certain output descriptors. Examples of output descriptors are: addr() Outputs whose scriptPubKey corresponds to the specified address (does not include P2PK) raw() Outputs whose scriptPubKey equals the specified hex scripts combo() P2PK, P2PKH, P2WPKH, and P2SH-P2WPKH outputs for the given pubkey pkh() P2PKH outputs for the given pubkey sh(multi(,,,...)) P2SH-multisig outputs for the given threshold and pubkeys

In the above, either refers to a fixed public key in hexadecimal notation, or to an xpub/xprv optionally followed by one or more path elements separated by "/", and optionally ending in "/_" (unhardened), or "/_'" or "/\*h" (hardened) to specify all unhardened or hardened child keys. In the latter case, a range needs to be specified by below if different from 1000. For more information on output descriptors, see the documentation in the doc/descriptors.md file.

**Arguments:**

1\. "action"                       (string, required) The action to execute

&#x20;                                     "start" for starting a scan

&#x20;                                     "abort" for aborting the current scan (returns true when abort was successful)

&#x20;                                     "status" for progress report (in %) of the current scan

2\. "scanobjects"                  (array, required) Array of scan objects

&#x20;   \[                             Every scan object is either a string descriptor or an object:

&#x20;       "descriptor",             (string, optional) An output descriptor

&#x20;       {                         (object, optional) An object with output descriptor and metadata

&#x20;         "desc": "descriptor",   (string, required) An output descriptor

&#x20;         "range": n,             (numeric, optional) Up to what child index HD chains should be explored (default: 1000)

&#x20;       },

&#x20;       ...

&#x20;   ]

**Result:**

&#x20;{

&#x20; "unspents": \[

&#x20;   {

&#x20;   "txid" : "transactionid",     (string) The transaction id

&#x20;   "vout": n,                    (numeric) the vout value

&#x20;   "scriptPubKey" : "script",    (string) the script key

&#x20;   "amount" : x.xxx,             (numeric) The total amount in KLC of the unspent output

&#x20;   "height" : n,                 (numeric) Height of the unspent transaction output

&#x20;  }

&#x20;  ,...],

&#x20;"total\_amount" : x.xxx,          (numeric) The total amount of all found unspent outputs in KLC

]

**searchlogs**

requires -logevents to be enabled

**Arguments:**

1\. "fromBlock"        (numeric, required) The number of the earliest block (latest may be given to mean the most recent block).

2\. "toBlock"          (string, required) The number of the latest block (-1 may be given to mean the most recent block).

3\. "address"          (string, optional) An address or a list of addresses to only get logs from particular account(s).

4\. "topics"           (string, optional) An array of values from which at least one must appear in the log entries. The order is important, if you want to leave topics out use null, e.g. \["null", "0x00..."].

5\. "minconf"          (uint, optional, default=0) Minimal number of confirmations before a log is returned

**Examples:**

\> Kalycoin -cli searchlogs 0 100 '{"addresses": \["12ae42729af478ca92c8c66773a3e32115717be4"]}' '{"topics": \["null","b436c2bf863ccd7b8f63171201efd4792066b4ce8e543dde9c3e9e9ab98e216c"]}'

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "searchlogs", "params": \[0 100 {"addresses": \["12ae42729af478ca92c8c66773a3e32115717be4"]} {"topics": \["null","b436c2bf863ccd7b8f63171201efd4792066b4ce8e543dde9c3e9e9ab98e216c"]}] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**verifychain**

Verifies blockchain database.

**Arguments:**

1\. checklevel (numeric, optional, 0-4, default=3) How thorough the block verification is.

2\. nblocks    (numeric, optional, default=6, 0=all) The number of blocks to check.

**Result:**

true|false (boolean) Verified or not

**Examples:**

\> Kalycoin -cli verifychain

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "verifychain", "params": \[] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**verifytxoutproof**

Verifies that a proof points to a transaction in a block, returning the transaction it commits to and throwing an RPC error if the block is not in our best chain

**Arguments:**

1\. "proof" (string, required) The hex-encoded proof generated by gettxoutproof

**Result:**

\["txid"] (array, strings) The txid(s) which the proof commits to, or empty array if the proof can not be validated.

**Test example:**

verifytxoutproof "0000002081d3145a457b724b725171603a991b8d8186f0506c65722e436a6a33d039690ed689a1e4bdea746f8a3c47d6856765282fb5f7f20c9c43cc9e0170b6ba1214076010135d8683001b0000000052ef386ec7ae80719e408c3ea4193583bd0665fffd633d5e10b19e26375ac9b6386faa7484bfd98fc4789fd584229d5c20f72f772a8b3024ea94d1563e84e964b7e989413b1f509a5c14f24dadcf6da7e4f9e8559e5f6ff185cbc978fa1693fc0100000046304402205c0fbeff48e49b24848fba7428ea1c821ef4942135d60f51f6a4260e76941ac5022012a051fc518ec6b684a49eaf75631cdfa5574b170ccab6a0612da44585eab5600300000002fc77727661996828f410e89871d981a1c37f951d35d4ed196745d348cc74ca611849670ed23cdc629f56093cb030457bc2accd02f6df375c1a448fc7c824aa5c010d"

**Test result:**

\[

&#x20; "5caa24c8c78f441a5c37dff602cdacc27b4530b03c09569f62dc3cd20e674918"

]

**waitforlogs**

waitforlogs (fromBlock) (toBlock) (filter) (minconf) requires -logevents to be enabled

Waits for a new logs and return matching log entries. When the call returns, it also specifies the next block number to start waiting for new logs. By calling waitforlogs repeatedly using the returned nextBlock number, a client can receive a stream of up-to-date log entires.

This call is different from the similarly named waitforlogs. This call returns individual matching log entries, searchlogs returns a transaction receipt if one of the log entries of that transaction matches the filter conditions.

**Arguments:**

1\. fromBlock (int | "latest", optional, default=null) The block number to start looking for logs. ()

2\. toBlock   (int | "latest", optional, default=null) The block number to stop looking for logs. If null, will wait indefinitely into the future.

3\. filter    ({ addresses?: Hex160String\[], topics?: Hex256String\[] }, optional default={}) Filter conditions for logs. Addresses and topics are specified as array of hexadecimal strings

4\. minconf   (uint, optional, default=6) Minimal number of confirmations before a log is returned

**Result:**

An object with the following properties:

1\. logs (LogEntry\[]) Array of matchiing log entries. This may be empty if \`filter\` removed all entries.2. count (int) How many log entries are returned.3. nextBlock (int) To wait for new log entries haven't seen before, use this number as \`fromBlock\`

Usage:

\`waitforlogs\` waits for new logs, starting from the tip of the chain.

\`waitforlogs 600\` waits for new logs, but starting from block 600. If there are logs available, this call will return immediately.

\`waitforlogs 600 700\` waits for new logs, but only up to 700th block

\`waitforlogs null null\` this is equivalent to \`waitforlogs\`, using default parameter values

\`waitforlogs null null\` { "addresses": \[ "ff0011..." ], "topics": \[ "c0fefe"] }\` waits for logs in the future matching the specified conditions

**Sample Output:**

```
{
  "entries": [
    {
      "blockHash": "56d5f1f5ec239ef9c822d9ed600fe9aa63727071770ac7c0eabfc903bf7316d4",
      "blockNumber": 3286,
      "transactionHash": "00aa0f041ce333bc3a855b2cba03c41427cda04f0334d7f6cb0acad62f338ddc",
      "transactionIndex": 2,
      "from": "3f6866e2b59121ada1ddfc8edc84a92d9655675f",
      "to": "8e1ee0b38b719abe8fa984c986eabb5bb5071b6b",
      "cumulativeGasUsed": 23709,
      "gasUsed": 23709,
      "contractAddress": "8e1ee0b38b719abe8fa984c986eabb5bb5071b6b",
      "topics": [
        "f0e1159fa6dc12bb31e0098b7a1270c2bd50e760522991c6f0119160028d9916",
        "0000000000000000000000000000000000000000000000000000000000000002"
      ],
      "data": "00000000000000000000000000000000000000000000000000000000000000010000000000000000000000000000000000000000000000000000000000000003"
    }
  ],
 
  "count": 7,
  "nextblock": 801
}
```

**Control**

**echo**

echo|echojson "message" ...

Simply echo back the input arguments. This command is for testing.

The difference between echo and echojson is that echojson has argument conversion enabled in the client-side table in Kalycoin -cli and the GUI. There is no server-side difference.

**getmemoryinfo**

Returns an object containing information about memory usage.

**Arguments:**

1\. "mode" determines what kind of information is returned. This argument is optional, the default mode is "stats".

&#x20; \- "stats" returns general statistics about memory usage in the daemon.

&#x20; \- "mallocinfo" returns an XML string describing low-level heap state (only available if compiled with glibc 2.10+).

**Result (mode "stats"):**

{

&#x20; "locked": {               (json object) Information about locked memory manager

&#x20;   "used": xxxxx,          (numeric) Number of bytes used

&#x20;   "free": xxxxx,          (numeric) Number of bytes available in current arenas

&#x20;   "total": xxxxxxx,       (numeric) Total number of bytes managed

&#x20;   "locked": xxxxxx,       (numeric) Amount of bytes that succeeded locking. If this number is smaller than total, locking pages failed at some point and key data could be swapped to disk.

&#x20;   "chunks\_used": xxxxx,   (numeric) Number allocated chunks

&#x20;   "chunks\_free": xxxxx,   (numeric) Number unused chunks

&#x20; }

}

**Result (mode "mallocinfo"):**

"\<malloc version="1">..."

**Examples:**

\> Kalycoin -cli getmemoryinfo

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getmemoryinfo", "params": \[] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**help**

List all commands, or get help for a specified command.

**Arguments:**

1\. "command"     (string, optional) The command to get help on

**Result:**

"text"     (string) The help text

**logging**

Gets and sets the logging configuration.

When called without an argument, returns the list of categories with status that are currently being debug logged or not.

When called with arguments, adds or removes categories from debug logging and return the lists above. The arguments are evaluated in order "include", "exclude".

If an item is both included and excluded, it will thus end up being excluded.

The valid logging categories are: net, tor, mempool, http, bench, zmq, db, rpc, estimatefee, addrman, selectcoins, reindex, cmpctblock, rand, prune, proxy, mempoolrej, libevent, coindb, qt, leveldb, coinstake, http-poll.

In addition, the following are available as category names with special meanings:

·         "all", "1" : represent all logging categories.

·         "none", "0" : even if other logging categories are specified, ignore all of them.

**Arguments:**

1\. "include"        (array of strings, optional) A json array of categories to add debug logging

&#x20;    \[

&#x20;      "category"   (string) the valid logging category

&#x20;      ,...

&#x20;    ]

2\. "exclude"        (array of strings, optional) A json array of categories to remove debug logging

&#x20;    \[

&#x20;      "category"   (string) the valid logging category

&#x20;      ,...

&#x20;    ]

**Result:**

{                &#x20;

&#x20; "category": 0|1,  (numeric) if being debug logged or not. 0:inactive, 1:active

&#x20; ...

}

**Examples:**

\> Kalycoin -cli logging "\[\\"all\\"]" "\[\\"http\\"]"

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "logging", "params": \[\["all"], "\[libevent]"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**stop**

Stop Kalycoin server.

**uptime**

Returns the total uptime of the server.

**Result:**

ttt (numeric) The number of seconds that the server has been running

**Examples:**

\> Kalycoin -cli uptime

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "uptime", "params": \[] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**Generating**

**generate**

Mine up to nblocks blocks immediately (before the RPC call returns) to an address in the wallet.

**Arguments:**

1\. nblocks  (numeric, required) How many blocks are generated immediately.

2\. maxtries (numeric, optional) How many iterations to try (default = 1000000).

**Result:**

\[ blockhashes ] (array) hashes of blocks generated

**Examples:**

Generate 11 blocks

&#x20;\> Kalycoin -cli generate 11

**generatetoaddress**

Mine blocks immediately to a specified address (before the RPC call returns)

**Arguments:**

1\. nblocks  (numeric, required) How many blocks are generated immediately.

2\. address  (string, required) The address to send the newly generated Kalycoin to.

3\. maxtries (numeric, optional) How many iterations to try (default = 1000000).

**Result:**

\[ blockhashes ] (array) hashes of blocks generated

**Examples:**

Generate 11 blocks to myaddress

&#x20;

\> Kalycoin -cli generatetoaddress 11 "myaddress"

**Mining**

**getblocktemplate**

If the request parameters include a 'mode' key, that is used to explicitly select between the default 'template' request or a 'proposal'. It returns data needed to construct a block to work on. For full specification, see BIPs 22, 23, 9, and 145: [https://github.com/bitcoin/bips/blob/master/bip-0022.mediawiki](https://github.com/bitcoin/bips/blob/master/bip-0022.mediawiki) [https://github.com/bitcoin/bips/blob/master/bip-0023.mediawiki](https://github.com/bitcoin/bips/blob/master/bip-0023.mediawiki) [https://github.com/bitcoin/bips/blob/master/bip-0009.mediawiki#getblocktemplate\_changes](https://github.com/bitcoin/bips/blob/master/bip-0009.mediawiki#getblocktemplate\_changes) [https://github.com/bitcoin/bips/blob/master/bip-0145.mediawiki](https://github.com/bitcoin/bips/blob/master/bip-0145.mediawiki)

**Arguments:**

1\. template\_request (json object, optional) A json object in the following spec

{

&#x20; "mode":"template" (string, optional) This must be set to "template", "proposal" (see BIP 23), or omitted

&#x20; "capabilities":\[ (array, optional) A list of strings

&#x20; "support" (string) client side supported feature, 'longpoll', 'coinbasetxn', 'coinbasevalue', 'proposal', 'serverlist', 'workid'

&#x20;  ,...

&#x20;   ],

&#x20; "rules":

&#x20;\[

&#x20;   (array, optional) A list of strings

&#x20;   "support" (string) client side supported softfork deployment

&#x20;   ,...

&#x20; ]

}

**Result:**

{

&#x20; "version" : n,                    (numeric) The preferred block version

&#x20; "rules" : \[ "rulename", ... ],    (array of strings) specific block rules that are to be enforced

&#x20; "vbavailable" : {                 (json object) set of pending, supported versionbit (BIP 9) softfork deployments

&#x20;     "rulename" : bitnumber          (numeric) identifies the bit number as indicating acceptance and readiness for the named softfork rule

&#x20;     ,...

&#x20; },

&#x20; "vbrequired" : n,                 (numeric) bit mask of versionbits the server requires set in submissions

&#x20; "previousblockhash" : "xxxx",     (string) The hash of current highest block

&#x20; "transactions" : \[                (array) contents of non-coinbase transactions that should be included in the next block

&#x20;     {

&#x20;        "data" : "xxxx",             (string) transaction data encoded in hexadecimal (byte-for-byte)

&#x20;        "txid" : "xxxx",             (string) transaction id encoded in little-endian hexadecimal

&#x20;        "hash" : "xxxx",             (string) hash encoded in little-endian hexadecimal (including witness data)

&#x20;        "depends" : \[                (array) array of numbers

&#x20;            n                          (numeric) transactions before this one (by 1-based index in 'transactions' list) that must be present in the final block if this one is

&#x20;            ,...

&#x20;        ],

&#x20;        "fee": n,                    (numeric) difference in value between transaction inputs and outputs (in satoshis); for coinbase transactions, this is a negative Number of the total collected block fees (ie, not including the block subsidy); if key is not present, fee is unknown and clients MUST NOT assume there isn't one

&#x20;        "sigops" : n,                (numeric) total SigOps cost, as counted for purposes of block limits; if key is not present, sigop cost is unknown and clients MUST NOT assume it is zero

&#x20;        "weight" : n,                (numeric) total transaction weight, as counted for purposes of block limits

&#x20;     }

&#x20;     ,...

&#x20; ],

&#x20; "coinbaseaux" : {                 (json object) data that should be included in the coinbase's scriptSig content

&#x20;     "flags" : "xx"                  (string) key name is to be ignored, and value included in scriptSig

&#x20; },

&#x20; "coinbasevalue" : n,              (numeric) maximum allowable input to coinbase transaction, including the generation award and transaction fees (in satoshis)

&#x20; "coinbasetxn" : { ... },          (json object) information for coinbase transaction

&#x20; "target" : "xxxx",                (string) The hash target

&#x20; "mintime" : xxx,                  (numeric) The minimum timestamp appropriate for next block time in seconds since epoch (Jan 1 1970 GMT)

&#x20; "mutable" : \[                     (array of string) list of ways the block template may be changed

&#x20;    "value"                          (string) A way the block template may be changed, e.g. 'time', 'transactions', 'prevblock'

&#x20;    ,...

&#x20; ],

&#x20; "noncerange" : "00000000ffffffff",(string) A range of valid nonces

&#x20; "sigoplimit" : n,                 (numeric) limit of sigops in blocks

&#x20; "sizelimit" : n,                  (numeric) limit of block size

&#x20; "weightlimit" : n,                (numeric) limit of block weight

&#x20; "curtime" : ttt,                  (numeric) current timestamp in seconds since epoch (Jan 1 1970 GMT)

&#x20; "bits" : "xxxxxxxx",              (string) compressed target of next block

&#x20; "height" : n                      (numeric) The height of the next block

}  &#x20;

**getmininginfo**

Returns a json object containing mining-related information.

**Examples:**

&#x20;\> Kalycoin -cli getmininginfo&#x20;

&#x20;

&#x20;\>curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getmininginfo", "params": \[] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**Result:**

{

&#x20; "blocks": nnn,             (numeric) The current block

&#x20; "currentblockweight": nnn, (numeric) The last block weight

&#x20; "currentblocktx": nnn,     (numeric) The last block transaction

&#x20; "difficulty": xxx.xxxxx    (numeric) The current difficulty

&#x20; "networkhashps": nnn,      (numeric) The network hashes per second

&#x20; "pooledtx": n              (numeric) The size of the mempool

&#x20; "chain": "xxxx",           (string) current network name as defined in BIP70 (main, test, regtest)

&#x20; "warnings": "..."          (string) any network and blockchain warnings

}

**Test example:**

./ Kalycoin -cli getmininginfo

**Test result:**

&#x20;{

&#x20; "blocks": 401661,

&#x20; "currentblockweight": 4000,

&#x20; "currentblocktx": 0,

&#x20; "difficulty": {

&#x20;   "proof-of-work": 1.52587890625e-005,

&#x20;   "proof-of-stake": 2798173.863126792,

&#x20;   "search-interval": 0

&#x20; },

&#x20; "blockvalue": 400000000,

&#x20; "netmhashps": 0,

&#x20; "netstakeweight": 1335439448399970,

&#x20; "errors": "",

&#x20; "networkhashps": 76789015825010.86,

&#x20; "pooledtx": 2,

&#x20; "stakeweight": {

&#x20;   "minimum": 568351000,

&#x20;   "maximum": 0,

&#x20;   "combined": 568351000

&#x20; },

&#x20; "chain": "main",

&#x20; "warnings": ""

}

**getnetworkhashps**

Returns the estimated network hashes per second based on the last n blocks (for PoW only). Pass in \[blocks] to override # of blocks, -1 specifies since last difficulty change. Pass in \[height] to estimate the network speed at the time when a certain block was found.

**Arguments:**

1\. nblocks (numeric, optional, default=120) The number of blocks, or -1 for blocks since last difficulty change.

2\. height  (numeric, optional, default=-1) To estimate at the time of the given height.

**Result:**

x (numeric) Hashes per second estimated

**Examples:**

\> Kalycoin -cli getnetworkhashps

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getnetworkhashps", "params": \[] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**Test result:**

3.514351301619956e-008

**getstakinginfo**

Returns an object containing staking-related information.

**Example:**

./ Kalycoin -cli getstakinginfo

**Result:**

{

&#x20; "enabled": true or false,(bool),if HD key is enabled, the value if true,else is false.

&#x20; "staking": true or false,(bool),if wallet staking token or not.

&#x20; "errors": "XXX",         (string), any network and blockchain errors

&#x20; "currentblocktx": n,     (numberic),the last block transaction

&#x20; "pooledtx": n,           (numberic), The size of the mempool

&#x20; "difficulty": n,         (numberic),the current proof-of-work difficulty

&#x20; "search-interval": n,

&#x20; "weight": n,             (numberic), the total staking token number

&#x20; "netstakeweight": n,     (numberic), the total numbers of staking in the network

&#x20; "expectedtime": n,       (numberic), the time that to get the rights to cast the block

}

**Test example:**

./ Kalycoin -cli getstakinginfo

**Test result:**

{

&#x20; "enabled": true,

&#x20; "staking": false,

&#x20; "errors": "",

&#x20; "currentblocktx": 0,

&#x20; "pooledtx": 0,

&#x20; "difficulty": 4.656542373906925e-010,

&#x20; "search-interval": 0,

&#x20; "weight": 0,

&#x20; "netstakeweight": 0,

&#x20; "expectedtime": 0

}

**getsubsidy**

Returns subsidy value for the specified value of target.

**prioritisetransaction**

Accepts the transaction into mined blocks at a higher (or lower) priority

**Arguments:**

1\. "txid"         (string, required) The transaction id.

2\. dummy          (numeric, optional) API-Compatibility for previous API. Must be zero or null.

&#x20;                 DEPRECATED. For forward compatibility use named arguments and omit this parameter.

3\. fee\_delta      (numeric, required) The fee value (in satoshis) to add (or subtract, if negative).

&#x20;                 Note, that this value is not a fee rate. It is a value to modify absolute fee of the TX.

&#x20;                 The fee is not actually paid, only the algorithm for selecting transactions into a block

&#x20;                 considers the transaction as it would have paid a higher (or lower) fee.

**Result:**

true (boolean) Returns true

**Examples:**

\> Kalycoin -cli prioritisetransaction "txid" 0.0 10000

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "prioritisetransaction", "params": \["txid", 0.0, 10000] }' -H 'content-type: text/plain;' http://127.0.0.1:3889

**submitblock**

Attempts to submit new block to network. See [https://en.bitcoin.it/wiki/BIP\_0022](https://en.bitcoin.it/wiki/BIP\_0022) for full specification.

**Arguments:**

1\. "hexdata" (string, required) the hex-encoded block data to submit

2\. "dummy" (optional) dummy value, for compatibility with BIP22. This value is ignored.

**Examples:**

\> Kalycoin -cli submitblock "mydata"

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "submitblock", "params": \["mydata"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**Network**

**addnode**

Attempts to add or remove a node from the addnode list. Or try a connection to a node once. Nodes added using addnode (or -connect) are protected from DoS disconnection and are not required to be full nodes/support SegWit as other outbound peers are (though such peers will not be synced from).

**Arguments:**

1\. "node" (string, required) The node (see getpeerinfo for nodes)

&#x20;

2\. "command" (string, required) 'add' to add a node to the list, 'remove' to remove a node from the list, 'onetry' to try a connection to the node once

**Examples:**

\- Mainnet port 3888, Testnet port 13888, Regtest port 23888:

&#x20;

\> Kalycoin -cli addnode "192.168.0.6:3888" "onetry"

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "addnode", "params": \["192.168.0.6:3888", "onetry"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**clearbanned**

Clear all banned IPs.

**Examples:**

\> Kalycoin -cli clearbanned

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "clearbanned", "params": \[] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**disconnectnode**

Immediately disconnects from the specified peer node.

Strictly one out of 'address' and 'nodeid' can be provided to identify the node.

To disconnect by nodeid, either set 'address' to the empty string, or call using the named 'nodeid' argument only.

**Arguments:**

1\. "address"     (string, optional) The IP address/port of the node

2\. "nodeid"      (number, optional) The node ID (see getpeerinfo for node IDs)

**Examples:**

\- Mainnet port 3888, Testnet port 13888, Regtest port 23888:

\-

\> Kalycoin -cli disconnectnode "192.168.0.6:3888"

&#x20;

\> Kalycoin -cli disconnectnode "" 1

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "disconnectnode", "params": \["192.168.0.6:3888"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "disconnectnode", "params": \["", 1] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**estimaterawfee**

WARNING: This interface is unstable and may disappear or change!

WARNING: This is an advanced API call that is tightly coupled to the specific implementation of fee estimation. The parameters it can be called with and the results it returns will change if the internal implementation changes.

Estimates the approximate fee per kilobyte needed for a transaction to begin confirmation within conf\_target blocks if possible. Uses virtual transaction size as defined in BIP 141 (witness data is discounted).

**Arguments:**

1\. conf\_target (numeric) Confirmation target in blocks (1 - 1008)

2\. threshold   (numeric, optional) The proportion of transactions in a given feerate range that must have been

confirmed within conf\_target in order to consider those feerates as high enough and proceed to check

lower buckets. Default: 0.95

**Result:**

{

&#x20; "short" : {                 estimate for short time horizon

&#x20;     "feerate" : x.x,        (numeric, optional) estimate fee rate in KLC /kB

&#x20;     "decay" : x.x,          (numeric) exponential decay (per block) for historical moving average of confirmation data

&#x20;     "scale" : x,            (numeric) The resolution of confirmation targets at this time horizon

&#x20;     "pass" : {              (json object, optional) information about the lowest range of feerates to succeed in meeting the threshold

&#x20;         "startrange" : x.x,     (numeric) start of feerate range

&#x20;         "endrange" : x.x,       (numeric) end of feerate range

&#x20;         "withintarget" : x.x,   (numeric) number of txs over history horizon in the feerate range that were confirmed within target

&#x20;         "totalconfirmed" : x.x, (numeric) number of txs over history horizon in the feerate range that were confirmed at any point

&#x20;         "inmempool" : x.x,      (numeric) current number of txs in mempool in the feerate range unconfirmed for at least target blocks

&#x20;         "leftmempool" : x.x,    (numeric) number of txs over history horizon in the feerate range that left mempool unconfirmed after target

&#x20;     },

&#x20;     "fail" : { ... },       (json object, optional) information about the highest range of feerates to fail to meet the threshold

&#x20;     "errors":  \[ str... ]   (json array of strings, optional) Errors encountered during processing

&#x20; },

&#x20; "medium" : { ... },    (json object, optional) estimate for medium time horizon

&#x20; "long" : { ... }       (json object) estimate for long time horizon

}

&#x20;

Results are returned for any horizon which tracks blocks up to the confirmation target.

**Example:**

\> Kalycoin -cli estimaterawfee 6 0.9

**getaddednodeinfo**

Returns information about the given added node, or all added nodes (note that onetry addnodes are not listed here)

**Arguments:**

1\. "node" (string, optional) If provided, return information about this specific node, otherwise all nodes are returned.

**Result:**

&#x20;\[

&#x20; {

&#x20;   "addednode" : "192.168.0.201",          (string) The node IP address or name (as provided to addnode)

&#x20;   "connected" : true|false,               (boolean) If connected

&#x20;   "addresses" : \[                         (list of objects) Only when connected = true

&#x20;      {

&#x20;        "address" : "192.168.0.201:3888",  (string) The Kalycoin server IP and port we're connected to

&#x20;        "connected" : "outbound"           (string) connection, inbound or outbound

&#x20;      }

&#x20;    ]

&#x20; }

&#x20; ,...

]

**Examples:**

\> Kalycoin -cli getaddednodeinfo "192.168.0.201"

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getaddednodeinfo", "params": \["192.168.0.201"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**getconnectioncount**

Returns the number of connections to other nodes.

**Result:**

n (numeric) The connection count

**Examples:**

\> Kalycoin -cli getconnectioncount

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getconnectioncount", "params": \[] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**Test example:**

./ Kalycoin -cli getconnectioncount

**Test result:**

7

**getnettotals**

Returns information about network traffic, including bytes in, bytes out, and current time.

**Result:**

{

&#x20; "totalbytesrecv": n,                     (numeric) Total bytes received

&#x20; "totalbytessent": n,                     (numeric) Total bytes sent

&#x20; "timemillis": t,                         (numeric) Current UNIX time in milliseconds

&#x20; "uploadtarget":

&#x20; {

&#x20;   "timeframe": n,                        (numeric) Length of the measuring timeframe in seconds

&#x20;   "target": n,                           (numeric) Target in bytes

&#x20;   "target\_reached": true|false,          (boolean) True if target is reached

&#x20;   "serve\_historical\_blocks": true|false, (boolean) True if serving historical blocks

&#x20;   "bytes\_left\_in\_cycle": t,              (numeric) Bytes left in current time cycle

&#x20;   "time\_left\_in\_cycle": t                (numeric) Seconds left in current time cycle

&#x20; }

}

**Examples:**

\> Kalycoin -cli getnettotals

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getnettotals", "params": \[] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**getnetworkinfo**

Returns an object containing various state info regarding P2P networking.

**Result:**

{

&#x20; "version": xxxxx,                      (numeric) the server version

&#x20; "subversion": "/Satoshi:x.x.x/",       (string) the server subversion string

&#x20; "protocolversion": xxxxx,              (numeric) the protocol version

&#x20; "localservices": "xxxxxxxxxxxxxxxx",   (string) the services we offer to the network

&#x20; "localrelay": true|false,              (bool) true if transaction relay is requested from peers

&#x20; "timeoffset": xxxxx,                   (numeric) the time offset

&#x20; "connections": xxxxx,                  (numeric) the number of connections

&#x20; "networkactive": true|false,           (bool) whether p2p networking is enabled

&#x20; "networks": \[                          (array) information per network

&#x20; {

&#x20;   "name": "xxx",                       (string) network (ipv4, ipv6 or onion)

&#x20;   "limited": true|false,               (boolean) is the network limited using -onlynet?

&#x20;   "reachable": true|false,             (boolean) is the network reachable?

&#x20;   "proxy": "host:port"                 (string) the proxy that is used for this network, or empty if none

&#x20;   "proxy\_randomize\_credentials": true|false,  (string) Whether randomized credentials are used

&#x20; }

&#x20; ,...

&#x20; ],

&#x20; "relayfee": x.xxxxxxxx,                (numeric) minimum relay fee for transactions in KLC /kB

&#x20; "incrementalfee": x.xxxxxxxx,          (numeric) minimum fee increment for mempool limiting or BIP 125 replacement in Kalycoin /kB

&#x20; "localaddresses": \[                    (array) list of local addresses

&#x20; {

&#x20;   "address": "xxxx",                   (string) network address

&#x20;   "port": xxx,                         (numeric) network port

&#x20;   "score": xxx                         (numeric) relative score

&#x20; }

&#x20; ,...

&#x20; ]

&#x20; "warnings": "..."                      (string) any network and blockchain warnings

}

**Examples:**

\> Kalycoin -cli getnetworkinfo

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getnetworkinfo", "params": \[] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**getpeerinfo**

Returns data about each connected network node as a json array of objects.

**Result:**

\[

&#x20; {

&#x20;   "id": n,                   (numeric) Peer index

&#x20;   "addr":"host:port",        (string) The IP address and port of the peer

&#x20;   "addrbind":"ip:port",      (string) Bind address of the connection to the peer

&#x20;   "addrlocal":"ip:port",     (string) Local address as reported by the peer

&#x20;   "services":"xxxxxxxxxxxxxxxx",   (string) The services offered

&#x20;   "relaytxes":true|false,    (boolean) Whether peer has asked us to relay transactions to it

&#x20;   "lastsend": ttt,           (numeric) The time in seconds since epoch (Jan 1 1970 GMT) of the last send

&#x20;   "lastrecv": ttt,           (numeric) The time in seconds since epoch (Jan 1 1970 GMT) of the last receive

&#x20;   "bytessent": n,            (numeric) The total bytes sent

&#x20;   "bytesrecv": n,            (numeric) The total bytes received

&#x20;   "conntime": ttt,           (numeric) The connection time in seconds since epoch (Jan 1 1970 GMT)

&#x20;   "timeoffset": ttt,         (numeric) The time offset in seconds

&#x20;   "pingtime": n,             (numeric) ping time (if available)

&#x20;   "minping": n,              (numeric) minimum observed ping time (if any at all)

&#x20;   "pingwait": n,             (numeric) ping wait (if non-zero)

&#x20;   "version": v,              (numeric) The peer version, such as 70001

&#x20;   "subver": "/Satoshi:0.8.5/",  (string) The string version

&#x20;   "inbound": true|false,     (boolean) Inbound (true) or Outbound (false)

&#x20;   "addnode": true|false,     (boolean) Whether connection was due to addnode/-connect or if it was an automatic/inbound connection

&#x20;   "startingheight": n,       (numeric) The starting height (block) of the peer

&#x20;   "banscore": n,             (numeric) The ban score

&#x20;   "synced\_headers": n,       (numeric) The last header we have in common with this peer

&#x20;   "synced\_blocks": n,        (numeric) The last block we have in common with this peer

&#x20;   "inflight": \[

&#x20;      n,                      (numeric) The heights of blocks we're currently asking from this peer

&#x20;      ...

&#x20;   ],

&#x20;   "whitelisted": true|false, (boolean) Whether the peer is whitelisted

&#x20;   "bytessent\_per\_msg": {

&#x20;      "addr": n,              (numeric) The total bytes sent aggregated by message type

&#x20;      ...

&#x20;   },

&#x20;   "bytesrecv\_per\_msg": {

&#x20;      "addr": n,              (numeric) The total bytes received aggregated by message type

&#x20;      ...

&#x20;   }

&#x20; }

&#x20; ,...

]

**Examples:**

\> Kalycoin -cli getpeerinfo

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getpeerinfo", "params": \[] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**Test example:**

./ Kalycoin -cli getpeerinfo

**Test result:**：

&#x20;{

&#x20;   "id": 1479,

&#x20;   "addr": "171.96.72.225:63736",

&#x20;   "addrlocal": "59.46.230.210:3888",

&#x20;   "addrbind": "59.46.230.210:3888",

&#x20;   "services": "000000000000000d",

&#x20;   "relaytxes": true,

&#x20;   "lastsend": 1562045310,

&#x20;   "lastrecv": 1562045263,

&#x20;   "bytessent": 405234,

&#x20;   "bytesrecv": 404534,

&#x20;   "conntime": 1561978028,

&#x20;   "timeoffset": -2,

&#x20;   "pingtime": 0.609372,

&#x20;   "minping": 0.140614,

&#x20;   "version": 70016,

&#x20;   "subver": "/Satoshi:0.14.16/",

&#x20;   "inbound": true,

&#x20;   "addnode": false,

&#x20;   "startingheight": 401184,

&#x20;   "banscore": 0,

&#x20;   "synced\_headers": 401655,

&#x20;   "synced\_blocks": 401650,

&#x20;   "inflight": \[

&#x20;   ],

&#x20;   "whitelisted": false,

&#x20;   "bytessent\_per\_msg": {

&#x20;     "addr": 40437,

&#x20;     "blocktxn": 21843,

&#x20;     "cmpctblock": 77441,

&#x20;     "feefilter": 32,

&#x20;     "getblocktxn": 58,

&#x20;     "getdata": 13753,

&#x20;     "getheaders": 1021,

&#x20;     "headers": 63150,

&#x20;     "inv": 58072,

&#x20;     "notfound": 61,

&#x20;     "ping": 17952,

&#x20;     "pong": 17952,

&#x20;     "reject": 78,

&#x20;     "sendcmpct": 132,

&#x20;     "sendheaders": 24,

&#x20;     "tx": 93042,

&#x20;     "verack": 24,

&#x20;     "version": 162

&#x20;   },

&#x20;   "bytesrecv\_per\_msg": {

&#x20;     "addr": 11595,

&#x20;     "blocktxn": 16722,

&#x20;     "cmpctblock": 4544,

&#x20;     "feefilter": 32,

&#x20;     "getaddr": 24,

&#x20;     "getblocktxn": 2146,

&#x20;     "getdata": 14398,

&#x20;     "getheaders": 1021,

&#x20;     "headers": 101655,

&#x20;     "inv": 97978,

&#x20;     "notfound": 10071,

&#x20;     "ping": 17952,

&#x20;     "pong": 17952,

&#x20;     "reject": 140,

&#x20;     "sendcmpct": 1320,

&#x20;     "sendheaders": 24,

&#x20;     "tx": 106809,

&#x20;     "verack": 24,

&#x20;     "version": 127

&#x20;   },...

&#x20; }

**listbanned**

List all banned IPs/Subnets.

**Examples:**

\> Kalycoin -cli listbanned

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "listbanned", "params": \[] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**ping**

Requests that a ping be sent to all other nodes, to measure ping time. Results provided in getpeerinfo, pingtime and pingwait fields are decimal seconds. Ping command is handled in queue with all other commands, so it measures processing backlog, not just network ping.

**Examples:**

\> Kalycoin -cli ping

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "ping", "params": \[] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**setban**

setban "subnet" "add|remove" (bantime) (absolute)

Attempts to add or remove an IP/Subnet from the banned list.

**Arguments:**

1\. "subnet"       (string, required) The IP/Subnet (see getpeerinfo for nodes IP) with an optional netmask (default is /32 = single IP)

2\. "command"      (string, required) 'add' to add an IP/Subnet to the list, 'remove' to remove an IP/Subnet from the list

3\. "bantime"      (numeric, optional) time in seconds how long (or until when if \[absolute] is set) the IP is banned (0 or empty means using the default time of 24h which can also be overwritten by the -bantime startup argument)

4\. "absolute"     (boolean, optional) If set, the bantime must be an absolute timestamp in seconds since epoch (Jan 1 1970 GMT)

**Examples:**

\> Kalycoin -cli setban "192.168.0.6" "add" 86400

&#x20;

\> Kalycoin -cli setban "192.168.0.0/24" "add"

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "setban", "params": \["192.168.0.6", "add", 86400] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**setnetworkactive**

Disable/enable all p2p network activity.

**Arguments:**

1\. "state" (boolean, required) true to enable networking, false to disable

**Rawtransactions**

**combinepsbt**

Combine multiple partially signed Kalycoin transactions into one transaction. Implements the Combiner role.

**Arguments:**

1\. "txs" (string) A json array of base64 strings of partially signed transactions

\[

&#x20; "psbt" (string) A base64 string of a PSBT

&#x20; ,...

]

**Result:**

"psbt" (string) The base64-encoded partially signed transaction

**Examples:**

\> Kalycoin -cli combinepsbt \["mybase64\_1", "mybase64\_2", "mybase64\_3"]

**combinerawtransaction**

Combine multiple partially signed transactions into one transaction. The combined transaction may be another partially signed transaction or a fully signed transaction.

**Arguments:**

1\. "txs" (string) A json array of hex strings of partially signed transactions

\[

&#x20; "hexstring" (string) A transaction hash

&#x20; ,...

]

**Result:**

"hex" (string) The hex-encoded raw transaction with signature(s)

**Examples:**

\> Kalycoin -cli combinerawtransaction \["myhex1", "myhex2", "myhex3"]

**converttopsbt**

Converts a network serialized transaction to a PSBT. This should be used only with createrawtransaction and fundrawtransaction createpsbt and walletcreatefundedpsbt should be used for new applications.

**Arguments:**

1\. "hexstring"   (string, required) The hex string of a raw transaction

2\. permitsigdata (boolean, optional, default=false) If true, any signatures in the input will be discarded and conversion.

will continue. If false, RPC will fail if any signatures are present.

3\. iswitness     (boolean, optional) Whether the transaction hex is a serialized witness transaction.

If iswitness is not present, heuristic tests will be used in decoding. If true, only witness deserializaion

will be tried. If false, only non-witness deserialization wil be tried. Only has an effect if

permitsigdata is true.

**Result:**

"psbt" (string) The resulting raw transaction (base64-encoded string)

**Examples:**

Create a transaction

\> Kalycoin -cli createrawtransaction "\[{\\"txid\\":\\"myid\\",\\"vout\\":0}]" "\[{\\"data\\":\\"00010203\\"}]"

Convert the transaction to a PSBT

\> Kalycoin -cli converttopsbt "rawtransaction"

**createpsbt**

Creates a transaction in the Partially Signed Transaction format. Implements the Creator role.

**Arguments:**

1\. "inputs"           (array, required) A json array of json objects

\[

&#x20; {

&#x20;   "txid":"id",      (string, required) The transaction id

&#x20;   "vout":n,         (numeric, required) The output number

&#x20;   "sequence":n      (numeric, optional) The sequence number

&#x20; }

&#x20; ,...

]

2\. "outputs"          (array, required) a json array with outputs (key-value pairs), where none of the keys are duplicated.

That is, each address can only appear once and there can only be one 'data' object.

\[

&#x20; {

&#x20;   "address": x.xxx, (obj, optional) A key-value pair. The key (string) is the Kalycoin address, the value (float or string) is the amount in Kalycoin

&#x20; },

&#x20; {

&#x20;   "data": "hex"     (obj, optional) A key-value pair. The key must be "data", the value is hex encoded data

&#x20; },...

&#x20; More key-value pairs of the above form. For compatibility reasons, a dictionary, which holds the key-value pairs directly, is also

accepted as second parameter.

]

3\. locktime           (numeric, optional, default=0) Raw locktime. Non-0 value also locktime-activates inputs

4\. replaceable        (boolean, optional, default=false) Marks this transaction as BIP125 replaceable.

Allows this transaction to be replaced by a transaction with higher fees. If provided, it is an error if explicit sequence numbers are incompatible.

**Result:**

"psbt" (string) The resulting raw transaction (base64-encoded string)

**Examples:**

\> Kalycoin -cli createpsbt "\[{\\"txid\\":\\"myid\\",\\"vout\\":0}]" "\[{\\"data\\":\\"00010203\\"}]"

**createrawtransaction**

createrawtransaction \[{"txid":"id","vout":n},...] \[{"address":amount},{"data":"hex"},...] ( locktime ) ( replaceable )

Create a transaction spending the given inputs and creating new outputs. Outputs can be addresses or data. Returns hex-encoded raw transaction. Note that the transaction's inputs are not signed, and it is not stored in the wallet or transmitted to the network.

**Arguments:**

&#x20;1\. "inputs"               (array, required) A json array of json objects

&#x20;    \[

&#x20;      {

&#x20;        "txid":"id",      (string, required) The transaction id

&#x20;        "vout":n,         (numeric, required) The output number

&#x20;        "sequence":n      (numeric, optional) The sequence number

&#x20;      }

&#x20;      ,...

&#x20;    ]

2\. "outputs"               (array, required) a json array with outputs (key-value pairs), where none of the keys are duplicated.

That is, each address can only appear once and there can only be one 'data' object.

&#x20;  \[

&#x20;   {

&#x20;     "address": x.xxx,    (obj, optional) A key-value pair. The key (string) is the Kalycoin address, the value (float or string) is the amount in Kalycoin

&#x20;   },

&#x20;   {

&#x20;     "data": "hex"        (obj, optional) A key-value pair. The key must be "data", the value is hex encoded data

&#x20;   },

&#x20;   {

&#x20;     "contract":{

&#x20;        "contractAddress":"address",   (string, required) Valid contract address (valid hash160 hex data)

&#x20;        "data":"hex",                  (string, required) Hex data to add in the call output

&#x20;        "amount":x.xxx,                (numeric, optional) Value in KLC to send with the call, should be a valid amount, default 0

&#x20;        "gasLimit":x,                  (numeric, optional) The gas limit for the transaction

&#x20;        "gasPrice":x.xxx               (numeric, optional) The gas price for the transaction

&#x20;      }

&#x20;   {

&#x20;   ,...                     More key-value pairs of the above form. For compatibility reasons, a dictionary, which holds the key-value pairs directly, is also

&#x20;                            accepted as second parameter.

&#x20;  ]

3\. locktime                  (numeric, optional, default=0) Raw locktime. Non-0 value also locktime-activates inputs

4\. replaceable               (boolean, optional, default=false) Marks this transaction as BIP125 replaceable.

&#x20;                            Allows this transaction to be replaced by a transaction with higher fees. If provided, it is an error if explicit sequence numbers are incompatible.

**Result:**

"transaction" (string) hex string of the transaction

**Examples:**

\> Kalycoin -cli createrawtransaction "\[{\\"txid\\":\\"myid\\",\\"vout\\":0}]" "\[{\\"address\\":0.01}]"

&#x20;

\> Kalycoin -cli createrawtransaction "\[{\\"txid\\":\\"myid\\",\\"vout\\":0}]" "\[{\\"data\\":\\"00010203\\"}]"

&#x20;

\> Kalycoin -cli createrawtransaction "\[{\\"txid\\":\\"myid\\",\\"vout\\":0}]" "\[{\\"contract\\":{\\"contractAddress\\":\\"mycontract\\",\\"data\\":\\"00\\", \\"gasLimit\\":250000, \\"gasPrice\\":0.00000040, \\"amount\\":0\}}]"

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "createrawtransaction", "params": \["\[{\\"txid\\":\\"myid\\",\\"vout\\":0}]", "\[{\\"address\\":0.01}]"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "createrawtransaction", "params": \["\[{\\"txid\\":\\"myid\\",\\"vout\\":0}]", "\[{\\"data\\":\\"00010203\\"}]"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "createrawtransaction", "params": \["\[{\\"txid\\":\\"myid\\",\\"vout\\":0}]", "\[{\\"contract\\":{\\"contractAddress\\":\\"mycontract\\",\\"data\\":\\"00\\", \\"gasLimit\\":250000, \\"gasPrice\\":0.00000040, \\"amount\\":0\}}]"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**decodepsbt**

Return a JSON object representing the serialized, base64-encoded partially signed Kalycoin transaction.

**Arguments:**

1\. "psbt" (string, required) The PSBT base64 string

**Result:**

{

&#x20; "tx" : {                   (json object) The decoded network-serialized unsigned transaction.

&#x20;   ...                                      The layout is the same as the output of decoderawtransaction.

&#x20; },

&#x20; "unknown" : {                (json object) The unknown global fields

&#x20;   "key" : "value"            (key-value pair) An unknown key-value pair

&#x20;    ...

&#x20; },

&#x20; "inputs" : \[                 (array of json objects)

&#x20;   {

&#x20;     "non\_witness\_utxo" : {   (json object, optional) Decoded network transaction for non-witness UTXOs

&#x20;       ...

&#x20;     },

&#x20;     "witness\_utxo" : {            (json object, optional) Transaction output for witness UTXOs

&#x20;       "amount" : x.xxx,           (numeric) The value in KLC

&#x20;       "scriptPubKey" : {          (json object)

&#x20;         "asm" : "asm",            (string) The asm

&#x20;         "hex" : "hex",            (string) The hex

&#x20;         "type" : "pubkeyhash",    (string) The type, eg 'pubkeyhash'

&#x20;         "address" : "address"     (string) Kalycoin address if there is one

&#x20;       }

&#x20;     },

&#x20;     "partial\_signatures" : {             (json object, optional)

&#x20;       "pubkey" : "signature",           (string) The public key and signature that corresponds to it.

&#x20;       ,...

&#x20;     }

&#x20;     "sighash" : "type",                  (string, optional) The sighash type to be used

&#x20;     "redeem\_script" : {       (json object, optional)

&#x20;         "asm" : "asm",            (string) The asm

&#x20;         "hex" : "hex",            (string) The hex

&#x20;         "type" : "pubkeyhash",    (string) The type, eg 'pubkeyhash'

&#x20;       }

&#x20;     "witness\_script" : {       (json object, optional)

&#x20;         "asm" : "asm",            (string) The asm

&#x20;         "hex" : "hex",            (string) The hex

&#x20;         "type" : "pubkeyhash",    (string) The type, eg 'pubkeyhash'

&#x20;       }

&#x20;     "bip32\_derivs" : {          (json object, optional)

&#x20;       "pubkey" : {                     (json object, optional) The public key with the derivation path as the value.

&#x20;         "master\_fingerprint" : "fingerprint"     (string) The fingerprint of the master key

&#x20;         "path" : "path",                         (string) The path

&#x20;       }

&#x20;       ,...

&#x20;     }

&#x20;     "final\_scriptsig" : {       (json object, optional)

&#x20;         "asm" : "asm",            (string) The asm

&#x20;         "hex" : "hex",            (string) The hex

&#x20;       }

&#x20;      "final\_scriptwitness": \["hex", ...] (array of string) hex-encoded witness data (if any)

&#x20;     "unknown" : {                (json object) The unknown global fields

&#x20;       "key" : "value"            (key-value pair) An unknown key-value pair

&#x20;        ...

&#x20;     },

&#x20;   }

&#x20;   ,...

&#x20; ]

&#x20; "outputs" : \[                 (array of json objects)

&#x20;   {

&#x20;     "redeem\_script" : {       (json object, optional)

&#x20;         "asm" : "asm",            (string) The asm

&#x20;         "hex" : "hex",            (string) The hex

&#x20;         "type" : "pubkeyhash",    (string) The type, eg 'pubkeyhash'

&#x20;       }

&#x20;     "witness\_script" : {       (json object, optional)

&#x20;         "asm" : "asm",            (string) The asm

&#x20;         "hex" : "hex",            (string) The hex

&#x20;         "type" : "pubkeyhash",    (string) The type, eg 'pubkeyhash'

&#x20;     }

&#x20;     "bip32\_derivs" : \[          (array of json objects, optional)

&#x20;       {

&#x20;         "pubkey" : "pubkey",                     (string) The public key this path corresponds to

&#x20;         "master\_fingerprint" : "fingerprint"     (string) The fingerprint of the master key

&#x20;         "path" : "path",                         (string) The path

&#x20;         }

&#x20;       }

&#x20;       ,...

&#x20;     ],

&#x20;     "unknown" : {                (json object) The unknown global fields

&#x20;       "key" : "value"            (key-value pair) An unknown key-value pair

&#x20;        ...

&#x20;     },

&#x20;   }

&#x20;   ,...

&#x20; ]

&#x20; "fee" : fee                      (numeric, optional) The transaction fee paid if all UTXOs slots in the PSBT have been filled.

}

**Examples:**

\> Kalycoin -cli decodepsbt "psbt"

**decoderawtransaction**

Return a JSON object representing the serialized, hex-encoded transaction.

**Arguments:**

1\. "hexstring" (string, required) The transaction hex string

2\. iswitness   (boolean, optional) Whether the transaction hex is a serialized witness transaction

If iswitness is not present, heuristic tests will be used in decoding

**Result:**

{

&#x20; "txid" : "id",          (string) The transaction id

&#x20; "hash" : "id",          (string) The transaction hash (differs from txid for witness transactions)

&#x20; "size" : n,             (numeric) The transaction size

&#x20; "vsize" : n,            (numeric) The virtual transaction size (differs from size for witness transactions)

&#x20; "weight" : n,           (numeric) The transaction's weight (between vsize\*4 - 3 and vsize\*4)

&#x20; "version" : n,          (numeric) The version

&#x20; "locktime" : ttt,       (numeric) The lock time

&#x20; "vin" : \[               (array of json objects)

&#x20;    {

&#x20;      "txid": "id",      (string) The transaction id

&#x20;      "vout": n,         (numeric) The output number

&#x20;      "scriptSig": {     (json object) The script

&#x20;        "asm": "asm",  (string) asm

&#x20;        "hex": "hex"   (string) hex

&#x20;      },

&#x20;      "txinwitness": \["hex", ...] (array of string) hex-encoded witness data (if any)

&#x20;      "sequence": n     (numeric) The script sequence number

&#x20;    }

&#x20;    ,...

&#x20; ],

&#x20; "vout" : \[             (array of json objects)

&#x20;    {

&#x20;      "value" : x.xxx,            (numeric) The value in KLC

&#x20;      "n" : n,                    (numeric) index

&#x20;      "scriptPubKey" : {          (json object)

&#x20;        "asm" : "asm",          (string) the asm

&#x20;        "hex" : "hex",          (string) the hex

&#x20;        "reqSigs" : n,            (numeric) The required sigs

&#x20;        "type" : "pubkeyhash",  (string) The type, eg 'pubkeyhash'

&#x20;        "addresses" : \[           (json array of string)

&#x20;          "Q2tvKAXCxZjSmdNbao16dKXC8tRWfcF5oc"   (string) Kalycoin address

&#x20;          ,...

&#x20;        ]

&#x20;      }

&#x20;    }

&#x20;    ,...

&#x20; ],

}

**Examples:**

\> Kalycoin -cli decoderawtransaction "hexstring"

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "decoderawtransaction", "params": \["hexstring"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**Test example:**

./ Kalycoin -cli decoderawtransaction "0100000001697f98c004bbb7d184119a31b2b8c96683fa8c7ca0d7755c6196888fb6ba046e010000006a473044022077de54191ae91b502d03a83bd1d580a8b4467fc3d205c7bce169f13e6abc1c91022064f759845c960b04ddf9dd5a635da5f8b990fc934fced06747d52f2658603735012103c426034f05b3b66700f151991e6e45f2d63545a73b36c0a8e8c4200c53f7fd2cfeffffff02a0f53813000000001976a914e85324d4402d9758122c5498de80d1cfcc6330cb88aca09f6636000000001976a914093f4c533deb449f6bd0a427bddb0f02c297101388ac5dad0700"

**Test result:**

{

&#x20; "txid": "27f5f35b447e219d0b3a3ac55f9dc6aacf2d4145fbd930207ef5b7710c47d883",

&#x20; "hash": "27f5f35b447e219d0b3a3ac55f9dc6aacf2d4145fbd930207ef5b7710c47d883",

&#x20; "version": 1,

&#x20; "size": 225,

&#x20; "vsize": 225,

&#x20; "weight": 900,

&#x20; "locktime": 503133,

&#x20; "vin": \[

&#x20;   {

&#x20;     "txid": "6e04bab68f8896615c75d7a07c8cfa8366c9b8b2319a1184d1b7bb04c0987f69",

&#x20;     "vout": 1,

&#x20;     "scriptSig": {

&#x20;       "asm": "3044022077de54191ae91b502d03a83bd1d580a8b4467fc3d205c7bce169f13e6abc1c91022064f759845c960b04ddf9dd5a635da5f8b990fc934fced06747d52f2658603735\[ALL] 03c426034f05b3b66700f151991e6e45f2d63545a73b36c0a8e8c4200c53f7fd2c",

&#x20;       "hex": "473044022077de54191ae91b502d03a83bd1d580a8b4467fc3d205c7bce169f13e6abc1c91022064f759845c960b04ddf9dd5a635da5f8b990fc934fced06747d52f2658603735012103c426034f05b3b66700f151991e6e45f2d63545a73b36c0a8e8c4200c53f7fd2c"

&#x20;     },

&#x20;     "sequence": 4294967294

&#x20;   }

&#x20; ],

&#x20; "vout": \[

&#x20;   {

&#x20;     "value": 3.22500000,

&#x20;     "n": 0,

&#x20;     "scriptPubKey": {

&#x20;       "asm": "OP\_DUP OP\_HASH160 e85324d4402d9758122c5498de80d1cfcc6330cb OP\_EQUALVERIFY OP\_CHECKSIG",

&#x20;       "hex": "76a914e85324d4402d9758122c5498de80d1cfcc6330cb88ac",

&#x20;       "reqSigs": 1,

&#x20;       "type": "pubkeyhash",

&#x20;       "addresses": \[

&#x20;         "QhnQUjuCK7PANDqE7tCdf5DVjKmHoykeSY"

&#x20;       ]

&#x20;     }

&#x20;   },

&#x20;   {

&#x20;     "value": 9.12695200,

&#x20;     "n": 1,

&#x20;     "scriptPubKey": {

&#x20;       "asm": "OP\_DUP OP\_HASH160 093f4c533deb449f6bd0a427bddb0f02c2971013 OP\_EQUALVERIFY OP\_CHECKSIG",

&#x20;       "hex": "76a914093f4c533deb449f6bd0a427bddb0f02c297101388ac",

&#x20;       "reqSigs": 1,

&#x20;       "type": "pubkeyhash",

&#x20;       "addresses": \[

&#x20;         "QMSt24HzDcBQmsqCybzYQmfVPQFvNjK6ax"

&#x20;       ]

&#x20;     }

&#x20;   }

&#x20; ]

}

**decodescript**

Decode a hex-encoded script.

**Arguments:**

1\. "hexstring" (string) the hex encoded script

**Result:**

{

&#x20; "asm":"asm",   (string) Script public key

&#x20; "hex":"hex",   (string) hex encoded public key

&#x20; "type":"type", (string) The output type

&#x20; "reqSigs": n,  (numeric) The required signatures

&#x20; "addresses": \[ (json array of string)

&#x20; "address"      (string) Kalycoin address

&#x20; ,...

&#x20; ],

&#x20; "p2sh","address" (string) address of P2SH script wrapping this redeem script (not returned if the script is already a P2SH).

}

**Examples:**

\> Kalycoin -cli decodescript "hexstring"

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "decodescript", "params": \["hexstring"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

&#x20;

\### finalizepsbt

Finalize the inputs of a PSBT. If the transaction is fully signed, it will produce a network serialized transaction which can be broadcast with sendrawtransaction. Otherwise a PSBT will be created which has the final\_scriptSig and final\_scriptWitness fields filled for inputs that are complete. Implements the Finalizer and Extractor roles.

**Arguments:**

1\. "psbt"    (string) A base64 string of a PSBT

2\. "extract" (boolean, optional, default=true) If true and the transaction is complete, extract and return the complete transaction in normal network serialization instead of the PSBT.

**Result:**

{

&#x20; "psbt" : "value",           (string) The base64-encoded partially signed transaction if not extracted

&#x20; "hex"  : "value",           (string) The hex-encoded network transaction if extracted

&#x20; "complete" : true|false,    (boolean) If the transaction has a complete set of signatures

}

**Examples:**

\> Kalycoin -cli finalizepsbt "psbt"

**fromhexaddress**

Converts a raw hex address to a base58 pubkeyhash address

**Arguments:**

1\. "hexaddress" (string, required) The raw hex address

**Result:**

"address" (string) The base58 pubkeyhash address

**Examples:**

\> Kalycoin -cli fromhexaddress "hexaddress"

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "fromhexaddress", "params": \["hexaddress"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**Test example:**

fromhexaddress "6c89a1a6ca2ae7c00b248bb2832d6f480f27da68"

**Test result:**

qTTH1Yr2eKCuDLqfxUyBLCAjmomQ8pyrBt

**fundrawtransaction**

Add inputs to a transaction until it has enough in value to meet its out value. This will not modify existing inputs, and will add at most one change output to the outputs. No existing outputs will be modified unless "subtractFeeFromOutputs" is specified. Note that inputs which were signed may need to be resigned after completion since in/outputs have been added. The inputs added will not be signed, use signrawtransaction for that. Note that all existing inputs must have their previous output transaction be in the wallet. Note that all inputs selected must be of standard form and P2SH scripts must be in the wallet using importaddress or addmultisigaddress (to calculate fees). You can see whether this is the case by checking the "solvable" field in the listunspent output. Only pay-to-pubkey, multisig, and P2SH versions thereof are currently supported for watch-only

**Arguments:**

1\. "hexstring"                (string, required) The hex string of the raw transaction

2\. options                    (object, optional)

&#x20;  {

&#x20;    "changeAddress"          (string, optional, default pool address) The Kalycoin address to receive the change

&#x20;    "changePosition"         (numeric, optional, default random) The index of the change output

&#x20;    "change\_type"            (string, optional) The output type to use. Only valid if changeAddress is not specified. Options are "legacy", "p2sh-segwit", and "bech32". Default is set by -changetype.

&#x20;    "includeWatching"        (boolean, optional, default false) Also select inputs which are watch only

&#x20;    "lockUnspents"           (boolean, optional, default false) Lock selected unspent outputs

&#x20;    "feeRate"                (numeric, optional, default not set: makes wallet determine the fee) Set a specific fee rate in Kalycoin /kB

&#x20;    "subtractFeeFromOutputs" (array, optional) A json array of integers.

&#x20;                             The fee will be equally deducted from the amount of each specified output.

&#x20;                             The outputs are specified by their zero-based index, before any change output is added.

&#x20;                             Those recipients will receive less Kalycoin s than you enter in their corresponding amount field.

&#x20;                             If no outputs are specified here, the sender pays the fee.

&#x20;                                 \[vout\_index,...]

&#x20;    "replaceable"            (boolean, optional) Marks this transaction as BIP125 replaceable.

&#x20;                             Allows this transaction to be replaced by a transaction with higher fees

&#x20;    "conf\_target"            (numeric, optional) Confirmation target (in blocks)

&#x20;    "estimate\_mode"          (string, optional, default=UNSET) The fee estimate mode, must be one of:

&#x20;        "UNSET"

&#x20;        "ECONOMICAL"

&#x20;        "CONSERVATIVE"

&#x20;  }

&#x20;                             for backward compatibility: passing in a true instead of an object will result in {"includeWatching":true}

3\. iswitness                  (boolean, optional) Whether the transaction hex is a serialized witness transaction

&#x20;                             If iswitness is not present, heuristic tests will be used in decoding

**Result:**

{

&#x20; "hex": "value", (string) The resulting raw transaction (hex-encoded string)

&#x20; "fee": n,       (numeric) Fee in KLC the resulting transaction pays

&#x20; "changepos": n  (numeric) The position of the added change output, or -1

}

**Examples:**

Create a transaction with no inputs

\> Kalycoin -cli createrawtransaction "\[]" "{\\"myaddress\\":0.01}"

Add sufficient unsigned inputs to meet the output value

\> Kalycoin -cli fundrawtransaction "rawtransactionhex"

Sign the transaction

\> Kalycoin -cli signrawtransaction "fundedtransactionhex"

Send the transaction

\> Kalycoin -cli sendrawtransaction "signedtransactionhex"

**gethexaddress**

Converts a base58 pubkeyhash address to a hex address for use in smart contracts.

**Arguments:**

1\. "address" (string, required) The base58 address

**Result:**

"hexaddress" (string) The raw hex pubkeyhash address for use in smart contracts

**Examples:**

\> Kalycoin -cli gethexaddress "address"

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "gethexaddress", "params": \["address"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**Test example:**

gethexaddress "qTTH1Yr2eKCuDLqfxUyBLCAjmomQ8pyrBt"

**Test result:**

6c89a1a6ca2ae7c00b248bb2832d6f480f27da68

**getrawtransaction**

NOTE: By default this function only works for mempool transactions. If the -txindex option is enabled, it also works for blockchain transactions. If the block which contains the transaction is known, its hash can be provided even for nodes without -txindex. Note that if a blockhash is provided, only that block will be searched and if the transaction is in the mempool or other blocks, or if this node does not have the given block available, the transaction will not be found. **DEPRECATED**: for now, it also works for transactions with unspent outputs.

Return the raw transaction data.

If verbose is 'true', returns an Object with information about 'txid'. If verbose is 'false' or omitted, returns a string that is serialized, hex-encoded data for 'txid'.

**Arguments:**

1\. "txid"      (string, required) The transaction id

2\. verbose     (bool, optional, default=false) If false, return a string, otherwise return a json object

3\. "blockhash" (string, optional) The block in which to look for the transaction

&#x20;

Result (if verbose is not set or set to false):

"data"         (string) The serialized, hex-encoded data for 'txid'

&#x20;

Result (if verbose is set to true):

{

&#x20; "in\_active\_chain": b,   (bool) Whether specified block is in the active chain or not (only present with explicit "blockhash" argument)

&#x20; "hex" : "data",         (string) The serialized, hex-encoded data for 'txid'

&#x20; "txid" : "id",          (string) The transaction id (same as provided)

&#x20; "hash" : "id",          (string) The transaction hash (differs from txid for witness transactions)

&#x20; "size" : n,             (numeric) The serialized transaction size

&#x20; "vsize" : n,            (numeric) The virtual transaction size (differs from size for witness transactions)

&#x20; "weight" : n,           (numeric) The transaction's weight (between vsize\*4-3 and vsize\*4)

&#x20; "version" : n,          (numeric) The version

&#x20; "locktime" : ttt,       (numeric) The lock time

&#x20; "vin" : \[               (array of json objects)

&#x20;    {

&#x20;      "txid": "id",      (string) The transaction id

&#x20;      "vout": n,         (numeric)

&#x20;      "scriptSig": {     (json object) The script

&#x20;        "asm": "asm",    (string) asm

&#x20;        "hex": "hex"     (string) hex

&#x20;      },

&#x20;      "sequence": n      (numeric) The script sequence number

&#x20;      "txinwitness": \["hex", ...] (array of string) hex-encoded witness data (if any)

&#x20;    }

&#x20;    ,...

&#x20; ],

&#x20; "vout" : \[            &#x20;

&#x20;    {

&#x20;      "value" : x.xxx,            (numeric) The value in Kalycoin

&#x20;      "n" : n,                    (numeric) index

&#x20;      "scriptPubKey" : {          (json object)

&#x20;        "asm" : "asm",            (string) the asm

&#x20;        "hex" : "hex",            (string) the hex

&#x20;        "reqSigs" : n,            (numeric) The required sigs

&#x20;        "type" : "pubkeyhash",    (string) The type, eg 'pubkeyhash'

&#x20;        "addresses" : \[           (json array of string)

&#x20;          "address"               (string) Kalycoin address

&#x20;          ,...

&#x20;        ]

&#x20;      }

&#x20;    }

&#x20;    ,...

&#x20; ],

&#x20; "blockhash" : "hash",     (string) the block hash

&#x20; "confirmations" : n,      (numeric) The confirmations

&#x20; "time" : ttt,             (numeric) The transaction time in seconds since epoch (Jan 1 1970 GMT)

&#x20; "blocktime" : ttt         (numeric) The block time in seconds since epoch (Jan 1 1970 GMT)

}

**Examples:**

\> Kalycoin -cli getrawtransaction "mytxid"

&#x20;

\> Kalycoin -cli getrawtransaction "mytxid" true

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getrawtransaction", "params": \["mytxid", true] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

&#x20;

\> Kalycoin -cli getrawtransaction "mytxid" false "myblockhash"

&#x20;

\> Kalycoin -cli getrawtransaction "mytxid" true "myblockhash"

**sendrawtransaction**

Submits raw transaction (serialized, hex-encoded) to local node and network.

Also see createrawtransaction and signrawtransaction calls.

**Arguments:**

1\. "hexstring" (string, required) The hex string of the raw transaction)

2\. allowhighfees (boolean, optional, default=false) Allow high fees

**Result:**

"hex" (string) The transaction hash in hex

**Examples:**

Create a transaction

\> Kalycoin -cli createrawtransaction "\[{\\"txid\\" : \\"mytxid\\",\\"vout\\":0}]" "{\\"myaddress\\":0.01}"

Sign the transaction, and get back the hex

\> Kalycoin -cli signrawtransaction "myhex"

Send the transaction (signed hex)

\> Kalycoin -cli sendrawtransaction "signedhex"

As a json rpc call

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "sendrawtransaction", "params": \["signedhex"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**signrawtransaction**

**DEPRECATED**. Sign inputs for raw transaction (serialized, hex-encoded). The second optional argument (may be null) is an array of previous transaction outputs that this transaction depends on but may not yet be in the block chain. The third optional argument (may be null) is an array of base58-encoded private keys that, if given, will be the only keys used to sign the transaction.

**Arguments:**

1\. "hexstring"                      (string, required) The transaction hex string

2\. "prevtxs"       (string, optional) An json array of previous dependent transaction outputs

&#x20;    \[                              (json array of json objects, or 'null' if none provided)

&#x20;      {

&#x20;        "txid":"id",               (string, required) The transaction id

&#x20;        "vout":n,                  (numeric, required) The output number

&#x20;        "scriptPubKey": "hex",     (string, required) script key

&#x20;        "redeemScript": "hex",     (string, required for P2SH or P2WSH) redeem script

&#x20;        "amount": value            (numeric, required) The amount spent

&#x20;      }

&#x20;      ,...

&#x20;   ]

3\. "privkeys"                       (string, optional) A json array of base58-encoded private keys for signing

&#x20;   \[                               (json array of strings, or 'null' if none provided)

&#x20;     "privatekey"                  (string) private key in base58-encoding

&#x20;     ,...

&#x20;   ]

4\. "sighashtype"                    (string, optional, default=ALL) The signature hash type. Must be one of

&#x20;      "ALL"

&#x20;      "NONE"

&#x20;      "SINGLE"

&#x20;      "ALL|ANYONECANPAY"

&#x20;      "NONE|ANYONECANPAY"

&#x20;      "SINGLE|ANYONECANPAY"

**Result:**

{

&#x20; "hex" : "value",               (string) The hex-encoded raw transaction with signature(s)

&#x20; "complete" : true|false,       (boolean) If the transaction has a complete set of signatures

&#x20; "errors" : \[                   (json array of objects) Script verification errors (if there are any)

&#x20;   {

&#x20;     "txid" : "hash",           (string) The hash of the referenced, previous transaction

&#x20;     "vout" : n,                (numeric) The index of the output to spent and used as input

&#x20;     "scriptSig" : "hex",       (string) The hex-encoded signature script

&#x20;     "sequence" : n,            (numeric) Script sequence number

&#x20;     "error" : "text"           (string) Verification or signing error related to the input

&#x20;   }

&#x20;   ,...

&#x20; ]

}

**signrawtransactionwithkey**

Sign inputs for raw transaction (serialized, hex-encoded). The second argument is an array of base58-encoded private keys that will be the only keys used to sign the transaction. The third optional argument (may be null) is an array of previous transaction outputs that this transaction depends on but may not yet be in the block chain.

**Arguments:**

1\. "hexstring"                      (string, required) The transaction hex string

2\. "privkeys"                       (string, required) A json array of base58-encoded private keys for signing

&#x20;   \[                               (json array of strings)

&#x20;     "privatekey"                  (string) private key in base58-encoding

&#x20;     ,...

&#x20;   ]

3\. "prevtxs"                        (string, optional) An json array of previous dependent transaction outputs

&#x20;   \[                               (json array of json objects, or 'null' if none provided)

&#x20;      {

&#x20;        "txid":"id",               (string, required) The transaction id

&#x20;        "vout":n,                  (numeric, required) The output number

&#x20;        "scriptPubKey": "hex",     (string, required) script key

&#x20;        "redeemScript": "hex",     (string, required for P2SH or P2WSH) redeem script

&#x20;        "amount": value            (numeric, required) The amount spent

&#x20;      }

&#x20;      ,...

&#x20;   ]

4\. "sighashtype"                    (string, optional, default=ALL) The signature hash type. Must be one of

&#x20;      "ALL"

&#x20;      "NONE"

&#x20;      "SINGLE"

&#x20;      "ALL|ANYONECANPAY"

&#x20;      "NONE|ANYONECANPAY"

&#x20;      "SINGLE|ANYONECANPAY"

**Result:**

{

&#x20; "hex" : "value",                  (string) The hex-encoded raw transaction with signature(s)

&#x20; "complete" : true|false,          (boolean) If the transaction has a complete set of signatures

&#x20; "errors" : \[                      (json array of objects) Script verification errors (if there are any)

&#x20;   {

&#x20;     "txid" : "hash",              (string) The hash of the referenced, previous transaction

&#x20;     "vout" : n,                   (numeric) The index of the output to spent and used as input

&#x20;     "scriptSig" : "hex",          (string) The hex-encoded signature script

&#x20;     "sequence" : n,               (numeric) Script sequence number

&#x20;     "error" : "text"              (string) Verification or signing error related to the input

&#x20;   }

&#x20;   ,...

&#x20; ]

}

**Examples:**

\> Kalycoin -cli signrawtransactionwithkey "myhex"

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "signrawtransactionwithkey", "params": \["myhex"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**testmempoolaccept**

Returns if raw transaction (serialized, hex-encoded) would be accepted by mempool.

This checks if the transaction violates the consensus or policy rules.

See sendrawtransaction call.

**Arguments:**

1\. \["rawtxs"] (array, required) An array of hex strings of raw transactions. Length must be one for now.

2\. allowhighfees (boolean, optional, default=false) Allow high fees

**Result:**

\[                  (array) The result of the mempool acceptance test for each raw transaction in the input array.

&#x20;                           Length is exactly one for now.

&#x20;{

&#x20; "txid"           (string) The transaction hash in hex

&#x20; "allowed"        (boolean) If the mempool allows this tx to be inserted

&#x20; "reject-reason"  (string) Rejection string (only present when 'allowed' is false)

&#x20;}

]

**Examples:**

Create a transaction

\> Kalycoin -cli createrawtransaction "\[{\\"txid\\" : \\"mytxid\\",\\"vout\\":0}]" "{\\"myaddress\\":0.01}" Sign the transaction, and get back the hex

&#x20;

\> Kalycoin -cli signrawtransaction "myhex"

Test acceptance of the transaction (signed hex)

\> Kalycoin -cli testmempoolaccept \["signedhex"]

As a json rpc call

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "testmempoolaccept", "params": \[\["signedhex"]] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**Util**

**createmultisig**

Creates a multi-signature address with n signature of m keys required. It returns a json object with the address and redeemScript.

**Arguments:**

1\. nrequired                    (numeric, required) The number of required signatures out of the n keys.

2\. "keys"                       (string, required) A json array of keys which are Kalycoin addresses or hex-encoded public keys

&#x20;    \[

&#x20;      "key"                    (string) Kalycoin address or hex-encoded public key

&#x20;      ,...

&#x20;    ]

3\. "address\_type"               (string, optional) The address type to use. Options are "legacy", "p2sh-segwit", and "bech32". Default is legacy.

**Result:**

{

&#x20; "address":"multisigaddress",  (string) The value of the new multisig address.

&#x20; "redeemScript":"script"       (string) The string value of the hex-encoded redemption script.

}

**Examples:**

Create a multisig address from 2 public keys

\> Kalycoin -cli createmultisig 2 "\[\\"QjWnDZxwLhrJDcp4Hisse8RfBo2jRDZY5Z\\",\\"Q6sSauSf5pF2UkUwvKGq4qjNRzBZYqgEL5\\"]"

As a json rpc call

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "createmultisig", "params": \[2, "\[\\"QjWnDZxwLhrJDcp4Hisse8RfBo2jRDZY5Z\\",\\"Q6sSauSf5pF2UkUwvKGq4qjNRzBZYqgEL5\\"]"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**estimatesmartfee**

Estimates the approximate fee per kilobyte needed for a transaction to begin confirmation within conf\_target blocks if possible and return the number of blocks for which the estimate is valid. Uses virtual transaction size as defined in BIP 141 (witness data is discounted).

**Arguments:**

1\. conf\_target     (numeric) Confirmation target in blocks (1 - 1008)

2\. "estimate\_mode" (string, optional, default=CONSERVATIVE) The fee estimate mode.

&#x20;                  Whether to return a more conservative estimate which also satisfies

&#x20;                  a longer history. A conservative estimate potentially returns a

&#x20;                  higher feerate and is more likely to be sufficient for the desired

&#x20;                  target, but is not as responsive to short term drops in the

&#x20;                  prevailing fee market.  Must be one of:

&#x20;      "UNSET" (defaults to CONSERVATIVE)

&#x20;      "ECONOMICAL"

&#x20;      "CONSERVATIVE"

**Result:**

{

&#x20; "feerate" : x.x,     (numeric, optional) estimate fee-per-kilobyte (in KLC)

&#x20; "errors": \[ str... ] (json array of strings, optional) Errors encountered during processing

&#x20; "blocks" : n         (numeric) block number where estimate was found

}

The request target will be clamped between 2 and the highest target fee estimation is able to return based on how long it has been running. An error is returned if not enough transactions and blocks have been observed to make an estimate for any number of blocks.

**Example:**

\> Kalycoin -cli estimatesmartfee 6

**signmessagewithprivkey**

Sign a message with the private key of an address

**Arguments:**

1\. "privkey"         (string, required) The private key to sign the message with.

2\. "message"         (string, required) The message to create a signature of.

**Result:**

"signature"          (string) The signature of the message encoded in base 64

**Examples:**

Create the signature

\> Kalycoin -cli signmessagewithprivkey "privkey" "my message"

Verify the signature

\> Kalycoin -cli verifymessage "QD1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX" "signature" "my message"

As json rpc

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "signmessagewithprivkey", "params": \["privkey", "my message"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**validateaddress**

Return information about the given Kalycoin address.

**DEPRECATION WARNING:** Parts of this command have been deprecated and moved to getaddressinfo. Clients must transition to using getaddressinfo to access this information before upgrading to v0.18. The following deprecated fields have moved to getaddressinfo and will only be shown here with -deprecatedrpc=validateaddress: ismine, iswatchonly, script, hex, pubkeys, sigsrequired, pubkey, addresses, embedded, iscompressed, account, timestamp, hdkeypath, kdmasterkeyid.

**Arguments:**

1\. "address" (string, required) The Kalycoin address to validate

**Result:**

{

&#x20; "isvalid" : true|false,       (boolean) If the address is valid or not. If not, this is the only property returned.

&#x20; "address" : "address",        (string) The Kalycoin address validated

&#x20; "scriptPubKey" : "hex",       (string) The hex encoded scriptPubKey generated by the address

&#x20; "isscript" : true|false,      (boolean) If the key is a script

&#x20; "iswitness" : true|false,     (boolean) If the address is a witness address

&#x20; "witness\_version" : version   (numeric, optional) The version number of the witness program

&#x20; "witness\_program" : "hex"     (string, optional) The hex value of the witness program

}

**Examples:**

\> Kalycoin -cli validateaddress "QPSSGeFHDnKNxiEyFrD1wcEaHr9hrQDDWc"

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "validateaddress", "params": \["QPSSGeFHDnKNxiEyFrD1wcEaHr9hrQDDWc"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**verifymessage**

Verify a signed message

**Arguments:**

1\. "address" (string, required) The Kalycoin address to use for the signature.

2\. "signature" (string, required) The signature provided by the signer in base 64 encoding (see signmessage).

3\. "message" (string, required) The message that was signed.

**Result:**

true|false (boolean) If the signature is verified or not.

**Examples:**

Unlock the wallet for 30 seconds

\> Kalycoin -cli walletpassphrase "mypassphrase" 30

Create the signature

\> Kalycoin -cli signmessage "QD1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX" "my message"

Verify the signature

\> Kalycoin -cli verifymessage "QD1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX" "signature" "my message"

As json rpc

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "verifymessage", "params": \["QD1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX", "signature", "my message"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**Wallet**

**abandontransaction**

Mark in-wallet transaction as abandoned This will mark this transaction and all its in-wallet descendants as abandoned which will allow for their inputs to be respent. It can be used to replace "stuck" or evicted transactions. It only works on transactions which are not included in a block and are not currently in the mempool. It has no effect on transactions which are already abandoned.

**Arguments:**

1\. "txid" (string, required) The transaction id

**Examples:**

\> Kalycoin -cli abandontransaction "1075db55d416d3ca199f55b6084e2115b9345e16c5cf302fc80e9d5fbf5d48d"

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "abandontransaction", "params": \["1075db55d416d3ca199f55b6084e2115b9345e16c5cf302fc80e9d5fbf5d48d"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**abortrescan**

Stops current wallet rescan triggered by an RPC call, e.g. by an importprivkey call.

**Examples:**

Import a private key

\> Kalycoin -cli importprivkey "mykey"

Abort the running wallet rescan

\> Kalycoin -cli abortrescan

As a JSON-RPC call

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "abortrescan", "params": \[] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**Test example:**

./ Kalycoin -cli abortrescan

**Test result:**

false

**addmultisigaddress**

Add a nrequired-to-sign multisignature address to the wallet. Requires a new wallet backup. Each key is a Kalycoin address or hex-encoded public key. This functionality is only intended for use with non-watchonly addresses. See importaddress for watchonly p2sh address support. If 'label' is specified, assign address to that label.

**Arguments:**

1\. nrequired                      (numeric, required) The number of required signatures out of the n keys or addresses.

2\. "keys"                         (string, required) A json array of Kalycoin addresses or hex-encoded public keys

&#x20;    \[

&#x20;      "address"                  (string) Kalycoin address or hex-encoded public key

&#x20;      ...,

&#x20;    ]

3\. "label"                        (string, optional) A label to assign the addresses to.

4\. "address\_type"                 (string, optional) The address type to use. Options are "legacy", "p2sh-segwit", and "bech32". Default is set by -addresstype

**Result:**

{

&#x20; "address":"multisigaddress", (string) The value of the new multisig address.

&#x20; "redeemScript":"script"      (string) The string value of the hex-encoded redemption script.

}

**Examples:**

Add a multisig address from 2 addresses

\> Kalycoin -cli addmultisigaddress 2 "\[\\"QjWnDZxwLhrJDcp4Hisse8RfBo2jRDZY5Z\\",\\"Q6sSauSf5pF2UkUwvKGq4qjNRzBZYqgEL5\\"]"

As json rpc call

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "addmultisigaddress", "params": \[2, "\[\\"QjWnDZxwLhrJDcp4Hisse8RfBo2jRDZY5Z\\",\\"Q6sSauSf5pF2UkUwvKGq4qjNRzBZYqgEL5\\"]"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**backupwallet**

Safely copies current wallet file to destination, which can be a directory or a path with filename.

**Arguments:**

1\. "destination" (string) The destination directory or file

**Examples:**

\> Kalycoin -cli backupwallet "backup.dat"

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "backupwallet", "params": \["backup.dat"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**bumpfee**

Bumps the fee of an opt-in-RBF transaction T, replacing it with a new transaction B. An opt-in RBF transaction with the given txid must be in the wallet. The command will pay the additional fee by decreasing (or perhaps removing) its change output. If the change output is not big enough to cover the increased fee, the command will currently fail instead of adding new inputs to compensate. (A future implementation could improve this.) The command will fail if the wallet or mempool contains a transaction that spends one of T's outputs. By default, the new fee will be calculated automatically using estimatesmartfee. The user can specify a confirmation target for estimatesmartfee. Alternatively, the user can specify totalFee, or use RPC settxfee to set a higher fee rate. At a minimum, the new fee rate must be high enough to pay an additional new relay fee (incrementalfee returned by getnetworkinfo) to enter the node's mempool.

**Arguments:**

1\. txid                  (string, required) The txid to be bumped

2\. options               (object, optional)

&#x20;  {

&#x20;    "confTarget"        (numeric, optional) Confirmation target (in blocks)

&#x20;    "totalFee"          (numeric, optional) Total fee (NOT feerate) to pay, in satoshis.

&#x20;                        In rare cases, the actual fee paid might be slightly higher than the specified

&#x20;                        totalFee if the tx change output has to be removed because it is too close to

&#x20;                        the dust threshold.

&#x20;    "replaceable"       (boolean, optional, default true) Whether the new transaction should still be

&#x20;                        marked bip-125 replaceable. If true, the sequence numbers in the transaction will

&#x20;                        be left unchanged from the original. If false, any input sequence numbers in the

&#x20;                        original transaction that were less than 0xfffffffe will be increased to 0xfffffffe

&#x20;                        so the new transaction will not be explicitly bip-125 replaceable (though it may

&#x20;                        still be replaceable in practice, for example if it has unconfirmed ancestors which

&#x20;                        are replaceable).

&#x20;    "estimate\_mode"     (string, optional, default=UNSET) The fee estimate mode, must be one of:

&#x20;        "UNSET"

&#x20;        "ECONOMICAL"

&#x20;        "CONSERVATIVE"

&#x20;  }

**Result:**

{

&#x20; "txid": "value",     (string) The id of the new transaction

&#x20; "origfee": n,        (numeric) Fee of the replaced transaction

&#x20; "fee": n,            (numeric) Fee of the new transaction

&#x20; "errors": \[ str... ] (json array of strings) Errors encountered during processing (may be empty)

}

**Examples:**

Bump the fee, get the new transaction's txid

&#x20;

\> Kalycoin -cli bumpfee \<txid>

**createcontract**

Create a contract with bytcode.

**Arguments:**

1\. "bytecode"       (string, required) contract bytcode.

2\. gasLimit         (numeric or string, optional) gasLimit, default: 2500000, max: 40000000

3\. gasPrice         (numeric or string, optional) gasPrice KLC price per gas unit, default: 0.0000004, min:0.0000004

4\. "senderaddress"  (string, optional) The Kalycoin address that will be used to create the contract.

5\. "broadcast"      (bool, optional, default=true) Whether to broadcast the transaction or not.

6\. "changeToSender" (bool, optional, default=true) Return the change to the sender.

**Result:**

\[

&#x20; {

&#x20;   "txid" :    (string) The transaction id.

&#x20;   "sender" :  (string) KLC address of the sender.

&#x20;   "hash160" : (string) ripemd-160 hash of the sender.

&#x20;   "address" : (string) expected contract address.

}

]

**Examples:**

\> Kalycoin -cli createcontract "60606040525b33600060006101000a81548173ffffffffffffffffffffffffffffffffffffffff02191690836c010000000000000000000000009081020402179055506103786001600050819055505b600c80605b6000396000f360606040526008565b600256"

&#x20;

\> Kalycoin -cli createcontract "60606040525b33600060006101000a81548173ffffffffffffffffffffffffffffffffffffffff02191690836c010000000000000000000000009081020402179055506103786001600050819055505b600c80605b6000396000f360606040526008565b600256" 6000000 0.0000004 "QM72Sfpbz1BPpXFHz9m3CdqATR44Jvaydd" true

**createwallet**

Creates and loads a new wallet.

**Arguments:**

1\. "wallet\_name"        (string, required) The name for the new wallet. If this is a path, the wallet will be created at the path location.

2\. disable\_private\_keys (boolean, optional, default: false) Disable the possibility of private keys (only watchonlys are possible in this mode).

**Result:**

{

&#x20; "name" :    \<wallet\_name>, (string) The wallet name if created successfully. If the wallet was created using a full path, the wallet\_name will be the full path.

&#x20; "warning" : \<warning>,     (string) Warning message if wallet was not loaded cleanly.

}

**Examples:**

\> Kalycoin -cli createwallet "testwallet"

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "createwallet", "params": \["testwallet"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**Test example:**

createwallet “ancd”

**Test result:**

&#x20; {

&#x20;   "name": "ancd",

&#x20;   "warning": ""

&#x20; }

**dumpprivkey**

Reveals the private key corresponding to 'address'. Then the importprivkey can be used with this output

**Arguments:**

1\. "address"   (string, required) The Kalycoin address for the private key

**Result:**

"key"                (string) The private key

**Examples:**

\> Kalycoin -cli dumpprivkey "myaddress"

&#x20;

\> Kalycoin -cli importprivkey "mykey"

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "dumpprivkey", "params": \["myaddress"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**dumpwallet**

Dumps all wallet keys in a human-readable format to a server-side file. This does not allow overwriting existing files.

**Arguments:**

1\. "filename"    (string, required) The filename with path (either absolute or relative to Kalycoin d)

**Result:**

{

&#x20;

&#x20; "filename" :  (string) The filename with full absolute path

&#x20;

}

**Examples:**

\> Kalycoin -cli dumpwallet "test"

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "dumpwallet", "params": \["test"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**encryptwallet**

Encrypts the wallet with 'passphrase'. This is for first time encryption. After this, any calls that interact with private keys such as sending or signing will require the passphrase to be set prior the making these calls. Use the walletpassphrase call for this, and then walletlock call. If the wallet is already encrypted, use the wallet passphrase change call. Note that this will shutdown the server.

**Arguments:**

1\. "passphrase" (string) The pass phrase to encrypt the wallet with. It must be at least 1 character, but should be long.

**Examples:**

Encrypt your wallet

\> Kalycoin -cli encryptwallet "my pass phrase"

Now set the passphrase to use the wallet, such as for signing or sending Kalycoin

\> Kalycoin -cli walletpassphrase "my pass phrase"

Now we can do something like sign

\> Kalycoin -cli signmessage "address" "test message"

Now lock the wallet again by removing the passphrase

\> Kalycoin -cli walletlock

As a json rpc call

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "encryptwallet", "params": \["my pass phrase"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**getaddressesbylabel**

Returns the list of addresses assigned the specified label.

**Arguments:**

1\. "label" (string, required) The label.

**Result:**

{

&#x20; "address":

&#x20; {

&#x20;   "purpose": "string" (string) Purpose of address ("send" for sending address, "receive" for receiving address)

&#x20; },...

}

**Examples:**

\> Kalycoin -cli getaddressesbylabel "tabby"

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getaddressesbylabel", "params": \["tabby"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**Test example:**

./ Kalycoin -cli getaddressesbylabel ""

**Test result:**

{

&#x20;   "QUTYNrXYMQUzZyUekmfakR8bzTuLqYcLtf":

&#x20;   {

&#x20;     "purpose": "receive"

&#x20;   },

&#x20;   "QZmURd7wViLVKjUu8b3mvdXeSJjFmH7hf2":

&#x20;   {

&#x20;     "purpose": "receive"

&#x20;   }

}

**getaddressinfo**

Return information about the given Kalycoin address. Some information requires the address to be in the wallet.

**Arguments:**

1\. "address"                    (string, required) The Kalycoin address to get the information of.

**Result:**

{

&#x20; "address" : "address",        (string) The Kalycoin address validated

&#x20; "scriptPubKey" : "hex",       (string) The hex encoded scriptPubKey generated by the address

&#x20; "ismine" : true|false,        (boolean) If the address is yours or not

&#x20; "iswatchonly" : true|false,   (boolean) If the address is watchonly

&#x20; "isscript" : true|false,      (boolean) If the key is a script

&#x20; "iswitness" : true|false,     (boolean) If the address is a witness address

&#x20; "witness\_version" : version   (numeric, optional) The version number of the witness program

&#x20; "witness\_program" : "hex"     (string, optional) The hex value of the witness program

&#x20; "script" : "type"             (string, optional) The output script type. Only if "isscript" is true and the redeemscript is known. Possible types: nonstandard, pubkey, pubkeyhash, scripthash, multisig, nulldata, witness\_v0\_keyhash, witness\_v0\_scripthash, witness\_unknown

&#x20; "hex" : "hex",                (string, optional) The redeemscript for the p2sh address

&#x20; "pubkeys"                     (string, optional) Array of pubkeys associated with the known redeemscript (only if "script" is "multisig")

&#x20;   \[

&#x20;     "pubkey"

&#x20;     ,...

&#x20;   ]

&#x20; "sigsrequired" : xxxxx        (numeric, optional) Number of signatures required to spend multisig output (only if "script" is "multisig")

&#x20; "pubkey" : "publickeyhex",    (string, optional) The hex value of the raw public key, for single-key addresses (possibly embedded in P2SH or P2WSH)

&#x20; "embedded" : {...},           (object, optional) Information about the address embedded in P2SH or P2WSH, if relevant and known. It includes all getaddressinfo output fields for the embedded address, excluding metadata ("timestamp", "hdkeypath", "hdseedid") and relation to the wallet ("ismine", "iswatchonly", "account").

&#x20; "iscompressed" : true|false,  (boolean) If the address is compressed

&#x20; "label" :  "label"            (string) The label associated with the address, "" is the default account

&#x20; "account" : "account"         (string) DEPRECATED. This field will be removed in V0.18. To see this deprecated field, start Kalycoin d with -deprecatedrpc=accounts. The account associated with the address, "" is the default account

&#x20; "timestamp" : timestamp,      (number, optional) The creation time of the key if available in seconds since epoch (Jan 1 1970 GMT)

&#x20; "hdkeypath" : "keypath"       (string, optional) The HD keypath if the key is HD and available

&#x20; "hdseedid" : "\<hash160>"      (string, optional) The Hash160 of the HD seed

&#x20; "hdmasterkeyid" : "\<hash160>" (string, optional) alias for hdseedid maintained for backwards compatibility. Will be removed in V0.18.

&#x20; "labels"                      (object) Array of labels associated with the address.

&#x20;   \[

&#x20;     { (json object of label data)

&#x20;       "name": "labelname"     (string) The label

&#x20;       "purpose": "string"     (string) Purpose of address ("send" for sending address, "receive" for receiving address)

&#x20;     },...

&#x20;   ]

}

**Examples:**

\> Kalycoin -cli getaddressinfo "QZCAJ4qLJpNW74Cbgtnav18wYxQ9wX4V3h"

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getaddressinfo", "params": \["QZCAJ4qLJpNW74Cbgtnav18wYxQ9wX4V3h"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**Test example:**

./ Kalycoin -cli getaddressinfo "QZCAJ4qLJpNW74Cbgtnav18wYxQ9wX4V3h"

**Test result:**

{

&#x20; "address": "QZCAJ4qLJpNW74Cbgtnav18wYxQ9wX4V3h",

&#x20; "scriptPubKey": "76a9148a1827980248580e401055e52c9617cfbbe7efbf88ac",

&#x20; "ismine": true,

&#x20; "iswatchonly": false,

&#x20; "isscript": false,

&#x20; "iswitness": false,

&#x20; "pubkey": "0397a9f2710a0ac5a1ee1345893be6d903fc9e7c79479ab6a4067064731d009a73",

&#x20; "iscompressed": true,

&#x20; "label": "",

&#x20; "timestamp": 1562060128,

&#x20; "hdkeypath": "m/88'/0'/0'",

&#x20; "hdseedid": "96d04ecdab5e6ddeb20b8c62c98cf3a7548ab07d",

&#x20; "hdmasterkeyid": "96d04ecdab5e6ddeb20b8c62c98cf3a7548ab07d",

&#x20; "labels": \[

&#x20;   {

&#x20;     "name": "",

&#x20;     "purpose": "receive"

&#x20;   }

&#x20; ]

}

**getbalance**

Returns the total available balance. The available balance is what the wallet considers currently spendable, and is thus affected by options which limit spendability such as -spendzeroconfchange.

**Arguments:**

1\. (dummy)           (string, optional) Remains for backward compatibility. Must be excluded or set to "\*".

2\. minconf           (numeric, optional, default=0) Only include transactions confirmed at least this many times.

3\. include\_watchonly (bool, optional, default=false) Also include balance in watch-only addresses (see 'importaddress')

**Result:**

amount              (numeric) The total amount in KLC received for this account.

**Examples:**

The total amount in the wallet with 1 or more confirmations

\> Kalycoin -cli getbalance

The total amount in the wallet at least 6 blocks confirmed

\> Kalycoin -cli getbalance "\*" 6

As a json rpc call

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getbalance", "params": \["\*", 6] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**Test example:**

./ Kalycoin -cli getbalance

**Test result:**

5.683000

**getnewaddress**

Returns a new Kalycoin address for receiving payments. If 'label' is specified, it is added to the address book so payments received with the address will be associated with 'label'.

**Arguments:**

1\. "label" (string, optional) The label name for the address to be linked to. If not provided, the default label "" is used. It can also be set to the empty string "" to represent the default label. The label does not need to exist, it will be created if there is no label by the given name.

2\. "address\_type" (string, optional) The address type to use. Options are "legacy", "p2sh-segwit", and "bech32". Default is set by -addresstype.

**Result:**

"address" (string) The new Kalycoin address

**Examples:**

\> Kalycoin -cli getnewaddress

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getnewaddress", "params": \[] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**Test example:**

./ Kalycoin -cli getnewaddress

**Test result:**

QcMKCuHMFwwGNBdYYes8vKN1Qm1MJkwsQf

**getrawchangeaddress**

Returns a new Kalycoin address, for receiving change. This is for use with raw transactions, NOT normal use.

**Arguments:**

1\. "address\_type"           (string, optional) The address type to use. Options are "legacy", "p2sh-segwit", and "bech32". Default is set by -changetype.

**Result:**

"address"    (string) The address

**Examples:**

\> Kalycoin -cli getrawchangeaddress

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getrawchangeaddress", "params": \[] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**Test example:**

./ Kalycoin -cli getrawchangeaddress

**Test result:**

QhPwqZNWgcgJRZpRH21hs3b2g8PooeaoPt

**getreceivedbyaddress**

Returns the total amount received by the given address in transactions with at least minconf confirmations.

**Arguments:**

1\. "address"         (string, required) The Kalycoin address for transactions.

2\. minconf             (numeric, optional, default=1) Only include transactions confirmed at least this many times.

**Result:**

amount (numeric) The total amount in KLC received at this address.

**Examples:**

The amount from transactions with at least 1 confirmation

\> Kalycoin -cli getreceivedbyaddress "QD1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX"

The amount including unconfirmed transactions, zero confirmations

\> Kalycoin -cli getreceivedbyaddress "QD1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX" 0

The amount with at least 6 confirmations, very safe

\> Kalycoin -cli getreceivedbyaddress "QD1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX" 6

As a json rpc call

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getreceivedbyaddress", "params": \["QD1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX", 6] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**gettransaction**

Get detailed information about in-wallet transaction

**Arguments:**

1\. "txid"                  (string, required) The transaction id

2\. "include\_watchonly"     (bool, optional, default=false) Whether to include watch-only addresses in balance calculation and details\[]

3\. "waitconf"              (int, optional, default=0) Wait for enough confirmations before returning

**Result:**

{

&#x20; "amount" : x.xxx,        (numeric) The transaction amount in KLC

&#x20; "fee": x.xxx,            (numeric) The amount of the fee in KKC. This is negative and only available for the

&#x20;                             'send' category of transactions.

&#x20; "confirmations" : n,     (numeric) The number of confirmations

&#x20; "blockhash" : "hash",    (string) The block hash

&#x20; "blockindex" : xx,       (numeric) The index of the transaction in the block that includes it

&#x20; "blocktime" : ttt,       (numeric) The time in seconds since epoch (1 Jan 1970 GMT)

&#x20; "txid" : "transactionid",   (string) The transaction id.

&#x20; "time" : ttt,            (numeric) The transaction time in seconds since epoch (1 Jan 1970 GMT)

&#x20; "timereceived" : ttt,    (numeric) The time received in seconds since epoch (1 Jan 1970 GMT)

&#x20; "bip125-replaceable": "yes|no|unknown",  (string) Whether this transaction could be replaced due to BIP125 (replace-by-fee);

&#x20;                                                  may be unknown for unconfirmed transactions not in the mempool

&#x20; "details" : \[

&#x20;   {

&#x20;     "account" : "accountname",        (string) DEPRECATED. This field will be removed in a V0.18. To see this deprecated field, start Kalycoin d with -deprecatedrpc=accounts. The account name involved in the transaction, can be "" for the default account.

&#x20;     "address" : "address",            (string) The Kalycoin address involved in the transaction

&#x20;     "category" : "send|receive",      (string) The category, either 'send' or 'receive'

&#x20;     "amount" : x.xxx,                 (numeric) The amount in KLC

&#x20;     "label" : "label",                (string) A comment for the address/transaction, if any

&#x20;     "vout" : n,                       (numeric) the vout value

&#x20;     "fee": x.xxx,                     (numeric) The amount of the fee in KLC. This is negative and only available for the

&#x20;                                          'send' category of transactions.

&#x20;     "abandoned": xxx                  (bool) 'true' if the transaction has been abandoned (inputs are respendable). Only available for the

&#x20;                                          'send' category of transactions.

&#x20;   }

&#x20;   ,...

&#x20; ],

&#x20; "hex" : "data"                        (string) Raw data for transaction

}

**Examples:**

\> Kalycoin -cli gettransaction "1075db55d416d3ca199f55b6084e2115b9345e16c5cf302fc80e9d5fbf5d48d"

&#x20;

\> Kalycoin -cli gettransaction "1075db55d416d3ca199f55b6084e2115b9345e16c5cf302fc80e9d5fbf5d48d" true

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "gettransaction", "params": \["1075db55d416d3ca199f55b6084e2115b9345e16c5cf302fc80e9d5fbf5d48d"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**getunconfirmedbalance**

Returns the server's total unconfirmed balance

**getwalletinfo**

Returns an object containing various wallet state info.

**Result:**

{

&#x20; "walletname": xxxxx,               (string) the wallet name

&#x20; "walletversion": xxxxx,            (numeric) the wallet version

&#x20; "balance": xxxxxxx,                (numeric) the total confirmed balance of the wallet in KLC

&#x20; "stake": xxxxxxx,                  (numeric) the total stake balance of the wallet in KLC

&#x20; "unconfirmed\_balance": xxx,        (numeric) the total unconfirmed balance of the wallet in KLC

&#x20; "immature\_balance": xxxxxx,        (numeric) the total immature balance of the wallet in KLC

&#x20; "txcount": xxxxxxx,                (numeric) the total number of transactions in the wallet

&#x20; "keypoololdest": xxxxxx,           (numeric) the timestamp (seconds since Unix epoch) of the oldest pre-generated key in the key pool

&#x20; "keypoolsize": xxxx,               (numeric) how many new keys are pre-generated (only counts external keys)

&#x20; "keypoolsize\_hd\_internal": xxxx,   (numeric) how many new keys are pre-generated for internal use (used for change outputs, only appears if the wallet is using this feature, otherwise external keys are used)

&#x20; "unlocked\_until": ttt,             (numeric) the timestamp in seconds since epoch (midnight Jan 1 1970 GMT) that the wallet is unlocked for transfers, or 0 if the wallet is locked

&#x20; "paytxfee": x.xxxx,                (numeric) the transaction fee configuration, set in KLC /kB

&#x20; "hdseedid": "\<hash160>"            (string, optional) the Hash160 of the HD seed (only present when HD is enabled)

&#x20; "hdmasterkeyid": "\<hash160>"       (string, optional) alias for hdseedid retained for backwards-compatibility. Will be removed in V0.18.

&#x20; "private\_keys\_enabled": true|false (boolean) false if privatekeys are disabled for this wallet (enforced watch-only wallet)

}

**Examples:**

&#x20; \> Kalycoin -cli getwalletinfo

&#x20;

&#x20; \> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getwalletinfo", "params": \[] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**importaddress**

Adds an address or script (in hex) that can be watched as if it were in your wallet but cannot be used to spend. Requires a new wallet backup.

**Arguments:**

1\. "address"            (string, required) The Bitcoin address (or hex-encoded script)

2\. "label"              (string, optional, default="") An optional label

3\. rescan               (boolean, optional, default=true) Rescan the wallet for transactions

4\. p2sh                 (boolean, optional, default=false) Add the P2SH version of the script as well

Note: This call can take over an hour to complete if rescan is true, during that time, other rpc calls may report that the imported address exists but related transactions are still missing, leading to temporarily incorrect/bogus balances and unspent outputs until rescan completes. If you have the full public key, you should call importpubkey instead of this.

Note: If you import a non-standard raw script in hex form, outputs sending to it will be treated as change, and not show up in many RPCs.

**Examples:**

Import an address with rescan

\> Kalycoin -cli importaddress "myaddress"

Import using a label without rescan

\> Kalycoin -cli importaddress "myaddress" "testing" false

As a JSON-RPC call

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "importaddress", "params": \["myaddress", "testing", false] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**importmulti**

Import addresses/scripts (with private or public keys, redeem script (P2SH)), rescanning all addresses in one-shot-only (rescan can be disabled via options). Requires a new wallet backup.

**Arguments:**

1\. requests                                                   (array, required) Data to be imported

&#x20; \[   &#x20;

&#x20;   {

&#x20;     "scriptPubKey": "\<script>" | { "address":"\<address>" }, (string / json, required) Type of scriptPubKey (string for script, json for address)

&#x20;     "timestamp": timestamp | "now"                        , (integer / string, required) Creation time of the key in seconds since epoch (Jan 1 1970 GMT),

&#x20;                                                             or the string "now" to substitute the current synced blockchain time. The timestamp of the oldest

&#x20;                                                             key will determine how far back blockchain rescans need to begin for missing wallet transactions.

&#x20;                                                             "now" can be specified to bypass scanning, for keys which are known to never have been used, and

&#x20;                                                             0 can be specified to scan the entire blockchain. Blocks up to 2 hours before the earliest key

&#x20;                                                             creation time of all keys being imported by the importmulti call will be scanned.

&#x20;     "redeemscript": "\<script>"                            , (string, optional) Allowed only if the scriptPubKey is a P2SH address or a P2SH scriptPubKey

&#x20;     "pubkeys": \["\<pubKey>", ... ]                         , (array, optional) Array of strings giving pubkeys that must occur in the output or redeemscript

&#x20;     "keys": \["\<key>", ... ]                               , (array, optional) Array of strings giving private keys whose corresponding public keys must occur in the output or redeemscript

&#x20;     "internal": \<true>                                    , (boolean, optional, default: false) Stating whether matching outputs should be treated as not incoming payments aka change

&#x20;     "watchonly": \<true>                                   , (boolean, optional, default: false) Stating whether matching outputs should be considered watched even when they're not spendable, only allowed if keys are empty

&#x20;     "label": \<label>                                      , (string, optional, default: '') Label to assign to the address (aka account name, for now), only allowed with internal=false

&#x20;   }

&#x20; ,...

&#x20; ]

2\. options                 (json, optional)

&#x20; {

&#x20;    "rescan": \<false>,         (boolean, optional, default: true) Stating if should rescan the blockchain after all imports

&#x20; }

&#x20;

Note: This call can take over an hour to complete if rescan is true, during that time, other rpc calls

may report that the imported keys, addresses or scripts exists but related transactions are still missing.

**Examples:**

\> Kalycoin -cli importmulti '\[{ "scriptPubKey": { "address": "\<my address>" }, "timestamp":1455191478 }, { "scriptPubKey": { "address": "\<my 2nd address>" }, "label": "example 2", "timestamp": 1455191480 }]'

&#x20;

\> Kalycoin -cli importmulti '\[{ "scriptPubKey": { "address": "\<my address>" }, "timestamp":1455191478 }]' '{ "rescan": false}'

&#x20;

Response is an array with the same size as the input that has the execution result :

\[{ "success": true } , { "success": false, "error": { "code": -1, "message": "Internal Server Error"} }, ... ]

**importprivkey**

Adds a private key (as returned by dumpprivkey) to your wallet. Requires a new wallet backup. Hint: use importmulti to import more than one private key.

**Arguments:**

1\. " Kalycoin privkey" (string, required) The private key (see dumpprivkey)

2\. "label"       (string, optional, default="") An optional label

3\. rescan        (boolean, optional, default=true) Rescan the wallet for transactions

Note: This call can take over an hour to complete if rescan is true, during that time, other rpc calls may report that the imported key exists but related transactions are still missing, leading to temporarily incorrect/bogus balances and unspent outputs until rescan completes.

**Examples:**

Dump a private key

\> Kalycoin -cli dumpprivkey "myaddress"

Import the private key with rescan

\> Kalycoin -cli importprivkey "mykey"

Import using a label and without rescan

\> Kalycoin -cli importprivkey "mykey" "testing" false

Import using default blank label and without rescan

\> Kalycoin -cli importprivkey "mykey" "" false

As a JSON-RPC call

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "importprivkey", "params": \["mykey", "testing", false] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**importprunedfunds**

Imports funds without rescan. Corresponding address or script must previously be included in wallet. Aimed towards pruned wallets. The end-user is responsible to import additional transactions that subsequently spend the imported outputs or rescan after the point in the blockchain the transaction is included.

**Arguments:**

1\. "rawtransaction" (string, required) A raw transaction in hex funding an already-existing address in wallet

2\. "txoutproof" (string, required) The hex output from gettxoutproof that contains the transaction

**listreceivedbyaddress**

List balances by receiving address.

**Arguments:**

1\. minconf (numeric, optional, default=1) The minimum number of confirmations before payments are included.

2\. include\_empty (bool, optional, default=false) Whether to include addresses that haven't received any payments.

3\. include\_watchonly (bool, optional, default=false) Whether to include watch-only addresses (see 'importaddress').

4\. address\_filter (string, optional) If present, only return information on this address.

**Result:**

&#x20;\[

&#x20; {

&#x20;   "involvesWatchonly" : true,        (bool) Only returned if imported addresses were involved in transaction

&#x20;   "address" : "receivingaddress",    (string) The receiving address

&#x20;   "account" : "accountname",         (string) DEPRECATED. Backwards compatible alias for label.

&#x20;   "amount" : x.xxx,                  (numeric) The total amount in KLC received by the address

&#x20;   "confirmations" : n,               (numeric) The number of confirmations of the most recent transaction included

&#x20;   "label" : "label",                 (string) The label of the receiving address. The default label is "".

&#x20;   "txids": \[

&#x20;      "txid",                         (string) The ids of transactions received with the address

&#x20;      ...

&#x20;   ]

&#x20; }

&#x20; ,...

]

**importpubkey**

Adds a public key (in hex) that can be watched as if it were in your wallet but cannot be used to spend. Requires a new wallet backup.

**Arguments:**

1\. "pubkey" (string, required) The hex-encoded public key

2\. "label"  (string, optional, default="") An optional label

3\. rescan   (boolean, optional, default=true) Rescan the wallet for transactions

&#x20;

Note: This call can take over an hour to complete if rescan is true, during that time, other rpc calls

may report that the imported pubkey exists but related transactions are still missing, leading to temporarily incorrect/bogus balances and unspent outputs until rescan completes.

**Examples:**

Import a public key with rescan

\> Kalycoin -cli importpubkey "mypubkey"

Import using a label without rescan

\> Kalycoin -cli importpubkey "mypubkey" "testing" false

As a JSON-RPC call

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "importpubkey", "params": \["mypubkey", "testing", false] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**importwallet**

Imports keys from a wallet dump file (see dumpwallet). Requires a new wallet backup to include imported keys.

**Arguments:**

1\. "filename" (string, required) The wallet file

**Examples:**

Dump the wallet

\> Kalycoin -cli dumpwallet "test"

Import the wallet

\> Kalycoin -cli importwallet "test"

Import using the json rpc call

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "importwallet", "params": \["test"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**keypoolrefill**

Fills the keypool.

**Arguments:**

1\. newsize (numeric, optional, default=100) The new keypool size

**Examples:**

\> Kalycoin -cli keypoolrefill

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "keypoolrefill", "params": \[] }' -H 'con

**listaddressgroupings**

Lists groups of addresses which have had their common ownership made public by common use as inputs or as the resulting change in past transactions

**Result:**

\[

&#x20; \[

&#x20;   \[

&#x20;     "address", (string) The Kalycoin address

&#x20;      amount,   (numeric) The amount in KLC

&#x20;     "label"    (string, optional) The label

&#x20;   ]

&#x20;   ,...

&#x20; ]

&#x20; ,...

]

**Examples:**

\> Kalycoin -cli listaddressgroupings

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "listaddressgroupings", "params": \[] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**listlabels**

Returns the list of all labels, or labels that are assigned to addresses with a specific purpose.

**Arguments:**

1\. "purpose" (string, optional) Address purpose to list labels for ('send','receive'). An empty string is the same as not providing this argument.

**Result:**

\[

&#x20; "label", (string) Label name

&#x20; ...

]

**Examples:**

List all labels

\> Kalycoin -cli listlabels

List labels that have receiving addresses

\> Kalycoin -cli listlabels receive

List labels that have sending addresses

\> Kalycoin -cli listlabels send

As json rpc call

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "listlabels", "params": \[receive] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**listlockunspent**

Returns list of temporarily unspendable outputs. See the lockunspent call to lock and unlock transactions for spending.

**Result:**

\[

&#x20; {

&#x20;   "txid" : "transactionid", (string) The transaction id locked

&#x20;   "vout" : n ,              (numeric) The vout value

&#x20; }

&#x20; ,...

]

**Examples:**

List the unspent transactions

\> Kalycoin -cli listunspent

Lock an unspent transaction

\> Kalycoin -cli lockunspent false "\[{\\"txid\\":\\"a08e6907dbbd3d809776dbfc5d82e371b764ed838b5655e72f463568df1aadf0\\",\\"vout\\":1}]"

List the locked transactions

\> Kalycoin -cli listlockunspent

Unlock the transaction again

\> Kalycoin -cli lockunspent true "\[{\\"txid\\":\\"a08e6907dbbd3d809776dbfc5d82e371b764ed838b5655e72f463568df1aadf0\\",\\"vout\\":1}]"

As a json rpc call

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "listlockunspent", "params": \[] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**Examples:**

\> Kalycoin -cli listreceivedbyaddress

&#x20;

\> Kalycoin -cli listreceivedbyaddress 6 true

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "listreceivedbyaddress", "params": \[6, true, true] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "listreceivedbyaddress", "params": \[6, true, true, "1M72Sfpbz1BPpXFHz9m3CdqATR44Jvaydd"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**listsinceblock**

Get all transactions in blocks since block \[blockhash], or all transactions if omitted. If "blockhash" is no longer a part of the main chain, transactions from the fork point onward are included. Additionally, if include\_removed is set, transactions affecting the wallet which were removed are returned in the "removed" array.

**Arguments:**

1\. "blockhash" (string, optional) The block hash to list transactions since

2\. target\_confirmations: (numeric, optional, default=1) Return the nth block hash from the main chain. e.g. 1 would mean the best block hash. Note: this is not used as a filter, but only affects \[lastblock] in the return value

3\. include\_watchonly: (bool, optional, default=false) Include transactions to watch-only addresses (see 'importaddress')

4\. include\_removed: (bool, optional, default=true) Show transactions that were removed due to a reorg in the "removed" array

(not guaranteed to work on pruned nodes)

**Result:**

{

&#x20; "transactions":

&#x20; \[

&#x20;   "account":"accountname",       (string) DEPRECATED. This field will be removed in V0.18. To see this deprecated field, start Kalycoin d with -deprecatedrpc=accounts. The account name associated with the transaction. Will be "" for the default account.

&#x20;   "address":"address",           (string) The Kalycoin address of the transaction. Not present for move transactions (category = move).

&#x20;   "category":"send|receive",     (string) The transaction category. 'send' has negative amounts, 'receive' has positive amounts.

&#x20;   "amount": x.xxx,               (numeric) The amount in KLC. This is negative for the 'send' category, and for the 'move' category for moves

&#x20;                                          outbound. It is positive for the 'receive' category, and for the 'move' category for inbound funds.

&#x20;   "vout" : n,                    (numeric) the vout value

&#x20;   "fee": x.xxx,                  (numeric) The amount of the fee in KLC. This is negative and only available for the 'send' category of transactions.

&#x20;   "confirmations": n,            (numeric) The number of confirmations for the transaction. Available for 'send' and 'receive' category of transactions.

&#x20;                                         When it's < 0, it means the transaction conflicted that many blocks ago.

&#x20;   "blockhash": "hashvalue",      (string) The block hash containing the transaction. Available for 'send' and 'receive' category of transactions.

&#x20;   "blockindex": n,               (numeric) The index of the transaction in the block that includes it. Available for 'send' and 'receive' category of transactions.

&#x20;   "blocktime": xxx,              (numeric) The block time in seconds since epoch (1 Jan 1970 GMT).

&#x20;   "txid": "transactionid",       (string) The transaction id. Available for 'send' and 'receive' category of transactions.

&#x20;   "time": xxx,                   (numeric) The transaction time in seconds since epoch (Jan 1 1970 GMT).

&#x20;   "timereceived": xxx,           (numeric) The time received in seconds since epoch (Jan 1 1970 GMT). Available for 'send' and 'receive' category of transactions.

&#x20;   "bip125-replaceable": "yes|no|unknown",&#x20;

&#x20;                                  (string) Whether this transaction could be replaced due to BIP125 (replace-by-fee);

&#x20;                                         may be unknown for unconfirmed transactions not in the mempool

&#x20;   "abandoned": xxx,              (bool) 'true' if the transaction has been abandoned (inputs are respendable). Only available for the 'send' category of transactions.

&#x20;   "comment": "...",              (string) If a comment is associated with the transaction.

&#x20;   "label" : "label"              (string) A comment for the address/transaction, if any

&#x20;   "to": "...",                   (string) If a comment to is associated with the transaction.

&#x20; ],

&#x20; "removed": \[

&#x20;   \<structure is the same as "transactions" above, only present if include\_removed=true>

&#x20;   Note: transactions that were re-added in the active chain will appear as-is in this array, and may thus have a positive confirmation count.

&#x20; ],

&#x20; "lastblock": "lastblockhash"     (string) The hash of the block (target\_confirmations-1) from the best block on the main chain. This is typically used to feed back into listsinceblock the next time you call it. So you would generally use a target\_confirmations of say 6, so you will be continually re-notified of transactions until they've reached 6 confirmations plus any new ones

}

**Examples:**

\> Kalycoin -cli listsinceblock

&#x20;

\> Kalycoin -cli listsinceblock "000000000000000bacf66f7497b7dc45ef753ee9a7d38571037cdb1a57f663ad" 6

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "listsinceblock", "params": \["000000000000000bacf66f7497b7dc45ef753ee9a7d38571037cdb1a57f663ad", 6] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**listtransactions**

If a label name is provided, this will return only incoming transactions paying to addresses with the specified label.

Returns up to 'count' most recent transactions skipping the first 'from' transactions.

Note that the "account" argument and "otheraccount" return value have been removed in V0.17. To use this RPC with an "account" argument, restart Kalycoin d with -deprecatedrpc=accounts

**Arguments:**

1\. "label"           (string, optional) If set, should be a valid label name to return only incoming transactions

&#x20;             with the specified label, or "\*" to disable filtering and return all transactions.

2\. count             (numeric, optional, default=10) The number of transactions to return

3\. skip              (numeric, optional, default=0) The number of transactions to skip

4\. include\_watchonly (bool, optional, default=false) Include transactions to watch-only addresses (see 'importaddress')

**Result:**

\[

&#x20; {

&#x20;   "address":"address",      (string) The Kalycoin address of the transaction.

&#x20;   "category":"send|receive", (string) The transaction category.

&#x20;   "amount": x.xxx,          (numeric) The amount in KLC. This is negative for the 'send' category, and is positive

&#x20;                                       for the 'receive' category,

&#x20;   "label": "label",         (string) A comment for the address/transaction, if any

&#x20;   "vout": n,                (numeric) the vout value

&#x20;   "fee": x.xxx,             (numeric) The amount of the fee in KLC. This is negative and only available for the

&#x20;                                        'send' category of transactions.

&#x20;   "confirmations": n,       (numeric) The number of confirmations for the transaction. Negative confirmations indicate the

&#x20;                                        transaction conflicts with the block chain

&#x20;   "trusted": xxx,           (bool) Whether we consider the outputs of this unconfirmed transaction safe to spend.

&#x20;   "blockhash": "hashvalue", (string) The block hash containing the transaction.

&#x20;   "blockindex": n,          (numeric) The index of the transaction in the block that includes it.

&#x20;   "blocktime": xxx,         (numeric) The block time in seconds since epoch (1 Jan 1970 GMT).

&#x20;   "txid": "transactionid",  (string) The transaction id.

&#x20;   "time": xxx,              (numeric) The transaction time in seconds since epoch (midnight Jan 1 1970 GMT).

&#x20;   "timereceived": xxx,      (numeric) The time received in seconds since epoch (midnight Jan 1 1970 GMT).

&#x20;   "comment": "...",         (string) If a comment is associated with the transaction.

&#x20;   "bip125-replaceable": "yes|no|unknown",  (string) Whether this transaction could be replaced due to BIP125 (replace-by-fee);

&#x20;                                                    may be unknown for unconfirmed transactions not in the mempool

&#x20;   "abandoned": xxx          (bool) 'true' if the transaction has been abandoned (inputs are respendable). Only available for the

&#x20;                                        'send' category of transactions.

&#x20; }

]

**Examples:**

List the most recent 10 transactions in the systems

\> Kalycoin -cli listtransactions

List transactions 100 to 120

\> Kalycoin -cli listtransactions "\*" 20 100

As a json rpc call

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "listtransactions", "params": \["\*", 20, 100] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**listreceivedbylabel**

List received transactions by label.

**Arguments:**

1\. minconf           (numeric, optional, default=1) The minimum number of confirmations before payments are included.

2\. include\_empty     (bool, optional, default=false) Whether to include labels that haven't received any payments.

3\. include\_watchonly (bool, optional, default=false) Whether to include watch-only addresses (see 'importaddress').

**Result:**

\[

&#x20; {

&#x20;   "involvesWatchonly" : true, (bool) Only returned if imported addresses were involved in transaction

&#x20;   "account" : "accountname",  (string) DEPRECATED. Backwards compatible alias for label.

&#x20;   "amount" : x.xxx,           (numeric) The total amount received by addresses with this label

&#x20;   "confirmations" : n,        (numeric) The number of confirmations of the most recent transaction included

&#x20;   "label" : "label"           (string) The label of the receiving address. The default label is "".

&#x20; }

&#x20; ,...

]

**Examples:**

\> Kalycoin -cli listreceivedbylabel

&#x20;

\> Kalycoin -cli listreceivedbylabel 6 true

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "listreceivedbylabel", "params": \[6, true, true] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**listunspent**

Returns array of unspent transaction outputs with between minconf and maxconf (inclusive) confirmations.

Optionally filter to only include txouts paid to specified addresses.

**Arguments:**

1\. minconf               (numeric, optional, default=1) The minimum confirmations to filter

2\. maxconf               (numeric, optional, default=9999999) The maximum confirmations to filter

3\. "addresses"           (string) A json array of Kalycoin addresses to filter

&#x20;   \[

&#x20;     "address"          (string) Kalycoin address

&#x20;     ,...

&#x20;   ]

4\. include\_unsafe        (bool, optional, default=true) Include outputs that are not safe to spend See description of "safe" attribute below.

5\. query\_options         (json, optional) JSON with query options

&#x20;   {

&#x20;     "minimumAmount"    (numeric or string, default=0) Minimum value of each UTXO in KLC

&#x20;     "maximumAmount"    (numeric or string, default=unlimited) Maximum value of each UTXO in KLC

&#x20;     "maximumCount"     (numeric or string, default=unlimited) Maximum number of UTXOs

&#x20;     "minimumSumAmount" (numeric or string, default=unlimited) Minimum sum value of all UTXOs in KLC

&#x20;   }

**Result：**

\[              &#x20;

&#x20; {

&#x20;   "txid" : "txid",          (string) the transaction id

&#x20;   "vout" : n,               (numeric) the vout value

&#x20;   "address" : "address",    (string) the Kalycoin address

&#x20;   "label" : "label",        (string) The associated label, or "" for the default label

&#x20;   "account" : "account",    (string) DEPRECATED. This field will be removed in V0.18. To see this deprecated field, start Kalycoin d with -deprecatedrpc=accounts. The associated account, or "" for the default account

&#x20;   "scriptPubKey" : "key",   (string) the script key

&#x20;   "amount" : x.xxx,         (numeric) the transaction output amount in KLC

&#x20;   "confirmations" : n,      (numeric) The number of confirmations

&#x20;   "redeemScript" : n        (string) The redeemScript if scriptPubKey is P2SH

&#x20;   "spendable" : xxx,        (bool) Whether we have the private keys to spend this output

&#x20;   "solvable" : xxx,         (bool) Whether we know how to spend this output, ignoring the lack of keys

&#x20;   "safe" : xxx              (bool) Whether this output is considered safe to spend. Unconfirmed transactions

&#x20;                             from outside keys and unconfirmed replacement transactions are considered unsafe

&#x20;                             and are not eligible for spending by fundrawtransaction and sendtoaddress.

&#x20; }

&#x20; ,...

]

**Examples：**

\> Kalycoin -cli listunspent

&#x20;

\> Kalycoin -cli listunspent 6 9999999 "\[\\"QjWnDZxwLhrJDcp4Hisse8RfBo2jRDZY5Z\\",\\"Q6sSauSf5pF2UkUwvKGq4qjNRzBZYqgEL5\\"]"

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "listunspent", "params": \[6, 9999999 "\[\\"QjWnDZxwLhrJDcp4Hisse8RfBo2jRDZY5Z\\",\\"Q6sSauSf5pF2UkUwvKGq4qjNRzBZYqgEL5\\"]"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

&#x20;

\> Kalycoin -cli listunspent 6 9999999 '\[]' true '{ "minimumAmount": 0.005 }'

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "listunspent", "params": \[6, 9999999, \[] , true, { "minimumAmount": 0.005 } ] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**listwallets**

Returns a list of currently loaded wallets. For full information on the wallet, use "getwalletinfo"

**Result:**

\[                       &#x20;

&#x20; "walletname"            (string) the wallet name

&#x20;  ...

]

**Examples:**

\> Kalycoin -cli listwallets

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "listwallets", "params": \[] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**loadwallet**

loadwallet "filename"

Loads a wallet from a wallet file or directory. Note that all wallet command-line options used when starting Kalycoin d will be applied to the new wallet (eg -zapwallettxes, upgradewallet, rescan, etc).

**Arguments:**

1\. "filename"    (string, required) The wallet directory or .dat file.

**Result:**

{

&#x20; "name" :    \<wallet\_name>,        (string) The wallet name if loaded successfully.

&#x20; "warning" : \<warning>,            (string) Warning message if wallet was not loaded cleanly.

}

**Examples:**

\> Kalycoin -cli loadwallet "test.dat"

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "loadwallet", "params": \["test.dat"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**lockunspent**

Updates list of temporarily unspendable outputs.

Temporarily lock (unlock=false) or unlock (unlock=true) specified transaction outputs.

If no transaction outputs are specified when unlocking then all current locked transaction outputs are unlocked.

A locked transaction output will not be chosen by automatic coin selection, when spending Kalycoins.

Locks are stored in memory only. Nodes start with zero locked outputs, and the locked output list is always cleared (by virtue of process exit) when a node stops or fails. Also see the listunspent call.

**Arguments:**

1\. unlock            (boolean, required) Whether to unlock (true) or lock (false) the specified transactions

2\. "transactions"  (string, optional) A json array of objects. Each object the txid (string) vout (numeric)

&#x20;    \[           (json array of json objects)

&#x20;      {

&#x20;        "txid":"id",    (string) The transaction id

&#x20;        "vout": n         (numeric) The output number

&#x20;      }

&#x20;      ,...

&#x20;    ]

**Result:**

true|false (boolean) Whether the command was successful or not

**Examples:**

List the unspent transactions

\> Kalycoin -cli listunspent

Lock an unspent transaction

\> Kalycoin -cli lockunspent false "\[{\\"txid\\":\\"a08e6907dbbd3d809776dbfc5d82e371b764ed838b5655e72f463568df1aadf0\\",\\"vout\\":1}]"

List the locked transactions

\> Kalycoin -cli listlockunspent

Unlock the transaction again

\> Kalycoin -cli lockunspent true "\[{\\"txid\\":\\"a08e6907dbbd3d809776dbfc5d82e371b764ed838b5655e72f463568df1aadf0\\",\\"vout\\":1}]"

As a json rpc call

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "lockunspent", "params": \[false, "\[{\\"txid\\":\\"a08e6907dbbd3d809776dbfc5d82e371b764ed838b5655e72f463568df1aadf0\\",\\"vout\\":1}]"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**removeprunedfunds**

Deletes the specified transaction from the wallet. Meant for use with pruned wallets and as a companion to importprunedfunds. This will affect wallet balances.

**Arguments:**

1\. "txid" (string, required) The hex-encoded id of the transaction you are deleting

**Examples:**

\> Kalycoin -cli removeprunedfunds "a8d0c0184dde994a09ec054286f1ce581bebf46446a512166eae7628734ea0a5"

As a JSON-RPC call

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "removeprunedfunds", "params": \["a8d0c0184dde994a09ec054286f1ce581bebf46446a512166eae7628734ea0a5"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**rescanblockchain**

Rescan the local blockchain for wallet related transactions.

**Arguments:**

1\. "start\_height" (numeric, optional) block height where the rescan should start

2\. "stop\_height" (numeric, optional) the last block height that should be scanned

**Result:**

{

&#x20; "start\_height" (numeric) The block height where the rescan has started. If omitted, rescan started from the genesis block.

&#x20; "stop\_height" (numeric) The height of the last rescanned block. If omitted, rescan stopped at the chain tip.

}

**Examples:**

\> Kalycoin -cli rescanblockchain 100000 120000

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "rescanblockchain", "params": \[100000, 120000] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**reservebalance**

Set reserve amount not participating in network protection. If no parameters provided current setting is printed.

**sendmany**

Send multiple times. Amounts are double-precision floating point numbers. Note that the "fromaccount" argument has been removed in V0.17. To use this RPC with a "fromaccount" argument, restart Kalycoin d with -deprecatedrpc=accounts

Requires wallet passphrase to be set with walletpassphrase call.

**Arguments:**

1\. "dummy"               (string, required) Must be set to "" for backwards compatibility.

2\. "amounts"             (string, required) A json object with addresses and amounts

&#x20;   {

&#x20;     "address":amount   (numeric or string) The Kalycoin address is the key, the numeric amount (can be string) in KLC is the value

&#x20;     ,...

&#x20;   }

3\. minconf               (numeric, optional, default=1) Only use the balance confirmed at least this many times.

4\. "comment"             (string, optional) A comment

5\. subtractfeefrom       (array, optional) A json array with addresses.

&#x20;                          The fee will be equally deducted from the amount of each selected address.

&#x20;                          Those recipients will receive less Kalycoin s than you enter in their corresponding amount field.

&#x20;                          If no addresses are specified here, the sender pays the fee.

&#x20;   \[

&#x20;     "address"          (string) Subtract fee from this address

&#x20;     ,...

&#x20;   ]

6\. replaceable           (boolean, optional) Allow this transaction to be replaced by a transaction with higher fees via BIP 125

7\. conf\_target           (numeric, optional) Confirmation target (in blocks)

8\. "estimate\_mode"       (string, optional, default=UNSET) The fee estimate mode, must be one of:

&#x20;      "UNSET"

&#x20;      "ECONOMICAL"

&#x20;      "CONSERVATIVE"

**Result:**

"txid" (string) The transaction id for the send. Only 1 transaction is created regardless of the number of addresses.

**Examples:**

Send two amounts to two different addresses:

\> Kalycoin -cli sendmany "" "{\\"QD1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX\\":0.01,\\"Q353tsE8YMTA4EuV7dgUXGjNFf9KpVvKHz\\":0.02}"

Send two amounts to two different addresses setting the confirmation and comment:

\> Kalycoin -cli sendmany "" "{\\"QD1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX\\":0.01,\\"Q353tsE8YMTA4EuV7dgUXGjNFf9KpVvKHz\\":0.02}" 6 "testing"

Send two amounts to two different addresses, subtract fee from amount:

\> Kalycoin -cli sendmany "" "{\\"QD1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX\\":0.01,\\"Q353tsE8YMTA4EuV7dgUXGjNFf9KpVvKHz\\":0.02}" 1 "" "\[\\"QD1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX\\",\\"Q353tsE8YMTA4EuV7dgUXGjNFf9KpVvKHz\\"]"

As a json rpc call

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "sendmany", "params": \["", {"QD1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX":0.01,"Q353tsE8YMTA4EuV7dgUXGjNFf9KpVvKHz":0.02}, 6, "testing"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**sendmanywithdupes**

Send multiple times. Amounts are double-precision floating point numbers. Supports duplicate addresses Requires wallet passphrase to be set with walletpassphrase call.

**Arguments:**

1\. "fromaccount"         (string, required) DEPRECATED. The account to send the funds from. Should be "" for the default account

2\. "amounts"             (string, required) A json object with addresses and amounts

&#x20;   {

&#x20;     "address":amount   (numeric or string) The Kalycoin address is the key, the numeric amount (can be string) in KLC is the value

&#x20;     ,...

&#x20;   }

3\. minconf               (numeric, optional, default=1) Only use the balance confirmed at least this many times.

4\. "comment"             (string, optional) A comment

5\. subtractfeefrom       (array, optional) A json array with addresses.

&#x20;                          The fee will be equally deducted from the amount of each selected address.

&#x20;                          Those recipients will receive less Kalycoin s than you enter in their corresponding amount field.

&#x20;                          If no addresses are specified here, the sender pays the fee.

&#x20;   \[

&#x20;     "address"          (string) Subtract fee from this address

&#x20;     ,...

&#x20;   ]

**Result:**

"txid" (string) The transaction id for the send. Only 1 transaction is created regardless of the number of addresses.

**Examples:**

Send two amounts to two different addresses:

\> Kalycoin -cli sendmanywithdupes "" "{\\"QD1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX\\":0.01,\\"Q353tsE8YMTA4EuV7dgUXGjNFf9KpVvKHz\\":0.02}"

Send two amounts to two different addresses setting the confirmation and comment:

\> Kalycoin -cli sendmanywithdupes "" "{\\"QD1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX\\":0.01,\\"Q353tsE8YMTA4EuV7dgUXGjNFf9KpVvKHz\\":0.02}" 6 "testing"

Send two amounts to two different addresses, subtract fee from amount:

\> Kalycoin -cli sendmanywithdupes "" "{\\"QD1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX\\":0.01,\\"Q353tsE8YMTA4EuV7dgUXGjNFf9KpVvKHz\\":0.02}" 1 "" "\[\\"QD1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX\\",\\"Q353tsE8YMTA4EuV7dgUXGjNFf9KpVvKHz\\"]"

As a json rpc call

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "sendmanywithdupes", "params": \["", "{\\"QD1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX\\":0.01,\\"Q353tsE8YMTA4EuV7dgUXGjNFf9KpVvKHz\\":0.02}", 6, "testing"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**sendtoaddress**

Send an amount to a given address.

Requires wallet passphrase to be set with walletpassphrase call.

**Arguments:**

&#x20; 1\. "address"            (string, required) The Kalycoin address to send to.

2\. "amount"               (numeric or string, required) The amount in KLC to send. eg 0.1

3\. "comment"              (string, optional) A comment used to store what the transaction is for.

&#x20;                            This is not part of the transaction, just kept in your wallet.

4\. "comment\_to"           (string, optional) A comment to store the name of the person or organization

&#x20;                            to which you're sending the transaction. This is not part of the

&#x20;                            transaction, just kept in your wallet.

5\. subtractfeefromamount  (boolean, optional, default=false) The fee will be deducted from the amount being sent.

&#x20;                            The recipient will receive less Kalycoin s than you enter in the amount field.

6\. replaceable            (boolean, optional) Allow this transaction to be replaced by a transaction with higher fees via BIP 125

7\. conf\_target            (numeric, optional) Confirmation target (in blocks)

8\. "estimate\_mode"        (string, optional, default=UNSET) The fee estimate mode, must be one of:

&#x20;      "UNSET"

&#x20;      "ECONOMICAL"

&#x20;      "CONSERVATIVE"

9\. "senderaddress"        (string, optional) The quantum address that will be used to send money from.

10."changeToSender"       (bool, optional, default=false) Return the change to the sender.

**Result:**

"txid" (string) The transaction id.

**Examples:**

\> Kalycoin -cli sendtoaddress "QM72Sfpbz1BPpXFHz9m3CdqATR44Jvaydd" 0.1

&#x20;

\> Kalycoin -cli sendtoaddress "QM72Sfpbz1BPpXFHz9m3CdqATR44Jvaydd" 0.1 "donation" "seans outpost"

&#x20;

\> Kalycoin -cli sendtoaddress "QM72Sfpbz1BPpXFHz9m3CdqATR44Jvaydd" 0.1 "" "" true

&#x20;

\> Kalycoin -cli sendtoaddress "QM72Sfpbz1BPpXFHz9m3CdqATR44Jvaydd", 0.1, "donation", "seans outpost", false, null, null, "", "QX1GkJdye9WoUnrE2v6ZQhQ72EUVDtGXQX", true

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "sendtoaddress", "params": \["QM72Sfpbz1BPpXFHz9m3CdqATR44Jvaydd", 0.1, "donation", "seans outpost"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "sendtoaddress", "params": \["QM72Sfpbz1BPpXFHz9m3CdqATR44Jvaydd", 0.1, "donation", "seans outpost", false, null, null, "", "QX1GkJdye9WoUnrE2v6ZQhQ72EUVDtGXQX", true] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**sendtocontract**

Send funds and data to a contract.

Requires wallet passphrase to be set with walletpassphrase call.

**Arguments:**

1\. "contractaddress" (string, required) The contract address that will receive the funds and data.

2\. "datahex"         (string, required) data to send.

3\. "amount"          (numeric or string, optional) The amount in KLC to send. eg 0.1, default: 0

4\. gasLimit          (numeric or string, optional) gasLimit, default: 250000, max: 40000000

5\. gasPrice          (numeric or string, optional) gasPrice KLC price per gas unit, default: 0.0000004, min:0.0000004

6\. "senderaddress"   (string, optional) The quantum address that will be used as sender.

7\. "broadcast"       (bool, optional, default=true) Whether to broadcast the transaction or not.

8\. "changeToSender"  (bool, optional, default=true) Return the change to the sender.

**Result:**

\[

&#x20; {

&#x20;   "txid" :    (string) The transaction id.

&#x20;   "sender" :  (string) KLC address of the sender.

&#x20;   "hash160" : (string) ripemd-160 hash of the sender.

&#x20; }

]

**Examples:**

\> Kalycoin -cli sendtocontract "c6ca2697719d00446d4ea51f6fac8fd1e9310214" "54f6127f"

&#x20;

\> Kalycoin -cli sendtocontract "c6ca2697719d00446d4ea51f6fac8fd1e9310214" "54f6127f" 12.0015 6000000 0.0000004 "QM72Sfpbz1BPpXFHz9m3CdqATR44Jvaydd"

**sethdseed**

Set or generate a new HD wallet seed. Non-HD wallets will not be upgraded to being a HD wallet. Wallets that are already HD will have a new HD seed set so that new keys added to the keypool will be derived from this new seed.

Note that you will need to MAKE A NEW BACKUP of your wallet after setting the HD wallet seed.

Requires wallet passphrase to be set with walletpassphrase call.

**Arguments:**

1\. "newkeypool" (boolean, optional, default=true) Whether to flush old unused addresses, including change addresses, from the keypool and regenerate it.

If true, the next address from getnewaddress and change address from getrawchangeaddress will be from this new seed.

If false, addresses (including change addresses if the wallet already had HD Chain Split enabled) from the existing

keypool will be used until it has been depleted.

2\. "seed" (string, optional) The WIF private key to use as the new HD seed; if not provided a random seed will be used.

The seed value can be retrieved using the command. It is the private key marked hdseed=1

**Examples:**

\> Kalycoin -cli sethdseed

&#x20;

\> Kalycoin -cli sethdseed false

&#x20;

\> Kalycoin -cli sethdseed true "wifkey"

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "sethdseed", "params": \[true, "wifkey"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**settxfee**

settxfee amount

Set the transaction fee per kB for this wallet. Overrides the global -paytxfee command line parameter.

**Arguments:**

1\. amount (numeric or string, required) The transaction fee in KLC /kB

**Results:**

true|false (boolean) Returns true if successful

**Examples:**

\> Kalycoin -cli settxfee 0.00001

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "settxfee", "params": \[0.00001] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**signmessage**

Sign a message with the private key of an address

**Arguments:**

1\. "address" (string, required) The Kalycoin address to use for the private key.

&#x20;

2\. "message" (string, required) The message to create a signature of.

**Result:**

"signature" (string) The signature of the message encoded in base 64

**Examples:**

Unlock the wallet for 30 seconds

\> Kalycoin -cli walletpassphrase "mypassphrase" 30

Create the signature

\> Kalycoin -cli signmessage "QD1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX" "my message"

Verify the signature

\> Kalycoin -cli verifymessage "QD1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX" "signature" "my message"

As json rpc

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "signmessage", "params": \["QD1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX", "my message"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**signrawtransactionwithwallet**

Sign inputs for raw transaction (serialized, hex-encoded). The second optional argument (may be null) is an array of previous transaction outputs that this transaction depends on but may not yet be in the block chain.

**Arguments:**

1\. "hexstring"                      (string, required) The transaction hex string

2\. "prevtxs"                        (string, optional) An json array of previous dependent transaction outputs

&#x20;    \[                              (json array of json objects, or 'null' if none provided)

&#x20;      {

&#x20;        "txid":"id",               (string, required) The transaction id

&#x20;        "vout":n,                  (numeric, required) The output number

&#x20;        "scriptPubKey": "hex",     (string, required) script key

&#x20;        "redeemScript": "hex",     (string, required for P2SH or P2WSH) redeem script

&#x20;        "amount": value            (numeric, required) The amount spent

&#x20;      }

&#x20;      ,...

&#x20;   ]

3\. "sighashtype"                    (string, optional, default=ALL) The signature hash type. Must be one of

&#x20;      "ALL"

&#x20;      "NONE"

&#x20;      "SINGLE"

&#x20;      "ALL|ANYONECANPAY"

&#x20;      "NONE|ANYONECANPAY"

&#x20;      "SINGLE|ANYONECANPAY"

**Result:**

{

&#x20; "hex" : "value",                  (string) The hex-encoded raw transaction with signature(s)

&#x20; "complete" : true|false,          (boolean) If the transaction has a complete set of signatures

&#x20; "errors" : \[                      (json array of objects) Script verification errors (if there are any)

&#x20;   {

&#x20;     "txid" : "hash",              (string) The hash of the referenced, previous transaction

&#x20;     "vout" : n,                   (numeric) The index of the output to spent and used as input

&#x20;     "scriptSig" : "hex",          (string) The hex-encoded signature script

&#x20;     "sequence" : n,               (numeric) Script sequence number

&#x20;     "error" : "text"              (string) Verification or signing error related to the input

&#x20;   }

&#x20;   ,...

&#x20; ]

}

**Examples:**

\> Kalycoin -cli signrawtransactionwithwallet "myhex"

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "signrawtransactionwithwallet", "params": \["myhex"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**unloadwallet**

Unloads the wallet referenced by the request endpoint otherwise unloads the wallet specified in the argument. Specifying the wallet name on a wallet endpoint is invalid.

**Arguments:**

1\. "wallet\_name" (string, optional) The name of the wallet to unload.

**Examples:**

\> Kalycoin -cli unloadwallet wallet\_name

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "unloadwallet", "params": \[wallet\_name] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**walletcreatefundedpsbt**

Creates and funds a transaction in the Partially Signed Transaction format. Inputs will be added if supplied inputs are not enough Implements the Creator and Updater roles.

**Arguments:**

1\. "inputs"                (array, required) A json array of json objects

&#x20;    \[

&#x20;      {

&#x20;        "txid":"id",      (string, required) The transaction id

&#x20;        "vout":n,         (numeric, required) The output number

&#x20;        "sequence":n      (numeric, optional) The sequence number

&#x20;      }

&#x20;      ,...

&#x20;    ]

2\. "outputs"               (array, required) a json array with outputs (key-value pairs), where none of the keys are duplicated.

That is, each address can only appear once and there can only be one 'data' object.

&#x20;  \[

&#x20;   {

&#x20;     "address": x.xxx,    (obj, optional) A key-value pair. The key (string) is the Kalycoin address, the value (float or string) is the amount in KLC

&#x20;   },

&#x20;   {

&#x20;     "data": "hex"        (obj, optional) A key-value pair. The key must be "data", the value is hex encoded data

&#x20;   }

&#x20;   ,...                     More key-value pairs of the above form. For compatibility reasons, a dictionary, which holds the key-value pairs directly, is also

&#x20;                            accepted as second parameter.

&#x20;  ]

3\. locktime                  (numeric, optional, default=0) Raw locktime. Non-0 value also locktime-activates inputs

&#x20;                            Allows this transaction to be replaced by a transaction with higher fees. If provided, it is an error if explicit sequence numbers are incompatible.

4\. options                 (object, optional)

&#x20;  {

&#x20;    "changeAddress"          (string, optional, default pool address) The Kalycoin address to receive the change

&#x20;    "changePosition"         (numeric, optional, default random) The index of the change output

&#x20;    "change\_type"            (string, optional) The output type to use. Only valid if changeAddress is not specified. Options are "legacy", "p2sh-segwit", and "bech32". Default is set by -changetype.

&#x20;    "includeWatching"        (boolean, optional, default false) Also select inputs which are watch only

&#x20;    "lockUnspents"           (boolean, optional, default false) Lock selected unspent outputs

&#x20;    "feeRate"                (numeric, optional, default not set: makes wallet determine the fee) Set a specific fee rate in KLC /kB

&#x20;    "subtractFeeFromOutputs" (array, optional) A json array of integers.

&#x20;                             The fee will be equally deducted from the amount of each specified output.

&#x20;                             The outputs are specified by their zero-based index, before any change output is added.

&#x20;                             Those recipients will receive less Kalycoin s than you enter in their corresponding amount field.

&#x20;                             If no outputs are specified here, the sender pays the fee.

&#x20;                                 \[vout\_index,...]

&#x20;    "replaceable"            (boolean, optional) Marks this transaction as BIP125 replaceable.

&#x20;                             Allows this transaction to be replaced by a transaction with higher fees

&#x20;    "conf\_target"            (numeric, optional) Confirmation target (in blocks)

&#x20;    "estimate\_mode"          (string, optional, default=UNSET) The fee estimate mode, must be one of:

&#x20;        "UNSET"

&#x20;        "ECONOMICAL"

&#x20;        "CONSERVATIVE"

&#x20;  }

5\. bip32derivs                    (boolean, optional, default=false) If true, includes the BIP 32 derivation paths for public keys if we know them

**Result:**

{

&#x20; "psbt": "value",         (string)  The resulting raw transaction (base64-encoded string)

&#x20; "fee":        n,         (numeric) Fee in KLC the resulting transaction pays

&#x20; "changepos":  n,         (numeric) The position of the added change output, or -1

}

**Examples:**

Create a transaction with no inputs

\> Kalycoin -cli walletcreatefundedpsbt "\[{\\"txid\\":\\"myid\\",\\"vout\\":0}]" "\[{\\"data\\":\\"00010203\\"}]"

**walletlock**

Removes the wallet encryption key from memory, locking the wallet.

After calling this method, you will need to call walletpassphrase again

before being able to call any methods which require the wallet to be unlocked.

**Examples:**

Set the passphrase for 2 minutes to perform a transaction

\> Kalycoin -cli walletpassphrase "my pass phrase" 120

Perform a send (requires passphrase set)

\> Kalycoin -cli sendtoaddress "QM72Sfpbz1BPpXFHz9m3CdqATR44Jvaydd" 1.0

Clear the passphrase since we are done before 2 minutes is up

\> Kalycoin -cli walletlock

As json rpc call

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "walletlock", "params": \[] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**walletpassphrase**

Stores the wallet decryption key in memory for 'timeout' seconds.

This is needed prior to performing transactions related to private keys such as sending KLC and staking

**Arguments:**

1\. "passphrase" (string, required) The wallet passphrase

&#x20;

2\. timeout      (numeric, required) The time to keep the decryption key in seconds; capped at 100000000 (\~3 years).

&#x20;

3\. staking only (bool, optional, omitted=false, enabled=true) Unlock wallet for staking only.

&#x20;

Note:

&#x20;

Issuing the walletpassphrase command while the wallet is already unlocked will set a new unlock

&#x20;

time that overrides the old one.

**Examples:**

Unlock the wallet for 60 seconds

\> Kalycoin -cli walletpassphrase "my pass phrase" 60

Lock the wallet again (before 60 seconds)

\> Kalycoin -cli walletlock

Unlock the wallet for staking only, for a long time

\> Kalycoin -cli walletpassphrase "my pass phrase" 99999999 true

As json rpc call

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "walletpassphrase", "params": \["my pass phrase", 60] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**walletpassphrasechange**

Changes the wallet passphrase from 'oldpassphrase' to 'newpassphrase'.

**Arguments:**

1\. "oldpassphrase"      (string) The current passphrase

2\. "newpassphrase"      (string) The new passphrase

**Examples:**

\> Kalycoin -cli walletpassphrasechange "old one" "new one"

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "walletpassphrasechange", "params": \["old one", "new one"] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

**walletprocesspsbt**

Update a PSBT with input information from our wallet and then sign inputs

that we can sign for.

**Arguments:**

1\. "psbt"                         (string, required) The transaction base64 string

2\. sign                           (boolean, optional, default=true) Also sign the transaction when updating

3\. "sighashtype"                  (string, optional, default=ALL) The signature hash type to sign with if not specified by the PSBT. Must be one of

&#x20;      "ALL"

&#x20;      "NONE"

&#x20;      "SINGLE"

&#x20;      "ALL|ANYONECANPAY"

&#x20;      "NONE|ANYONECANPAY"

&#x20;      "SINGLE|ANYONECANPAY"

4\. bip32derivs                    (boolean, optional, default=false) If true, includes the BIP 32 derivation paths for public keys if we know them

**Result:**

{

&#x20; "psbt" : "value",          (string) The base64-encoded partially signed transaction

&#x20; "complete" : true|false,   (boolean) If the transaction has a complete set of signatures

&#x20; ]

}

**Examples:**

\> Kalycoin -cli walletprocesspsbt "psbt"

**zmq**

**getzmqnotifications**

Returns information about the active ZeroMQ notifications.

**Result:**

\[

&#x20; {

&#x20;   "type": "pubhashtx", (string) Type of notification

&#x20;   "address": "..."     (string) Address of the publisher

&#x20; },

&#x20; ...

]

**Examples:**

\> Kalycoin -cli getzmqnotifications

&#x20;

\> curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getzmqnotifications", "params": \[] }' -H 'content-type: text/plain;' http://127.0.0.1:3889/

[\
](https://docs.qtum.site/en/lightning/)
