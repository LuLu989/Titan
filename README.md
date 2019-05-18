* Copyright (c) 2009-2019 Bitcoin Developers
* Copyright (c) 2012-2019 Peercoin Developers
* Copyright (c) 2013-2019 Novacoin Developers
* Copyright (c) 2018-2019 Titancoin Developers

What is Titancoin?
----------------
https://www.titanprojects.co

Titan Coin is an experimental new digital currency that enables instant payments to anyone, 
anywhere in the world. Titan Coin Introduces a completely new blockchain which uses Hybrid 
POW & dynamic POS SHA256 + Groestl (Dual Algorithm) for it's backbone of the transactions 
& a pos (proof of stake ) system that pays 2.5 percent per year.

 - 1 minute block target
 - 5 Billion total supply
 - POW: Ended at Block Number 17001 
 - Current Phase: Proof of Stake (POS)
 - Block Reward: 30 TTN
 - Reward Maturity: 60 blocks
 - Difficulty retargets every 30 minutes
 - P2P Port: 48144
 - RPC Port: 42812


License
-------

Titancoin is released under the terms of the MIT license. See `COPYING` for more
information or see http://opensource.org/licenses/MIT.


Get Started
-----------

1. For Linux: You can use both GUI and CLI version of Titancoin depending upon your needs.

We recommend any stable version of Ubuntu 16.04


 1.1 Installing Dependencies 

Open the terminal and run following commands one by one:


sudo apt-get install git

sudo apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils

sudo apt-get install libboost-system-dev libboost-filesystem-dev libboost-chrono-dev libboost-program-options-dev libboost-test-dev libboost-thread-dev

sudo apt-get install libboost-all-dev

sudo apt-get install software-properties-common

sudo add-apt-repository ppa:bitcoin/bitcoin

sudo apt-get update

sudo apt-get install libdb4.8-dev libdb4.8++-dev

sudo apt-get install libminiupnpc-dev

sudo apt-get install libzmq3-dev

sudo apt-get install libqt5gui5 libqt5core5a libqt5dbus5 qttools5-dev qttools5-dev-tools libprotobuf-dev protobuf-compiler 

sudo apt-get install libqt4-dev libprotobuf-dev protobuf-compiler


 1.2 Giving Permissions

Once you have installed all dependencies, next step is to give read write and execute permissions to titancoin folder. For that, go to the directory where titancoin folder is located and then run:

sudo chmod -R 777 titancoin/


 1.3 Compilation

After sucessfully giving all permissions, go to titancoin folder and run:

cd src && make clean -f makefile.unix && make -f makefile.unix

It will take a while depending upon your system's hardware configuration (RAM and Processor)


 1.4 Running Titancoin CLI

Once compilation successfully ends, you can run Titancoin daemon with following steps:

a) Make sure you are in src folder of Titancoin ( your_directory/Titancoin/src )
b) Run: ./Titancoind -daemon
c) The above comamnd will create "data directory for Titancoin"(.Titancoin folder) in your home folder. And will flash an error message:

(The error message flashes for the first time only, not for subsequent uses)

Error: To use the "-daemon" option, you must set a rpcpassword in the configuration file:
/home/your_linux_username/.Titancoin/Titancoin.conf
It is recommended you use the following random password:
rpcuser=Titancoinrpc
rpcpassword=some_long_password
(you do not need to remember this password)
The username and password MUST NOT be the same.
If the file does not exist, create it with owner-readable-only file permissions.

d) Run: touch /home/your_linux_username/.Titancoin/Titancoin.conf
e) Run: nano /home/your_linux_username/.Titancoin/Titancoin.conf
NOTE: Replace "your_linux_username" in above commands with your own linux username

f) Copy rpc credentails from error message to Titancoin.conf file and save.
g) Run: ./Titancoind -daemon ( This time there won't be any error message )
h) Run: ./Titancoind getinfo (To check conenction status, blocks and other information)
You have a running CLI wallet now

i) Refer to cli-commands for more information.

 1.5 Running Titancoin-qt (Linux GUI Wallet)

After successfully comiling Titancoin CLI, you can proceed for Titancoin-qt Wallet

a) Make sure you are in Titancoin's root directory ( your_directory/Titancoin)
b) Run: qmake
b) Run: make
c) You will see GUI wallet being complied on your screen, it will take some time.
d) Once compilation ends, Run: ./Titancoin-qt
e) You will see an Titancoin-qt icon in your Titancoin's root Directory, use that for subsequent uses.

Enjoy your GUI wallet


2. For Windows: GUI client is available.

2.1 Use the QT Executable file (TitanCoin-qt.exe) to run Titancoin GUI Wallet on your PC.

2.2 Data Directory is located at: Users/your_windows_user/AppData/Roaming/Titancoin


3. CLI Commands (for linux)

3.1 Make sure you are in src folder of Titancoin ( your_directory/Titancoin/src )

3.2 Run daemon: ./Titancoind -daemon
    (It will take some time, press Enter key if it's too long)

3.3 Run given CLI commands to use your CLI Wallet:

a) Check you CLI Wallet's Status: ./Titancoind getinfo

b) Check your Wallet's Balance: ./Titancoind getbalance

c) Check number of Nodes you are connected to: ./Titancoind getconnectioncount

d) Display Detailed information of Connected Nodes: ./Titancoind getpeerinfo

e) Generate New Address for Wallet: ./Titancoind getnewaddress

f) Send some TTN amount to a TTN address: ./Titancoind sendtoaddress  "TTN Address"  "Amount"

   example: ./Titancoind sendtoaddress JffkJB7NoELgopfFeopH2yCq7V6gABxTru 0.999

g) View all transactions in your wallet: ./Titancoind listtransactions

h) Encrypt CLI and GUI Wallet: ./Titancoind encryptwallet  "passphrase"

   example: ./Titancoind encryptwallet thehard*&password!!

i) Unlock CLI Wallet for given time (in seconds): ./Titancoind walletpassphrase  "passphrase"  "timeout"

   example: ./Titancoind walletpassphrase theahard*&password!! 90

j) Change Wallet Passphrase: ./Titancoind walletpassphrasechange "oldpassphrase"  "newpassphrase"

   example: ./Titancoind walletpassphrase thehard*&password!! thenew%^password

