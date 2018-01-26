# BlockCdn

## 0.pre install

sudo apt install automake

sudo apt install build-essential libtool

## 1.install go

wget https://storage.googleapis.com/golang/go1.9.1.linux-amd64.tar.gz

sudo tar -C /usr/local -zxvf go1.9.1.linux-amd64.tar.gz

sudo mkdir -p ~/go/src

echo "export GOPATH=$HOME/go" >> ~/.bashrc

echo "export PATH=$PATH:$GOPATH/bin:/usr/local/go/bin" >> ~/.bashrc

source ~/.bashrc

go version

## 2.install libevent
git clone https://github.com/forsunchao/blockcdn.git

cd blockcdn

sudo apt install unzip

unzip libevent-release-2.1.8-stable.zip

cd Libevent-release-2.1.8-stable

./autogen.sh

./configure --prefix=/usr

make

sudo make install

ls -al /usr/lib | grep libevent

## 3.install protobuf
cd ..

sudo apt install autoconf automake libtool curl make g++ unzip

sudo apt install libssl-dev

unzip protobuf-master.zip

cd protobuf-master

./autogen.sh

./configure

make # about 20mins

make check # about 16mins

sudo make install

sudo ldconfig # refresh shared library cache

protoc --version

## 4.install M_BerryMiner_ubuntu_v1_0
cd ..

tar -zxvf M_BerryMiner_ubuntu_v1_0.tar.gz

cp -R M_BerryMiner_ubuntu_v1_0 ~/M_BerryMiner_ubuntu_v1_0

cd ..

vim M_BerryMiner_ubuntu_v1_0/server/conf/code.txt

cat M_BerryMiner_ubuntu_v1_0/server/conf/code.txt

cd M_BerryMiner_ubuntu_v1_0/server/

chmod +x bcdn bin/bcdn_server

(./bcdn &)







