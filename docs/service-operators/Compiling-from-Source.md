# **Compiling from Source**

The instructions for in the [README.md](https://github.com/furiousteam/BLOC/blob/master/README.md) of [BLOC](https://bloc.money) cover common platforms for compiling from source, it would be impractical to include them all. So this page exists to capture the other platforms/distros that BLOC has been successfully compiled on. Please add to it if your environment is not covered, thanks!

## **Source code**

* Download [BLOC Source Code](https://github.com/furiousteam/BLOC.git) from GitHub

## **CentOS 7**

[BLOC](https://github.com/furiousteam/BLOC.git) build on CENTOS 7 or RHEL 7 with DEVTOOLS 7

```
$ sudo yum groupinstall 'Development Tools'
```
OR
```
$ sudo yum groups mark install 'Development Tools'
$ sudo yum update 
```

### Install devtools 7

```
# 1. Install a package with repository for your system:
# On CentOS, install package centos-release-scl available in CentOS repository:
$ sudo yum install centos-release-scl # On RHEL, enable RHSCL repository for you system:
$ sudo yum-config-manager --enable rhel-server-rhscl-7-rpms # 2. Install the collection:
$ sudo yum install devtoolset-7# 3. Start using software collections:
$ scl enable devtoolset-7 bash
```

### Requirements

```
$ sudo yum install git wget automake make cmake cmake3  -y

$ sudo yum install gflags-devel snappy-devel zlib-devel bzip2-devel gcc gcc-c++ libstdc++-devel libstdc++-static -y
$ sudo yum install python-devel -y
```

### Install boost 1.62 or above version 

Version 1.62 successfully build with gcc 7  

```
$ wget https://sourceforge.net/projects/boost/files/boost/1.62.0/boost_1_62_0.tar.gz
$ tar xvf boost_1_62_0.tar.gz
$ cd boost_1_62_0
$ scl enable devtoolset-7 bash
$ ./bootstrap.sh
$ ./b2
```

### Get BLOC source and Compile

```
$ cd ..

$ git clone https://github.com/furiousteam/BLOC.git
$ cd BLOC
$ mkdir build && cd build
$ scl enable devtoolset-7 bash
$ export CXXFLAGS="-std=gnu++11"
$ cmake3 .. -DBOOST_ROOT=~/boost_1_62_0
$ make
```