# KRC20 Integration

### **KRC 20 Integration Technical Guide**

This document explains the basics of interacting with an KRC 20 contract with the Kalycoind CLI command tool.

The full example in PHP: [ KRC 20.php](https://github.com/kalycoinproject/krc20-wrapper/blob/master/krc20.php) .

### **Intro**

We recommend that an exchange use one main address to store tokens for all users. Below MAIN\_ KRC \_ADDRESS is the main address.

The address of the KRC 20 token contract is TOKEN\_CONTRACT\_ADDRESS.

·         gas limit is DEFAULT\_GAS\_LIMIT, recommended value is 250000

·         gas price is DEFAULT\_GAS\_PRICE，recommended value is 0.00000040

TOKEN\_DECIMALS is the decimals of the token, which varies per token. Here we set it 8.

We'll use the following utility functions:

·         [addressToHash160](https://github.com/kalycoinproject/krc20-wrapper/blob/master/krc20.php) - Convert base58 address to hash160 address.

·         [to32bytesArg](https://github.com/kalycoinproject/krc20-wrapper/blob/master/krc20.php) left-pad hex data to 32 bytes with 0.

·         [addDecimals](https://github.com/kalycoinproject/krc20-wrapper/blob/master/krc20.php) multiply the nominal token amount by the number of decimal places.

### **Running KLCD**

You should remember to enable the indexing service when starting Kalycoind, using the flags -logevents -txindex.

### **Interacting With KRC 20**

In the CLI examples below, please substitute {} with actual addresses and values.

### **Getting Token Balance**

·         $userAddress is the deposit address

Kalycoin-cli callcontract \\

&#x20;   {TOKEN\_CONTRACT\_ADDRESS} \\

&#x20;   70a08231{to32bytesArg(addressToHash160($userAddress))}

In the JSON output look for executionResult.output. This is the token balance.

### **Withdraw**

·         $userAddress is the withdraw address

·         $amount the withdraw amount in unit token

Kalycoin-cli sendtocontract \\

&#x20;   {TOKEN\_CONTRACT\_ADDRESS} \\

&#x20;   a9059cbb{to32bytesArg(addressToHash160($userAddress))}{to32bytesArg(addDecimals($amount)) \\

&#x20;   0 \\

&#x20;   {DEFAULT\_GAS\_LIMIT} \\

&#x20;   {DEFAULT\_GAS\_PRICE} \\

&#x20;   {MAIN\_ KRC \_ADDRESS}

The command returns the txid of this transaction. You may use it to find information about this transaction (e.g. number of confirmations).

### **Generate a deposit address**

For an exchange, a user may use the same address for both Kalycoin and other KRC 20 tokens.

Use this command to generate a deposit address:

Kalycoin-cli getnewaddress

### **Deposit and Witdraw Logs**

·         $startingBlock is where you want to start looking (inclursive)

o    You can start looking from 0, but for better efficiency, you should remember where to start looking.

Kalycoin-cli searchlogs \\

&#x20;   STARTING\_BLOCK \\

&#x20;   999999999 \\

&#x20;   '{ "addresses": \["TOKEN\_CONTRACT\_ADDRESS"]}' \\

&#x20;   '{"topics": \["ddf252ad1be2c89b69c2b068fc378daa952ba7f163c4a11628f55a4df523b3ef"]}'

The event type filtered is the Transfer event:

event Transfer(address indexed \_from, address indexed \_to, uint256 \_value)

Look through the logs to filter by to or from addresses.

### **Checking Confirmations**

Given a transaction id $txid:

Kalycoin-cli gettransaction $txid

Use the property confirmations from output.
