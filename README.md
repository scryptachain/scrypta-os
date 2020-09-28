# Main repository for Scrypta on Raspberry PI4

<p><a href="https://camo.githubusercontent.com/4e892209b4b1e2d1a773ec97e544a92f068a6f0b/68747470733a2f2f6d69726f2e6d656469756d2e636f6d2f6d61782f333136382f312a31674778414b57714b5135577a635170755f766932412e6a706567" target="_blank" rel="noopener noreferrer"><img style="display: block; margin-left: auto; margin-right: auto;" src="https://camo.githubusercontent.com/4e892209b4b1e2d1a773ec97e544a92f068a6f0b/68747470733a2f2f6d69726f2e6d656469756d2e636f6d2f6d61782f333136382f312a31674778414b57714b5135577a635170755f766932412e6a706567" alt="" data-canonical-src="https://miro.medium.com/max/3168/1*1gGxAKWqKQ5WzcQpu_vi2A.jpeg" /></a></p>

<p style="text-align: center;">&nbsp;<a title="English &mdash; Scrypta Wiki" href="https://en.scrypta.wiki/scrypta-full-node/" target="_blank" rel="nofollow noopener"><strong>Wiki English</strong></a>&nbsp;&middot; &middot; &middot;&nbsp;<a title="Italiano &mdash; Scrypta Wiki" href="https://it.scrypta.wiki/scrypta-full-node/" target="_blank" rel="nofollow noopener"><strong>Wiki italiano</strong></a></p>

## List of complete commands to manually compile and install all libraries and dependencies for your Scrypta wallet on Raspberry PI4

Following you will find the complete workaround with all commands to manually compile and install all libraries and dependencies for your Scrypta wallet on Raspberry PI4.
Alternatively you can follow the guide for the installation of the Scrypta OS image file for your Raspberry PI4
https://github.com/scryptachain/scrypta-os/blob/master/imagefile_guide.md


For a step-by-step manual installation, proceed opening terminal and give the following commands.

```
sudo apt-get update && sudo apt-get upgrade 
```
After this command, the Raspi will ask for reboot. Proceed rebooting your Raspi.

```
sudo apt-get install -y pkg-config
sudo apt-get install -y software-properties-common python-software-properties
```

```
wget https://raw.githubusercontent.com/scryptachain/scrypta-os/master/add-apt-repository.sh
sudo mv add-apt-repository.sh /usr/bin/add-apt-repository
sudo chmod +x /usr/bin/add-apt-repository
sudo add-apt-repository -y ppa:bitcoin/bitcoin
```

```
sudo apt-get -y install build-essential autoconf automake libtool libboost-all-dev libboost-program-options-dev libssl1.0-dev
sudo apt-get -y install libleveldb-dev libgmp-dev libgmp3-dev libcurl4-openssl-dev libcrypto++-dev libqrencode-dev
sudo apt-get -y install libminiupnpc-dev autogen libtool libevent-dev libprotobuf-dev protobuf-compiler
sudo apt-get -y install curl g++ git git-core faketime bsdmainutils mingw-w64 g++-mingw-w64 nsis zip ca-certificates python
sudo apt-get -y install libgmp-dev libssl-dev libcurl4-openssl-dev
sudo apt-get -y install qtbase5-dev libqt5gui5 libqt5core5a libqt5dbus5 qttools5-dev qttools5-dev-tools libzmq3-dev
```

```
wget http://download.oracle.com/berkeley-db/db-4.8.30.NC.tar.gz
tar -xzvf db-4.8.30.NC.tar.gz
cd db-4.8.30.NC/build_unix
../dist/configure --enable-cxx
sudo make -j2
sudo make install
```

```
export BDB_INCLUDE_PATH="/usr/local/BerkeleyDB.4.8/include"
export BDB_LIB_PATH="/usr/local/BerkeleyDB.4.8/lib"
sudo ln -s /usr/local/BerkeleyDB.4.8/lib/libdb-4.8.so /usr/lib/libdb-4.8.so
sudo ln -s /usr/local/BerkeleyDB.4.8/lib/libdb_cxx-4.8.so /usr/lib/libdb_cxx-4.8.so
cd
```
Reboot again your Raspi
```
git clone https://github.com/scryptachain/scrypta
cd scrypta
sudo chmod +x share/genbuild.sh
sudo chmod +x autogen.sh
sudo chmod 755 src/leveldb/build_detect_platform
```
```
./autogen.sh
sudo ./configure --with-gui=qt5 --with-libressl --disable-sse2 CPPFLAGS="-I/usr/local/BerkeleyDB.4.8/include -O2" LDFLAGS="-L/usr/local/BerkeleyDB.4.8/lib"
sudo make -j4
```
