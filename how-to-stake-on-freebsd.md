# How to stake on FreeBSD

### **Staking Kalycoin on FreeBSD**

FreeBSD is a very powerful operating system, it has a great history of reliability, security and stability. Here we show how it can be used to stake Kalycoin in a secure way.

### **Sandboxing Kalycoin in a FreeBSD jail**

FreeBSD jails are a very powerful feature, in summary, your jail instance is more protected as it's like having a separate OS just for Kalycoin with reduced privileges.

Here's a good read on Jails: [https://www.freebsd.org/doc/handbook/jails.html](https://www.freebsd.org/doc/handbook/jails.html)

**FreeBSD version used for this tutorial is 12.2, download it from the official FreeBSD mirrors:**

[https://www.freebsd.org/where/](https://www.freebsd.org/where/)

### **Installing FreeBSD**

**Important**: Make sure to install and enable NTP, it's necesary to stay synchronized to network clocks.

Install FreeBSD as normal, however, the following hardening settings are recommended during install:

![](<.gitbook/assets/image (34).png>)

### **Create user**

Create a user with permissions "operator wheel"

![](<.gitbook/assets/image (39).png>)

Please remember to do all these commands as root

### **Host:**

### **/etc/sysctl.conf**

### **Allow sockets and upgrades in jail**

security.jail.allow\_raw\_sockets=1

security.jail.chflags\_allowed=1

![](<.gitbook/assets/image (33).png>)

### **/etc/rc.conf**

firewall\_enable="YES"

firewall\_quiet="YES"

firewall\_type="workstation"

firewall\_myservices="22 3888"

firewall\_allowservices="any"

firewall\_logdeny="YES"

jail\_enable="YES"

![](<.gitbook/assets/image (47).png>)

Notice that we've added some settings for firewall, these will enable IPFW and basic settings to secure our Jail, allowing only ports 22(ssh) and 3888(Kalycoin) to be accessed.

### **Resource limits for Jails**

### **/boot/loader.conf**

kern.racct.enable=1

jail\_enable="YES"

![](<.gitbook/assets/image (41).png>)

### **Creating our Jail for staking**

zfs create -o mountpoint=/jail zroot/jail

**(Change zroot for whatever name you chose for your zfs pool)**

zfs create -o mountpoint=/jail/ Kalycoin zroot/jail/ Kalycoin

### **Now we've created our jail for staking Kalycoin, let's fetch and install FreeBSD on it!**

cd /jail/ Kalycoin/ && fetch -o - http://ftp.freebsd.org/pub/FreeBSD/releases/amd64/12.2-RELEASE/base.txz | tar --unlink -xpJf - -C /jail/ Kalycoin

### **We've now installed FreeBSD into /jail/** **Kalycoin**

Typing ls /jail/ Kalycoin/ should show the filesystem of our Kalycoin FreeBSD Jail

Now, let's create the jail configuration file:

### **/etc/jail.conf**

```
Kalycoin {
host.hostname = Kalycoin.local;
ip4.addr = 192.168.0.99;
interface = em0;
path = /jail/ Kalycoin;
exec.start = "/bin/sh /etc/rc";
exec.stop = "/bin/sh /etc/rc.shutdown";
exec.clean;
mount.devfs;
allow.raw_sockets;
allow.sysvipc;
}
```

Ok now it's time to launch our jail!

service jail start Kalycoin

#### **We've just started our Kalycoin jail, We can now get into our Kalycoin jail to finish configuration, install Kalycoin and launch the wallet.**

jexec Kalycoin /bin/csh

cp /usr/share/zoneinfo/YOURTIMEZONE/ /etc/localtime This is very important, if the time info is incorrect, we'll produce orphan blocks or will be unable to sync

Create our basic /etc/rc.conf for our Kalycoin Jail

### **Kalycoin Jail:**

### **/etc/rc.conf**

```
syslogd_flags="-s -s"
sshd_enable=YES
clear_tmp_enable=YES
clear_tmp_X=YES
extra_netfs_types=NFS
dumpdev=NO
update_motd=NO
keyrate=fast sendmail_enable=NONE
sendmail_submit_enable=NO
sendmail_outbound_enable=NO
sendmail_msp_queue_enable=NO
```

### **Add dns nameservers to /etc/resolv.conf**

echo "nameserver 8.8.8.8" >> /etc/resolv.conf

echo "nameserver 8.8.4.4" >> /etc/resolv.conf

### **Installing Kalycoin**

Now that we've got our jail up and running, we need to install Kalycoin. There's 2 options on doing this, we can use the pkg repository or the powerful FreeBSD ports which are usually updated faster:

**pkg repository**

pkg update -f pkg install -y Kalycoin

![](<.gitbook/assets/image (157).png>)

#### **FreeBSD ports**

portsnap fetch extract cd /usr/ports/net-p2p/ Kalycoin && make install clean

The above will ask for a lot of configuration options, it might be better to use make config-recursive to set all options before compiling. If you want to use default settings just type cd /usr/ports/net-p2p/ Kalycoin && make install clean BATCH="YES"

### **Running Kalycoin**

Launching Kalycoin is just like in any other \*NIX operating system, however there's a minor difference here due to how FreeBSD jails work. First, we need to create a Kalycoin.conf file with the following contents:

This config is necessary, otherwise calling the daemon will return errors.

Then we can launch with Kalycoind -daemon

### **Security tips**

·         Set up firewall on host (you cannot setup a firewall inside a jail) and enable only the ports you need (22 and 3888) This is done in the host rc.conf at the top of this tutorial

·         Disable history, this will completely disable console history and it's a way to help secure your staking box, type the following on your FreeBSD console: unset history; unset savehist

·         Secure SSH:



1. Disable password authentication

![](<.gitbook/assets/image (167).png>)

![](<.gitbook/assets/image (160).png>)

![](<.gitbook/assets/image (155).png>)

• If using the FreeBSD box on your home network, force it to listen on local network only

![](<.gitbook/assets/image (175).png>)



