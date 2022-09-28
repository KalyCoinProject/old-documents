# How to build Kalycoin on CentOS

### **Build Kalycoin on CentOS 7**

CentOS is an enterprise-oriented Linux distribution, that means it's focused for stability and security but not necessarily the latest software. With that being said, you _cannot_ currently build Kalycoin in CentOS 7 following the steps that other more recent distributions can use.

In this document we'll show how to build Kalycoin in CentOS 7 and produce a **static binary** which can then be executed on any other Linux distribution, even if it's more recent.

### **General Prerequisites**

Update Yum repositories

&#x20;   sudo yum update

### **Install development tools and libraries**

Getting ready:

sudo yum install -y tar unzip git which wget patch make autoconf automake libtool \\

&#x20;   epel-release centos-release-scl centos-release-scl-rh finduitls vim mc openssl-devel \\

&#x20;   file

Enable Devtoolset-7

yum install -y devtoolset-7-gcc\* && \\

&#x20;   echo "source scl\_source enable devtoolset-7" >> /root/.bashrc

source scl\_source enable devtoolset-7

Clone Kalycoin Github source:

git clone --recurse-submodules --depth 1 https://github.com/ Kalycoin project/ Kalycoin

### **Building Kalycoin**

cd Kalycoin && make -C depends/

DEPENDS="$(pwd)/depends/x86\_64-pc-linux-gnu"

./autogen.sh

./configure --prefix=$DEPENDS

make

Please keep in mind, this will produce a **static build** and it will take longer than a normal build.
