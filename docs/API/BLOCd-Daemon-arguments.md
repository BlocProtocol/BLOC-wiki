# BLOCd Command line options

The following exemples are made using a Linux system but the concept is the same for all the OS supported by the BLOCd.

## Command line options:

This is the command line options available since the BLOCd v3.0

```
  --help                                Produce help message
  --version                             Output version information
  --os-version 
  --config-file arg (=BLOC.conf)        Specify configuration file
```

### --help

Display the help message and configuration settings.

#### Exemple

```
./BLOCd --help
```

**Expected results**

![--help](images/BLOCd/command-line-options/help.png)


### --version

Display the version information

#### Exemple

```
./BLOCd --version
```

**Expected results**

![--help](images/BLOCd/command-line-options/version.png)


### --os-version

Display the operating system version information

#### Exemple

```
./BLOCd --os-version
```

**Expected results**

![--help](images/BLOCd/command-line-options/os-version.png)


### --config-file arg (=BLOC.conf)

Specify a configuration file to start BLOCd. This is much more simple to use if you have a particular configuration and you do not want to type all the arguments while launching BLOCd.

#### Exemple

```
./BLOCd --config-file=BLOC.conf
```

**Expected results**

![--help](images/BLOCd/command-line-options/config-file.png)


## Create .CONF file

* Create a txt file with your favorite text editor and open it.
* Check all your required parameters and enter them like in this exemple

#### Exemple

```
rpc-bind-ip=127.0.0.1
```

**Expected results**

![--help](images/BLOCd/conf.png)


## Command line options and settings options

This is the command line options available since the BLOCd v3.0

```
  --data-dir arg (=/home/bloc/.BLOC)  Specify data directory
  --log-file arg
  --log-level arg (=2)
  --no-console                        Disable daemon console commands
  --testnet                           Used to deploy test nets. Checkpoints and
                                      hardcoded seeds are ignored, network id 
                                      is changed. Use it with --data-dir flag. 
                                      The wallet must be launched with 
                                      --testnet flag.
  --enable-cors arg                   Adds header 'Access-Control-Allow-Origin'
                                      to the daemon's RPC responses. Uses the 
                                      value as domain. Use * for all
  --enable_blockexplorer              Enable blockchain explorer RPC
  --print-genesis-tx                  Prints genesis' block tx hex to insert it
                                      to config and exits
  --genesis-block-reward-address arg
  --load-checkpoints arg (=default)   <default|filename> Use builtin default 
                                      checkpoints or checkpoint csv file for 
                                      faster initial blockchain sync
  --fee-address arg                   Sets fee address for light wallets that 
                                      use the daemon.
  --fee-amount arg (=0)               Sets the fee amount for the light wallets
                                      that use the daemon.
  --rpc-bind-ip arg (=127.0.0.1)      Interface for RPC service
  --rpc-bind-port arg (=2086)         Port for RPC service
  --p2p-bind-ip arg (=0.0.0.0)        Interface for p2p network protocol
  --p2p-bind-port arg (=2082)         Port for p2p network protocol
  --p2p-external-port arg (=0)        External port for p2p network protocol 
                                      (if port forwarding used with NAT)
  --allow-local-ip                    Allow local ip add to peer list, mostly 
                                      in debug purposes
  --add-peer arg                      Manually add peer to local peerlist
  --add-priority-node arg             Specify list of peers to connect to and 
                                      attempt to keep the connection open
  --add-exclusive-node arg            Specify list of peers to connect to only.
                                      If this option is given the options 
                                      add-priority-node and seed-node are 
                                      ignored
  --seed-node arg                     Connect to a node to retrieve peer 
                                      addresses, and disconnect
  --hide-my-port                      Do not announce yourself as peerlist 
                                      candidate
  --db-threads arg (=2)               Nuber of background threads used for 
                                      compaction and flush
  --db-max-open-files arg (=100)      Number of open files that can be used by 
                                      the DB
  --db-write-buffer-size arg (=256)   Size of data base write buffer in 
                                      megabytes
  --db-read-cache-size arg (=10)      Size of data base read cache in megabytes
```

### --data-dir arg (=/home/bloc/.BLOC)

* Specify another data directory than the original one set by BLOCd.
* The data directory contains the blockchain files from BLOC.
* Creating a new empty data directory will resynch the blockchain from 0.

#### Exemple

```
./BLOCd --data-dir=/home/bloc/.MYFOLDER
```

**Expected results**

![--help](images/BLOCd/command-line-options/data-dir.png)

**Possible Errors**
```
ERROR   Exception: Directory does not exist: /home/bloc/.MYFOLDER
```
Remark: Make sure you have created the folder you want to use before start BLOCd


### --log-file arg (=test.log)

* Specify another log file than the original one created by BLOCd named (BLOCd.log)
* The specified log file will be created in the same folder where BLOCd was started

#### Exemple

```
./BLOCd --log-file=test.log
```

**Expected results**

![--help](images/BLOCd/command-line-options/log-file.png)

File created next to BLOCd:

![--help](images/BLOCd/command-line-options/testlog.png)


### --log-level arg (=2)

* Specify another log file than the original one created by BLOCd with a level 2
* There is 5 different level. The higher you choose, the more details you get.
* Log level must be 0...5

#### Exemple

```
./BLOCd --log-level=2
```

**Expected results**

![--help](images/BLOCd/command-line-options/log-level.png)

#### TIPS

You can combine --log-file and --log-level together

#### Exemple

```
./BLOCd --log-file=test.log --log-level=2
```
**Expected results**

![--help](images/BLOCd/command-line-options/log-level-combine.png)


### --no-console

* Disable the BLOCd daemon console.
* Can be usefull in case you do not want to allow anyone to run commands through the BLOCd daemon
* As you can see on the screenshot, nothing happen when running the 'help' command

#### Exemple

```
./BLOCd --no-console
```

**Expected results**

![--help](images/BLOCd/command-line-options/no-console.png)
















[BLOC](https://bloc.money) believes that the cryptocurrency era will require a broader development community than just a few leading crypto platforms. For this reason, **BLOC** is providing an open platform that enables companies to build their own products using **BLOC API**. It is very easy to integrate **BLOC** payment into your website/ecommerce/phisical store/application.

**BLOC** has unfolded and advanced a set of key methods to portray universal and integrated access to act as an alternative or replace the current banking system in regards to the expensive and restricted POS contactless terminals.

We also have some specific language bindings to make integration easier. You can find more details on the [Ressources page](../API/Resources.md).

## BLOC-DEVELOPER

Make sure you visit the dedicated website [BLOC-DEVELOPER.com](https://bloc-developer.com) to find out more details and test your application.

If anything is missing or seems incorrect, please check the [GitHub issues](https://github.com/furiousteam/BLOC-wiki/issues) for existing known issues or [create a new one](https://github.com/furiousteam/BLOC-wiki/issues/new).