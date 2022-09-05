# Using KLC official Repository on Linux

We've published our official Kalycoin repository on https://repo.explorer.kalycoin.io  this repository supports the following distributions:

### Debian

- 8.x (Jessie)
- 9.x (stretch)
- 10x (Buster)
- Testing (Bullseye)
- Unstable (Sid)

### Ubuntu

16.04 - 20.10

### Mint

18.x

## Other official repositories

### Centos/Fedora/Redhat

Tested on Centos 7, 8 and Fedora 30. Other releases should work fine as well.

https://rpmrepo.explorer.kalycoin.io

### Archlinux

[Get it from the AUR](https://aur.archlinux.org/packages/kalycoin-core/) 

More distributions will be added in the future, this document will be updated to reflect those changes.

# Tutorial focus

This tutorial assumes you have a basic knowledge of Linux and terminal usage, the entire process uses the Linux terminal.

# Installing on Ubuntu

### Obtaining signing key

First, we need to obtain the Kalycoin signing key from the ubuntu keyserver, here's how:

![](https://kalycoin.s3.amazonaws.com/repos/ubuntu1.png)

`sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys  BF5B197D`

This will download and add the Kalycoin signing key to your linux install.

### Adding repository to your APT sources.

![](https://kalycoin.s3.amazonaws.com/repos/ubuntu2.png)


` echo "deb https://repo.explorer.kalycoin.io/apt/ubuntu/ $(lsb_release -cs) main" |sudo tee -a /etc/apt/sources.list.d/kalycoin.list`


### Refreshing APT sources and installing Kalycoin

![](https://kalycoin.s3.amazonaws.com/repos/ubuntu3.png)

`sudo apt update && sudo apt install kalycoin`

By doing this, we'll update our sources and install Kalycoin on our ubuntu Box

![](https://kalycoin.s3.amazonaws.com/repos/ubuntu4.png)



# Installing on Debian

First, we need to make sure **sudo** is installed: 

Type `sudo su` and press enter, if you get a password prompt, then you can move on to obtaining the public key

### Installing sudo

Obtain admin privileges (su to root) and then type your admin user (root) password

Once you're logged in as "root" please type the following: `apt-get install sudo`

When sudo finishes installing, add your user to the sudo group: `gpasswd -a youruser sudo`
Logout and then log in again.

### Installing dirmngr and apt-transport-https

![](https://kalycoin.s3.amazonaws.com/repos/debian1.png)

These two packages are needed to enable the Kalycoin repository on Debian, let's install them:

`apt install -y apt-transport-https dirmngr`

### Obtaining Public key

![](https://kalycoin.s3.amazonaws.com/repos/debian1.png)

`sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys  BF5B197D`

This downloads and installs the Kalycoin public key

### Adding repository to your APT sources.

![](https://kalycoin.s3.amazonaws.com/repos/debian3.png)

`sudo su` - Sudo to root first

` echo "deb https://repo.explorer.kalycoin.io/apt/debian/ buster main" >> /etc/apt/sources.list.d/kalycoin.list`

This will add the repository to your APT sources file. **NOTE:** Please remember to change "stretch" for your Debian version codename <!--(for instance, Debian 8.x codename is jessie, in this case you need to replace stretch for jessie)-->

### Refreshing APT sources and installing Kalycoin

![](https://kalycoin.s3.amazonaws.com/repos/debian4.png)

`sudo apt update && sudo apt install kalycoin`

By doing this, we'll update our sources and install Kalycoin on our debian Box

![](https://kalycoin.s3.amazonaws.com/repos/debian5.png)



# Install on Centos/Redhat/Fedora

These are the steps you need to take to install Kalycoin in a RPM-based distribution

![](https://kalycoin.s3.amazonaws.com/repos/centos1.png)

1. Install the public key for the RPM repository:
   
   `sudo rpm --import https://rpmrepo.explorer.kalycoin.io/key.asc  `

   ![](https://kalycoin.s3.amazonaws.com/repos/centos2.png)
   
2. Add the Kalycoin repository:
   
   `sudo yum-config-manager --add-repo https://rpmrepo.explorer.kalycoin.io/`

   ![](https://kalycoin.s3.amazonaws.com/repos/centos3.png)
   
3. `sudo yum update`

   ![](https://kalycoin.s3.amazonaws.com/repos/centos4.png)

4. `sudo yum install kalycoin`

![](https://kalycoin.s3.amazonaws.com/repos/centos5.png)

You can also use dnf to install Kalycoin on Fedora and distributions that support it.



# Install on Archlinux

To install on arch, the easiest way is to use "yay" https://aur.archlinux.org/packages/yay

You can install Kalycoin using the source files, but this will take a long time to compile from source. In most cases, we recommend using the binary release with: `yay kalycoin-core-bin`

![](https://kalycoin.s3.amazonaws.com/repos/arch1.png)

This will bring up a dialog where you need to confirm that you want to install the above mentioned package, press "1" to confirm .

![](https://kalycoin.s3.amazonaws.com/repos/arch2.png)

![](https://kalycoin.s3.amazonaws.com/repos/arch3.png)

![](https://kalycoin.s3.amazonaws.com/repos/arch4.png)

![](https://kalycoin.s3.amazonaws.com/repos/arch5.png)

## Launching Kalycoin

Launching is simple, we just go to our applications menu and scrolldown/search for kalycoin 

