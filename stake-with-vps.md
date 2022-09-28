# Stake with VPS

## **Staking with a VPS**

Many users prefer using a VPS for staking purposes, it is safer than using your local machine and it is more convenient for most people as you don't need to leave your computer turned on 24/7, there are also some very cheap and stable solutions you can use.

[You can also take advantage of the powerful solution we have at the AWS marketplace which is easier to setup and ready to go in just a few minutes!](https://aws.amazon.com/marketplace/pp/B07FB214D3)

In this tutorial we'll show how to do this using **Vultr** [https://vultr.com](https://vultr.com/) which is a very stable, cost effective and fast provider with instances all over the world, the same principles apply to any other cloud provider you may prefer.

### **Launching instance**

Let's begin, we log into our cloud provider dashboard where we get several options.

<figure><img src=".gitbook/assets/imagen (31).png" alt=""><figcaption></figcaption></figure>

Choose a location for the VPS, for this test we've chosen Miami.

<figure><img src=".gitbook/assets/imagen (6).png" alt=""><figcaption></figcaption></figure>

Choose a server type, our linux wallet runs on any linux distribution, however, it is recommended to use Ubuntu 18.04 if you want to compile the wallet yourself, (we'll do this on this tutorial). You can select any desired option, we went with a basic 1CPU/512MB ram VPS.

**SSH Keys**

It is recommended to use ssh-key to login instead of passwords, its far more secure and convenient.

Creating ssh-keys is out of the scope of this tutorial, but here are some good references on how to do this:

[https://www.vultr.com/docs/how-do-i-generate-ssh-keys](https://www.vultr.com/docs/how-do-i-generate-ssh-keys)

[https://www.digitalocean.com/community/tutorials/how-to-set-up-ssh-keys--2](https://www.digitalocean.com/community/tutorials/how-to-set-up-ssh-keys--2)

[https://docs.joyent.com/public-cloud/getting-started/ssh-keys/generating-an-ssh-key-manually/manually-generating-your-ssh-key-in-windows](https://docs.joyent.com/public-cloud/getting-started/ssh-keys/generating-an-ssh-key-manually/manually-generating-your-ssh-key-in-windows) < _this one is for Windows users._

After we've created our SSH key, we click on "add new"

<figure><img src=".gitbook/assets/imagen (20).png" alt=""><figcaption></figcaption></figure>

Here we can paste our SSH-key, enter a name for it and click on add ssh key.

<figure><img src=".gitbook/assets/imagen (23).png" alt=""><figcaption></figcaption></figure>

### **Logging in to your VPS**

Once we have our credentials ready, we log in and see the following screen

<figure><img src=".gitbook/assets/imagen (43).png" alt=""><figcaption></figcaption></figure>

### ****

#### Build on Ubuntu Server

This is a quick start script for compiling Kalycoin on Ubuntu

```
sudo apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils git cmake libboost-all-dev libgmp3-dev
sudo apt-get install software-properties-common
sudo add-apt-repository ppa:bitcoin/bitcoin
sudo apt-get update
sudo apt-get install libdb4.8-dev libdb4.8++-dev

# If you want to build the Qt GUI:
sudo apt-get install libqt5gui5 libqt5core5a libqt5dbus5 qttools5-dev qttools5-dev-tools libprotobuf-dev protobuf-compiler qrencode

git clone https://github.com/kalycoinproject/kalycoin --recursive
cd kalycoin

# Note autogen will prompt to install some more dependencies if needed
./autogen.sh
./configure 
make -j2
```

### **Launching Kalycoin daemon**

Kalycoin d -daemon -> This launches the Kalycoin daemon and the blockchain begins to synchronize right after launching. It can take some minutes before it's fully synced.

### **Encrypting wallet**

We can encrypt the wallet at any time, it's better to do it before we go any further.

To do this, type the following on the command line:

Kalycoin -cli encryptwallet yourpassword

This will encrypt the wallet which in turn closes the daemon, you'll see the following message:

wallet encrypted; Kalycoin server stopping, restart to run with encrypted wallet. The keypool has been flushed and a new HD seed was generated (if you are using HD). You need to make a new backup.

<figure><img src=".gitbook/assets/imagen (15).png" alt=""><figcaption></figcaption></figure>

Kalycoin -cli getaccountaddress "" -> Right after launching the daemon, you can obtain your wallet address by typing this.

You can send Kalycoin coins to the address we just obtained from the daemon, please remember that those transactions require at least 500+ confirmations before they become mature enough for staking.

### **Staking**

Now that we've waited until we have at least 501 confirmations on our received transaction, we are elligible for staking, however, if our wallet is encrypted (which we did for security reasons) we won't be able to stake, let's open our wallet for staking using the command line!.

Kalycoin -cli walletpassphrase password 999999999 true

The above command will unlock the walet **for staking only** for 31.6 Years! that should be enough for now. Please note, this will not unlock your backup, only the wallet that's running right now.

Now that we've unlocked our wallet, we need to wait until we have more than 501 confirmations to be elligible for staking, if we already do, it's a matter of time which will vary depending on the network weight vs your wallet's weight.

### **Checking Balance**

To check your balance, type Kalycoin -cli getinfo this will show general information, including your available balance and balance in staking

**Check transactions**

To check your transactions (incoming and outgoing) type Kalycoin -cli listtransactions

### **Check staking info**

To check Kalycoin 's staking information, type Kalycoin -cli getstakinginfo

### **Staking tips**

Staking really depends on network weight vs your wallet’s weight which is based on the amount of coins you have, higher weight increases your chances of staking a block.

If you have a large amount of coins, it’s a good idea to split those up in separate transactions, for instance, if you have 10.000  KLC, it’s better to send 10 transactions of 1000  KLC each to your wallet, each one generates a UTXO input which will take part in staking. This optimizes the staking process and works much better than just one large 10.000  KLC input.

If you want to split your coins into different addresses inside your VPS wallet, type the following to obtain new addresses inside your wallet: Kalycoin -cli getnewaddress Each time you type this, you’ll get a new address, KLC can generate any amount of addresses you want, but please keep in mind, if you do go over 100 new address, you might want to make a new backup of your wallet.

### **Wallet Backup**

Backing up your wallet from a Linux VPS is different from a desktop but not too complicated, there's several ways to do this, and here are some steps which should work on all major desktop OS.

First, we'll download Filezilla, which is an easy to use and secure FTP/SFTP server

{% embed url="https://filezilla-project.org" %}

Installing is just like any other windows app.

When the installer finishes, we launch Filezilla and are greeted with this screen, let's proceed and add our previously created ssh-key

We go into Edit -> Settings -> SFTP. This will give us the following screen in which we will be able to import our SSH key.

Please note that Filezilla only accepts the private key which is created when the ssh-key was generated.

Here we've already added the ssh key, now we can log into our server

we enter our VPS ip address + username (root in this case), leave a blank password because we're using ssh-key to login

Just press ok when prompted, and you'll be able to log in.

Here we can see the /root/ folder of our VPS, this is where our wallet runs and has the wallet stored in /root/. Kalycoin we can go ahead and double click the folder which will show us the following:

Now all we need to do is scroll down to wallet.dat, right click and select download from the list. This will download the wallet.dat file to our computer, we've successfully backed up our Kalycoin wallet!.

### **Updating wallet**

### **If you installed Kalycoin the old way (without using the repository)**

We highly recommend using the repository from now on, however, if you still want to compile the wallet yourself, here’s how to upgrade: **(Backup your wallet.dat first)** cd \~/ Kalycoin / git pull ./configure make Kalycoin -cli stop make install Kalycoin d -daemon

### **What happened there?**

·         We updated the sources from the original build folder (if you don’t have it anymore, you need to pull the entire repo as was shown in the beginning of this tutorial).

·         We configured and built the new Kalycoin daemon

·         We stopped the old daemon

·         We installed the new daemon

·         We executed the new daemon

### **If you installed Kalycoin using the repo**

If you used the repository to install your Kalycoin wallet, it’s very easy to upgrade to a new version, all you have to do is the following:

apt update && apt upgrade

This will update the apt sources on your Linux box and install the latest packages, Kalycoin included. If you only want to upgrade Kalycoin:

apt update && apt install —only-upgrade Kalycoin
