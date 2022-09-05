# Testnet User Guide

Kalycoin Testnet offers a public blockchain for testing and development. Free KLC Testnet coins are available from a faucet and users can test transactions, staking, smart contract creation and operations, KRC20 transactions, etc. Testnet is a separate blockchain from Mainnet. It has different blocks, different transactions, and different coins, but the operation, protocols and specifications are identical to Mainnet (unless new features are being introduced on Testnet).

The Kalycoin Core wallet application can be set to run on Testnet with the command line parameter "`-testnet`" on startup. A Testnet wallet works identically to a Mainnet wallet except it will use the \Kalycoin\testnet3 data directory and default port 13888. An additional test mode "regtest" is described below.

# Testnet Explorer

Explorer https://testnet.explorer.kalycoin.io/

Older Explorer https://testnet.kalycoin.io/

# Testnet Faucet

Get free Testnet KLC, once every 24 hours http://testnet-faucet.explorer.kalycoin.io

![1 KalycoinTestnetFaucet](https://user-images.githubusercontent.com/29760787/60824430-92590b00-a177-11e9-87bb-b351e0ac60f2.jpg)
 Kalycoin Testnet Faucet

# Testnet on the Kalycoin Web Wallet

Select Settings – Network – Testnet https://kalycoinwallet.org/

Select the network (Testnet or Mainnet) **before** restoring from a key file and entering the password.

## Testnet on the Kalycoin Core wallet

1. Download and install the Kalycoin Core wallet for Mac, Linux or Windows from https://kalycoineco.io/wallet or for all versions from https://github.com/kalycoinproject/kalycoin/releases. See the user documentation for wallets at https://docs.kalycoin.io/

2. Launch the wallet on Testnet

You can launch the wallet on Testnet by using the "`-testnet`" command line parameter on startup.

The Kalycoin Testnet data directories are:

* On macOS/OS X: ~/Library/Application Support/Kalycoin/testnet3
* On Linux: ~/.kalycoin/testnet3
* On Windows: %APPDATA%\Kalycoin\testnet3

## macOS

Using Apple macOS, to launch the kalycoin-qt GUI wallet on Testnet use Terminal and change directory to the Kalycoin app and launch the wallet with the `--testnet` parameter, using these commands:

```
cd /Applications/Kalycoin-Qt.app/Contents/MacOS
./Kalycoin-Qt --testnet
```

![2 MacKalycoin-Qt--testnet](https://user-images.githubusercontent.com/29760787/60824431-92590b00-a177-11e9-93f1-2badaa168ef0.jpg)
./Kalycoin-Qt --testnet

## Linux

Using Linux, launch the wallet with "`./kalycoind -testnet`" from the bin directory. The command from the home directory is
`~/kalycoin/kalycoin-0.17.6/bin/./kalycoin-qt -testnet`

![3 kalycoin-qt-testnet Linux](https://user-images.githubusercontent.com/29760787/60824432-92590b00-a177-11e9-94f4-b6c83bfa68d0.jpg) 
~/kalycoin/kalycoin-0.17.6/bin/./kalycoin-qt -testnet

The same approach can be used to launch kalycoind (the server wallet), using Terminal with change directory to navigate to the bin directory and launch kalycoind on Testnet:

![4 kalycoind-testnet Linux](https://user-images.githubusercontent.com/29760787/60824433-92f1a180-a177-11e9-830c-0a8ac8e6d48f.jpg)
./kalycoind -testnet

For kalycoind use the Command Line Interface (CLI) kalycoin-cli to give commands, and for the Testnet wallet use the "`-testnet`" parameter. Here the "`getblockchaininfo`" command is used to verify Testnet:

![5 getblockchaininfoLinux](https://user-images.githubusercontent.com/29760787/60824434-92f1a180-a177-11e9-9a3e-b198f75e2d49.jpg)
./kalycoin-cli -testnet getblockchaininfo

## Windows

The Kalycoin Windows installation includes Startup shortcuts for Mainnet and Testnet (the Testnet shortcut automatically invokes the "`-testnet`" parameter). To launch Testnet on windows for the kalycoin-qt GUI wallet, click the Testnet app on the Start menu:

![6 WindowsStartMenuTestnet](https://user-images.githubusercontent.com/29760787/60824416-908f4780-a177-11e9-8433-05eb61fd3b5b.jpg)
Launching kalycoin-qt for Testnet

To run kalycoind for Testnet on Windows, open a command prompt window ("Command Prompt"), change directories to (on 64-bit Windows) C:\Program Files\Kalycoin\daemon and launch with the command `kalycoind.exe -testnet`:

![7 kalycoind-testnetWindows](https://user-images.githubusercontent.com/29760787/60824417-908f4780-a177-11e9-9552-95dcc5dbf2a9.jpg)
 kalycoind.exe -testnet

To use the Command Line Interface, open another Command Prompt window, change directories to Program Files/Kalycoin/daemon, and enter the commands for kalycoin-cli with the "`-testnet`" prefix. For example, to confirm Testnet with `kalycoin-cli.exe -testnet getblockchaininfo`:

![8 getblockchaininfo Windows](https://user-images.githubusercontent.com/29760787/60824418-9127de00-a177-11e9-9b04-6950bf428c23.jpg)
kalycoin-cli.exe -testnet getblockchaininfo

## The configuration file "kalycoin.conf"

Another way to launch the Core wallet on Testnet is to include "`testnet=1`" in the configuration file "kalycoin.conf". This file should be located in the Kalycoin Mainnet data directory, and when the wallet launches it will read the configuration file and startup on Testnet:

![9 ConfFIleTestnet](https://user-images.githubusercontent.com/29760787/60824421-9127de00-a177-11e9-972f-e066916747ae.jpg)
(here the configuration file is renamed "kalycoin.conf.txt" for editing and renamed "kalycoin.conf" after)

# regtest

Regression Test (regtest) is another test blockchain that runs as local blockchain. regtest can be run in a Docker container (https://github.com/kalycoinproject/documents/blob/master/en/Launch-Kalycoin-with-Docker.md). To run the Core wallet for regtest on a desktop or server, use the "`-regtest`" parameter to launch as shown in the examples above.

![10 regtestkalycoin-qt](https://user-images.githubusercontent.com/29760787/60824422-91c07480-a177-11e9-97c6-7ae4f5c5b33d.jpg)
kalycoin-qt on regtest, mining two blocks a minute

A typical sequence after regtest is launched is to manually create blocks (using the "`generate`" command) and then run tests using transactions created:

![11 regtestgenerate600](https://user-images.githubusercontent.com/29760787/60824423-91c07480-a177-11e9-891c-b5cc8aefabff.jpg)
generate 600

regtest wallets use the /Kalycoin/regtest or \Kalycoin\regtest data directory, have default port 23888, and will be generating Proof of Work blocks with block rewards of 20,000 KLC for the first 5,000 blocks.

# Testnet Troubleshooting

1. If your new or updated wallet is having trouble making peer connections for Testnet, try the "`addnode`" command with the peers below. The correct response is "null" for kalycoin-qt or nothing for kalycoind, and then the wallet will try for the next few minutes to make the peer connections. Enter one or more of these commands:

```
addnode 35.197.235.28:13888 add
addnode 52.79.250.137:13888 add
addnode 47.89.255.216:13888 add
addnode 120.27.209.201:13888 add
addnode 35.197.132.10:13888 add
```
 
![12 Addnode](https://user-images.githubusercontent.com/29760787/60824425-91c07480-a177-11e9-918d-3c6ae2db609b.jpg)
-testnet addnode 47.89.255.216:13888 add

2. On the Web Wallet see "*Restore from key file failed. Maybe the password is not correct*"

In switching between Mainnet and Testnet with the Web Wallet (Settings – Network), switch networks **before** loading the key file and entering the password.

3. The Testnet Faucet gives "*You can only request tokens once every 24 hours*" on first use or > 24 hours after the previous use.

Click the address bar checkmark button several times until the green confirmation bar appears:

![13 FaucetSuccess](https://user-images.githubusercontent.com/29760787/60824426-91c07480-a177-11e9-8dfb-a6b534a60500.jpg) 
http://testnet-faucet.explorer.kalycoin.io


