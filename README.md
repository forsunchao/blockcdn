# blockcdn
blockcdn

0.pre install
sudo apt-get install automake
sudo apt-get install build-essential libtool

1.install go
wget https://storage.googleapis.com/golang/go1.9.1.linux-amd64.tar.gz
sudo tar -C /usr/local -zxvf go1.9.1.linux-amd64.tar.gz
sudo mkdir -p ~/go/src
echo "export GOPATH=$HOME/go" >> ~/.bashrc
echo "export PATH=$PATH:$GOPATH/bin:/usr/local/go/bin" >> ~/.bashrc
source ~/.bashrc
go version

2.install libevent
wget https://github.com/forsunchao/blockcdn/blob/master/libevent-release-2.1.8-stable.zip
unzip libevent-release-2.1.8-stable.zip
cd libevent-release-2.1.8-stable
./autogen.sh
./configure --prefix=/usr
make
sudo make install
ls -al /usr/lib | grep libevent

3.install protobuf
sudo apt-get install autoconf automake libtool curl make g++ unzip
sudo apt-get install libssl-dev
wget https://github.com/forsunchao/blockcdn/blob/master/protobuf-master.zip
unzip protobuf-master.zip
cd protobuf-master
./autogen.sh
./configure
make
make check
sudo make install
sudo ldconfig # refresh shared library cache
protoc --version

4.install M_BerryMiner_ubuntu_v1_0
wget https://github.com/forsunchao/blockcdn/blob/master/M_BerryMiner_ubuntu_v1_0.tar.gz
tar -xvf M_BerryMiner_ubuntu_v1_0.tar.gz 






