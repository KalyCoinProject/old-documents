# Kalycoin on Raspberry Pi

1. [Getting a Stakebox](#Getting-a-Stakebox)
2. [Downloading Kalycoin Raspbian](#Downloading-Kalycoin-Raspbian)
3. [Screenshots of Kalycoin Raspbian](#Screenshots-of-Kalycoin-Raspbian)
4. [Installing Kalycoin via Kalycoin Raspbian repository](#Installing-Kalycoin-via-Kalycoin-Raspbian-repository) **(only needed if you're not using a Kalycoin stakebox or not using the Kalycoin Raspbian image)**
5. [Raspberry Pi Zero](#raspberry-pi-zero)
6. [Setting up a firewall in Raspbian](#Protecting-access-with-a-basic-firewall)
7. [Launching Kalycoin daemon](#Launching-Kalycoin-daemon)
8. [Encrypting wallet](#Encrypting-wallet)
9. [Staking](#Staking)
10. [Backup](#How-to-backup-to-a-separate-device)
11. [Editing Configuration File](#Editing-Configuration-File)

### Getting a Stakebox

There's several ways to run Kalycoin on a Raspberry Pi, perhaps the easiest way is to just get a **Kalycoin Stakebox**, you can order from here:

<https://www.stakebox.org/products/kalycoin-stakebox>

***

### Downloading Kalycoin Raspbian

If you don't want to buy or already own a stakebox and just want to get the latest version of Raspbian with Kalycoin preinstalled with the official Kalycoin Repository, then you can download the Raspbian images yourself:

**PLEASE NOTE** if you're running a previous release of Kalycoin-Raspbian or have installed Kalycoin through the Repository. All you need to do to update your Kalycoin wallet is type in a terminal the following:

`sudo apt update && sudo apt -y upgrade`

# New Kalycoin Raspbian Release!

### Changelog:

- Upgrade to Debian Buster 10.9 release
- Kalycoin 0.20.3

#### Kalycoin Raspbian 64bit (Recommended from Raspberry Pi 2 - Raspberry Pi 4)

https://raspbianimages.s3.amazonaws.com/image_2021-06-20-KalycoinOS-lite.zip
https://raspbianimages.s3.amazonaws.com/image_2021-06-20-KalycoinOS.zip



### "Burning" the Kalycoin Raspbian image to your SD card

Please watch this video tutorial which shows how to download, burn and use your Kalycoin Raspbian image

https://www.youtube.com/watch?v=0W6NlIk7Tgw&t=0s

***

### What is SWAP anyway?

SWAP enables "virtual memory", it uses a portion of your disk to store data that cannot be stored in RAM, this helps devices like the Pi Zero to continue running without crashing even if the applications are using more than the 512MB RAM included with the Pi Zero.

### Creating a 2gb SWAP file

Enabling SWAP on the Pi  is extremely easy:

1. Open up a terminal as shown on the screenshot below

   ![2zero](2zero.png)

   Inside the terminal, type "sudo dphys-swapfile setup" and press enter

   You'll see text coming up, and a confirmation of your 2gb SWAP file being generated.

2. Still inside the same terminal, type "sudo dphys-swapfile swapon" and press enter
   This won't give you any confirmation, however, your SWAP file has been setup and activated!. You only need to do this once, the Pi Will activate your SWAP file in case of a reboot/shutdown.

   ![3zero](3zero.png)

3. Here we can see that the SWAP file is active giving us a total of 2.42GB of RAM (SWAP and ZRAM included)

   ![4zero](4zero.png)

### IMPORTANT NOTE!

**Kalycoin raspbian** default user is **kalycoin** and default password is **kalycoin1234**. You will need to enter these on first login and you will be asked by the login system to change your password immediately, please make sure to use a strong password!

***

### Screenshots of Kalycoin Raspbian

![kalycoinrasp1](kalycoinrasp1.png)

In order to launch Kalycoin, we need to go to the menu and go to internet -> Kalycoin

![kalycoinrasp2](kalycoinrasp2.png)

Once you click on it, you'll see the following screen mentioning some details regarding disk usage and disk space available on your raspberry pi.

![kalycoinrasp3](kalycoinrasp3.png)

After clicking ok, your Raspberry Pi will begin syncing!

![kalycoinrasp4](kalycoinrasp4.png)

Syncing on your raspberry can take anything from a couple of hours to a day, please be patient.

![kalycoinrasp5](kalycoinrasp5.png)

The Kalycoin raspbian image has also some cool wallpapers to choose from:

![wallpaper1](wallpaper1.png)

![wallpaper2](wallpaper2.png)

![wallpaper3](wallpaper3.png)

***

## Installing Kalycoin via Kalycoin Raspbian repository

If you're using a **"normal"** raspbian install, you can add the Kalycoin repository to install Kalycoin and keep with updates easily!

### Install dirmngr & apt-transport https

```sudo apt install -y dirmngr apt-transport-https  ```

### Add kalycoin public key

`sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys BF5B197D`

### Adding repository to your APT sourcess

`sudo su` - Sudo to root first

` echo "deb https://repo.explorer.kalycoin.io/apt/raspbian/ buster main" >> /etc/apt/sources.list`

This will add the repository to your APT sources file.

### Refreshing APT sources and installing Kalycoin

`sudo apt update && sudo apt install kalycoin`

By doing this, we'll update our sources and install Kalycoin on our raspberry Box, which can act now as a staking server/node.

## Changing default password

**PLEASE NOTE: you will only really need to do this if you're using a "clean" raspbian image; you won't need to do this if you're using a Stakebox or the official Kalycoin Raspbian**

This option is recommended for security reasons, the default password on the pi is well known, it's highly recommended to change it upon first login.

To change just type: `passwd`

The prompt will ask you to write and repeat the new password to confirm.

***

## Protecting access with a basic firewall

Well, our raspberry is only for staking, there's no need to have all those ports open, let's close everything we don't need and only allow access to necesary services.

First, let's install UFW (uncomplicated firewall) which is an easy-to-use interface for iptables

`sudo apt install ufw`

Once this is installed, we proceed with access permissions, we will define which ports will be accessible. Let's check first what's open:

`sudo ufw status` This should show something like this:

`Status: active`

`To               Action      From`

`--               ------      ----`

`22               ALLOW       Anywhere`

#### Ok so it's time to start closing down access, type the following:

`sudo ufw default deny incoming`

`sudo ufw allow 3888/tcp`

Here we've defined the basics, closing down everything except port 3888 and 3889 which are used by Kalycoin to function.

If you're using SSH, it's recommended to only allow access from local network.

`sudo ufw allow from 196.168.0.0/24 to any port 22`

## Binaries available on Raspberry Pi

- kalycoind
- kalycoin-cli
- kalycoin-qt
- kalycoin-tx

***

## Launching Kalycoin daemon

All we need to do to launch the Kalycoin daemon is type:
`kalycoind -daemon`

As soon as you type this, the wallet will create the wallet.dat file among other files (if they’re not already there). The wallet will run and begin syncing instantly from the other Blockchain nodes, this can take a few hours to complete so you can go ahead and have some coffee and let it synchronize.

## Launching Kalycoin-Qt

If you're using Raspberry Pi desktop interface, all you need to do is navigate to the applications menu->other->kalycoin-qt

***

## Encrypting wallet

We can encrypt the wallet at any time, it's better to do it before we go any further.

To do this, type the following on the command line:

`kalycoin-cli encryptwallet yourpassword`

This will encrypt the wallet which in turn closes the daemon, you'll see the following message:

`wallet encrypted; Kalycoin server stopping, restart to run with encrypted wallet.` If you alreadby backed up before encrypting, you **need to make a new backup.**

`kalycoin-cli getaccountaddress` "" -> Right after launching the daemon, you can obtain your wallet address by typing this.

You can send Kalycoin coins to the address we just obtained from the daemon, please remember that those transactions require at least 500+ confirmations before they become mature enough for staking.

***

## Staking

Now that we've waited until we have at least 501 confirmations on our received transaction, we are elligible for staking, however, if our wallet is encrypted (which we did for security reasons) we won't be able to stake, let's open our wallet for staking using the command line!.

`kalycoin-cli walletpassphrase password 999999999 true`

The above command will unlock the walet for 31.6 Years! that should be enough for now. Please note, this will not unlock your backup, only the wallet that's running right now.

Now that we've unlocked our wallet, we need to wait until we have more than 501 confirmations to be elligible for staking, if we already do, it's a matter of time which will vary depending on the network weight vs your wallet's weight.

## Checking Balance

To check your balance, type kalycoin-cli getinfo this will show general information, including your available balance and balance in staking

## Check transactions

To check your transactions (incoming and outgoing) type kalycoin-cli listtransactions

## Check staking info

To check Kalycoin's staking information, type kalycoin-cli getstakinginfo

## Staking tips

Staking really depends on network weight vs your wallet’s weight which is based on the amount of coins you have, higher weight increases your chances of staking a block.

If you have a large amount of coins, it’s a good idea to split those up in separate transactions, for instance, if you have 10.000 KLC, it’s better to send 10 transactions of 1000 KLC each to your wallet, each one generates a UTXO input which will take part in staking. This optimizes the staking process and works much better than just one large 10.000 KLC input.

If you want to split your coins into different addresses inside your Rasbperry Pi wallet, type the following to obtain new addresses inside your wallet: kalycoin-cli getnewaddress Each time you type this, you’ll get a new address, KLC can generate any amount of addresses you want, but please keep in mind, if you do go over 100 new address, you might want to make a new backup of your wallet.

## Updating wallet

We’re always launching new updates, sometimes it’s to add new features or fix bugs. In any case, updating is a breeze, all you have to do is type
` sudo apt update && sudo apt upgrade -y `

***

## How to backup to a separate device

Making a backup in Raspberry is simple, you only need to copy the wallet.dat file, but how do you export this to another device?

First, we'll download Filezilla, which is an easy to use and secure FTP/SFTP server

[https://filezilla-project.org](https://filezilla-project.org/)

![img](https://docs.kalycoin.io/en/How-to-Stake-KLC-using-a-Linux-Virtual-Private-Server/filezilla1.png)

Installing is just like any other windows app.

![img](https://docs.kalycoin.io/en/How-to-Stake-KLC-using-a-Linux-Virtual-Private-Server/filezilla2.png)

When the installer finishes, we launch Filezilla and are greeted with this screen, let's proceed and add our previously created ssh-key

We go into Edit -> Settings -> SFTP. This will give us the following screen in which we will be able to import our SSH key.

![img](https://docs.kalycoin.io/en/How-to-Stake-KLC-using-a-Linux-Virtual-Private-Server/filezilla3.png)

Please note that Filezilla only accepts the private key which is created when the ssh-key was generated.

![img](https://docs.kalycoin.io/en/How-to-Stake-KLC-using-a-Linux-Virtual-Private-Server/filezilla4.png)Here we've already added the ssh key, now we can log into our server

![img](https://docs.kalycoin.io/en/How-to-Stake-KLC-using-a-Linux-Virtual-Private-Server/filezilla5.png)

we enter our Raspberry Pi ip address + username (root in this case), leave a blank password because we're using ssh-key to login ![img](https://docs.kalycoin.io/en/How-to-Stake-KLC-using-a-Linux-Virtual-Private-Server/filezilla6.png)

Just press ok when prompted, and you'll be able to log in. ![img](https://docs.kalycoin.io/en/How-to-Stake-KLC-using-a-Linux-Virtual-Private-Server/filezilla8.png)

![img](https://docs.kalycoin.io/en/How-to-Stake-KLC-using-a-Linux-Virtual-Private-Server/filezilla9.png)

Here we can see the /root/ folder of our Raspberry Pi, this is where our wallet runs and has the wallet stored in /root/.kalycoin we can go ahead and double click the folder which will show us the following: ![img](https://docs.kalycoin.io/en/How-to-Stake-KLC-using-a-Linux-Virtual-Private-Server/filezilla10.png)

Now all we need to do is scroll down to wallet.dat, right click and select download from the list. This will download the wallet.dat file to our computer, we've successfully backed up our Kalycoin wallet!.

***

### Editing Configuration File

How to edit the kalycoin.conf configuration file.

1. Launch Terminal.

2. Change directories to the Kalycoin data directory:

   `cd .kalycoin`                (location home/pi/.kalycoin for Linux install) or

   `cd /home/kalycoin/.kalycoin`     (default location for image install)

3. Launch the editor, opening an existing or making a new configuration file:

   `sudo nano kalycoin.conf`

4. Edit configuration file, for example, enter

   ```
   uacomment=Your_Kalycoin_Address
   addnode=kalycoin5.dynu.net
   ```

   ![nano Linux](https://user-images.githubusercontent.com/29760787/69094735-ec6bb600-0a1e-11ea-92b3-d6c56ab0c7d2.jpg)

5. Press Control-O to write the file.

6. For “File name to write: kalycoin.conf” press Enter.

7. Press Control-X to exit the editor.

8. Restart your Kalycoin Core wallet to load the new configuration file.

9. Check the new settings.
   For Kalycoin-Qt use Window – Information and check for your address in "User Agent":

![Kalycoin-Qt Check](https://user-images.githubusercontent.com/29760787/69094763-f55c8780-0a1e-11ea-9145-37dc47ec312e.jpg)

   For kalycoind use the command `getnetworkinfo` and check for your address in "subversion":

![kalycoind check](https://user-images.githubusercontent.com/29760787/69094752-f097d380-0a1e-11ea-8bb0-8a571681edaf.jpg)

***