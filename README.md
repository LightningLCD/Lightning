# Lightning

PoS Coin

# UNIX BUILD NOTES
====================

To Build Lightning Headless Wallet Daemon.
-----------------

# Firstly ensure your system has all the Required tools in order to build Lightning Correctly with no issue's. Please commit these commands through the Terminal of your choice.


sudo apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils

sudo apt-get install qt5-default qt5-qmake qtbase5-dev-tools qttools5-dev-tools build-essential libboost-dev libboost-system-dev libboost-filesystem-dev libboost-program-options-dev libboost-thread-dev libssl-dev libdb++-dev libminiupnpc-dev 

sudo apt-get install software-properties-common

sudo add-apt-repository ppa:bitcoin/bitcoin

sudo apt-get update

sudo apt-get install libdb4.8-dev libdb4.8++-dev

sudo apt-get install libqrencode-dev



# Now you have all files Required by Lightning's code in order to build the Wallet.



# Now we proceed onto making the Lightning Wallet. Again use your preferred Terminal


git clone https://github.com/LightningLCD/Lightning.git

cd Lightning/src/secp256k1

chmod +x autogen.sh

sudo ./autogen.sh

sudo ./configure

sudo make && make install

cd

cd Lightning/src/leveldb

sudo sh build_detect_platform build_config.mk .

cd

cd Lightning/src

sudo make -f makefile.unix

strip lightningd

LD_LIBRARY_PATH=/usr/local/lib

export LD_LIBRARY_PATH



# You now have lightningd Ready to run and connect to the network.


# To Build Lightning Qt Wallet
------------------

# Firstly ensure your system has all the Required tools in order to build Lightning Correctly with no issue's. Please commit these commands through the Terminal of your choice.


sudo apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils

sudo apt-get install qt5-default qt5-qmake qtbase5-dev-tools qttools5-dev-tools build-essential libboost-dev libboost-system-dev libboost-filesystem-dev libboost-program-options-dev libboost-thread-dev libssl-dev libdb++-dev libminiupnpc-dev 

sudo apt-get install software-properties-common
sudo add-apt-repository ppa:bitcoin/bitcoin
sudo apt-get update
sudo apt-get install libdb4.8-dev libdb4.8++-dev

sudo apt-get install libqrencode-dev



# Now you have all files Required by Lightning's code in order to build the Wallet.



# Now we proceed onto making the Lightning Wallet. Again use your preferred Terminal



git clone https://github.com/LightningLCD/Lightning.git

cd Lightning/src/secp256k1

chmod +x autogen.sh

sudo ./autogen.sh

sudo ./configure

sudo make && make install

cd

cd Lightning/src/leveldb

sudo sh build_detect_platform build_config.mk .

cd

cd Lightning

sudo qmake Lightning.pro

sudo make -jnumofcoreshere