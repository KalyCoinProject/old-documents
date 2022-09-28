# How to add options

### **How to add options for Kalycoin node（or add config file）**

User can specify extra options (or set configurations) for Kalycoin node, in order to enable/disable some specific features, other than default settings.

This tutorial describes how to specify options (or configurations) to Kalycoin node.

### **For Kalycoin PC wallet（Kalycoin Core qt wallet）**

(_**This works for both PC wallet and command-line Kalycoin d wallet**_)

Kalycoin PC wallet (i.e. Kalycoin core qt wallet) is the most widely used Kalycoin wallet by common users. (Not yet installed a wallet? Please visit [https://github.com/qtumproject/qtum/releases/](https://github.com/qtumproject/qtum/releases/) to download latest pc wallet）

User can edit Kalycoin config file to specify some options.

Instructions:

### **1. Create Kalycoin.conf file**

Create a file named Kalycoin.conf under your datadir, the default datadir paths for different OS are different:

·         Linux: \~/.kalycoin

·         OSX: \~/Library/Application Support/ Kalycoin

·         Windows: %APPDATA%\ Kalycoin (Please paste this path to your windows explorer, the path will be resolved automatically)

_**Please be careful and don‘t remove or change any content under this directory except you are aware of them.**_

（PS: the datadir might be manually set as well, so please create your Kalycoin.conf under the datadir you spcified, if you did)

Still don't know how to create a file? You can also open this Kalycoin.conf on the wallet UI directly System Preference->OPEN CONFIGURATION FILE:

This will create and open the Kalycoin.conf directly for user.

### **2. Specify the options**

User can then specify any option in the file Kalycoin.conf just created.

For example, to specify some rpc related settings, user might add following lines to Kalycoin.conf:

rpcuser=test

rpcpassword=test1234

server=1

This will set rpcuser to test, rpcpassword to test1234, and enable the server feature.

### **3. Restart wallet**

It is required to RESTART the wallet after editing the Kalycoin.conf file, before the options are really effective.

### **Other options**

To learn more about the complete list of all valid Kalycoin options, please check the pc wallet menu for more details:

Help->Command-line Options:

![](<.gitbook/assets/image (54).png>)

<figure><img src=".gitbook/assets/imagen (45).png" alt=""><figcaption></figcaption></figure>

### **For the command-line wallet Kalycoin d**

If your have no idea about command line, please ignore this section.

For those who are familiar with command line, you can also specify options by adding options when running Kalycoin d.

For example：

./kalycoin d -rpcuser=test -rpcpassword=test1234 -server=1

These options -rpcuser=test -rpcpassword=test1234 -server=1 realize the same configuration setting as the "Specify the options" section described.

Note that if you specify the options through Kalycoin d command line, same options will be required to add to corresponding Kalycoin -cli command, e.g.:

./kalycoin -cli -rpcuser=test -rpcpassword=test1234 getinfo

### **Check options list by command line**

You can check the complete option list with：

./kalycoind -help

&#x20;
