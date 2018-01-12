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
wget https://github.com/libevent/libevent/releases/download/release-2.1.8-stable/libevent-2.1.8-stable.tar.gz
tar -zxvf libevent-release-2.1.8-stable
cd libevent-release-2.1.8-stable
./autogen.sh
./configure --prefix=/usr
make
sudo make install
ls -al /usr/lib | grep libevent

3.install protobuf
sudo apt-get install autoconf automake libtool curl make g++ unzip
sudo apt-get install libssl-dev
wget https://github.com/google/protobuf/archive/master.zip
mv master.zip protobuf.zip
unzip protobuf.zip
cd protobuf
./autogen.sh
./configure
make
make check
sudo make install
sudo ldconfig # refresh shared library cache
protoc --version

4.install M_BerryMiner_ubuntu_v1_0
wget 






