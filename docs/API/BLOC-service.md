# What is BLOC-Service

This section describes **BLOC** integration process into your service with **BLOC e-commerce** solution called **bloc-service**.
**bloc-service** is the substitue of old **walletd** a HTTP server which provides JSON 2.0 RPC interface for **BLOC** payment operations and address management. **bloc-service** allows you to accept incoming payments, generate an address for each user via a robust API and much more features explained as follow.

## **Getting ready**

To start integration process you should follow this easy steps:

## **Downloading**

If you wish to compile **bloc-service** and **BLOCd** yourself you can download the [Source Code](https://github.com/furiousteam/BLOC.git)

Binary distributions can be found: [here](https://github.com/furiousteam/BLOC/releases/latest).

Select the appropriate file for the target platform (Windows, Mac, Linux).

Binaries are provided in `.zip` format, while source code is provided in `.zip` and `.tar.gz` format.

## **Installing**

### Installing on Windows

Extract the *.zip* file (`BLOC-...-windows.zip`).

### Installing on Mac

Extract the *.zip* file:

```bash
unzip BLOC-...-mac.zip
```

### Installing on Linux

Extract the *.zip* file:

```bash
unzip BLOC-...-linux.zip
```

## **Synchronizing the Blockchain**

Here's a quick image of `BLOCd MAIN NET` in action:

![BLOCd MAIN NET](images/BLOCd/BLOC-MAINNET-3.0.0.1.png)

Here's a quick image of `BLOCd TEST NET` in action:

![BLOCd TEST NET](images/BLOCd/BLOC-TESTNET-3.0.0.1.jpg)

Running `BLOCd` will start the **BLOCd** network daemon, which will connect to the network and begin downloading and verifying the BLOC blockchain.  

Because the blockchain is constantly growing, the file size always increases (the blockchain is currently over 2 GB), and **BLOCd must verify every block**, which is both CPU and disk intensive. An SSD with at least this much free disk space is recommended, unless you plan to use [remote nodes](../Using-remote-nodes). 

### Using Checkpoints

You can sync a fresh chain from block 0 much quicker by using checkpoints. Follow [this guide](../Using-checkpoints) to learn more.

### Windows

Run the `BLOCd.exe` executable extracted from the Windows binary zip:

### Mac / Linux

Run the `BLOCd` binary extracted from the `.zip` download:

```bash
./BLOCd
```

## **Ready to work with bloc-service**

Once **BLOCd** has been successfully synchronised we are ready to operate with **bloc-service**

The following exemples are made using a Linux system but the concept is the same for all the OS supported by the **bloc-service**.

**bloc-service Screenshot**

![--help](images/bloc-service/help.png)


## **Command line options:**

This is the command line options available since the bloc-service v3.0

```
  Common Options:
  -c [ --config ] arg                configuration file
  -h [ --help ]                      produce this help message and exit
  -v [ --version ]                   Output version information
  --bind-address arg (=127.0.0.1)    payment service bind address
  --bind-port arg (=8070)            payment service bind port
  --rpc-password arg                 Specify the password to access the rpc 
                                     server.
  --rpc-legacy-security              Enable legacy mode (no password for RPC). 
                                     WARNING: INSECURE. USE ONLY AS A LAST 
                                     RESORT.
  -w [ --container-file ] arg        container file
  -p [ --container-password ] arg    container password
  -g [ --generate-container ]        generate new container file with one 
                                     wallet and exit
  --view-key arg                     generate a container with this secret key 
                                     view
  --spend-key arg                    generate a container with this secret 
                                     spend key
  --mnemonic-seed arg                generate a container with this mnemonic 
                                     seed
  -d [ --daemon ]                    run as daemon in Unix or as service in 
                                     Windows
  -l [ --log-file ] arg              log file
  --server-root arg                  server root. The service will use it as 
                                     working directory. Don't set it if don't 
                                     want to change it
  --log-level arg                    log level
  --SYNC_FROM_ZERO                   sync from timestamp 0
  --address                          print wallet addresses and exit
  --enable-cors arg                  Adds header 'Access-Control-Allow-Origin' 
                                     to walletd's RPC responses. Uses the value
                                     as domain. Use * for all.
  --scan-height arg                  The height to begin scanning a wallet from
```

## **Remote Node options:**

```
Remote Node Options:
  --daemon-address arg (=localhost)  daemon address
  --daemon-port arg (=2086)          daemon port
```

### --help

Display the help message and configuration settings.

#### Exemple

```
./bloc-service --help
```

**Expected results**

![--help](images/bloc-service/help.png)


### --config arg (=myconf.conf)

Specify a configuration file to start bloc-service. This is much more simple to use if you have a particular configuration and you do not want to type all the arguments while launching bloc-service.

#### Exemple

```
./bloc-service --config=myconf.conf
```

### --version

Display the current version of bloc-service

#### Exemple

```
./bloc-service --version
```

**Expected results**

![--help](images/bloc-service/--version.png)


## **Command line arguments**

All the following command line options and arguments must be used when start **bloc-service**

* You can use them directly in the command line and provided examples
* Or you can use them in the config file which is the best option

### --bind-address arg (=127.0.0.1)**

* Interface for bloc-service RPC
* Started by default on 127.0.0.1 when running either you specified it `./bloc-service --config=myconf.conf`
* If you want to use local only : 127.0.0.1
* if you want to open to public : 0.0.0.0d)
* More details about the [JSON bloc-service API](../wallet-rpc-api.md)

#### Exemple

```
./bloc-service --bind-address=127.0.0.1 --container-file=mycontainer --container-password=mypassword --rpc-password=RPCpassword
```

### --bind-port arg (=8070)

* Port for bloc-service RPC
* Started by default on 8070 when running either you specified it `./bloc-service --config=myconf.conf`
* You can change the port here for ex 8071
* More details about the [JSON bloc-service API](../wallet-rpc-api.md)

#### Exemple

```
./bloc-service --bind-port=8071 --container-file=mycontainer --container-password=mypassword --rpc-password=RPCpassword
```

### --rpc-password

Setup the rpc password to connect to bloc-service

#### Exemple

```
./bloc-service --container-file=mycontainer --container-password=mypassword --rpc-password=RPCpassword
```

### --rpc-legacy-security arg (=8070)

* Enable legacy mode (no password for RPC). 
* **WARNING: INSECURE. USE ONLY AS A LAST RESORT.**

#### Exemple

```
./bloc-service --container-file=mycontainer --container-password=mypassword --rpc-legacy-security
```

### --container-file=(arg)

* Container file is the only file that stores all data required to run your bloc-service. It contains user addresses and private keys required to operate them.
* This function works only coupled with `--container-password` and `--generate-container`

### --container-password=(arg)

* Container password file is the only file that stores all data required to run your bloc-service. It contains user addresses and private keys required to operate them.
* This function works only coupled with `--container-file` and `--generate-container`

### --generate-container

* Generate a new container file with one wallet and exit.
* This function works only coupled with `--container-file` and `--container-password`

#### Exemple

```
./bloc-service  --container-file=mycontainer --container-password=mypassword --generate-container 
```

**Expected results**

![generate-container](images/bloc-service/generate-container.png)


## **Create .CONF file**

* Create a txt file with your favorite text editor and open it.
* Check all your required parameters and enter them like in this exemple
* You need to type the arguments without the '--'

**Expected results**

![conf](images/bloc-service/myconf.png)

#### Example

```
container-file = mycontainer
container-password = mypassword
daemon-address = 127.0.0.1
daemon-port = 2086
bind-port = 8070
bind-address = 127.0.0.1
rpc-password = RPCpassword
```

[Download Example](images/bloc-service/myconf.conf)

* Place this file next to BLOCd
* Save it under the name `myconf.conf`

**Expected results**

![conf](images/bloc-service/CONF2.png)

**Notes**

* Config file path is relative to current working directory, not server root.
* Options `container-file` and `container-password` should ALWAYS be set (in either command line or config file mode).
* Options `container-file` and `log-file` options are relative to `server-root`. `server-root` default is the current working directory.


## **Generate a new wallet**

To start using **bloc-service** you must first generate a container.
Container file is the only file that stores all data required to run your service. It contains user addresses and private keys required to operate them.
**Make sure to backup this file regularly**.

To generate a new container you should run the following command:

```
./bloc-service --container-file=mycontainer --container-password=mypassword --generate-container 
```

* `mycontainer` is the container file name and a path to it (relative or absolute); path is optional in this argument, specifying only a container name will result in new file located in the same folder as **bloc-service** 
* `mypassword` is a secret password for the new wallet & container file.
* `generate-container` option tells **bloc-service** to generate container file and exit.

**Expected results**

![generate-container](images/bloc-service/generate-container.png)

*Note: if `mycontainer` exists **bloc-service** will show you the notification and will ask you to provide a different name*

If the operation was successful you will get a corresponding message with your new **BLOC** address. At the same time **bloc-service** will save your container on the local disk (in the same folder where **bloc-service** is located and shut down.


## **Start bloc-service**

* To start **bloc-service** RPC wallet you can use both command line and config file. Config file allows you to configure your settings only once and use `--config` option further.
* The command below launches **bloc-service** RPC Wallet with a specific config file:

```
./bloc-service --config=myconf.conf
```

* You may specify BLOC config directly through console arguments. Here is the same config file as above in console: 

```
./bloc-service --container-file=mycontainer --container-password=mypassword --daemon-address=127.0.0.1 --daemon-port=2086 --bind-address=127.0.0.1 --bind-port=8070 --rpc-password=RPCpassword 
```

**Expected results**

Start with command line:

![start bloc-service](images/bloc-service/start.png)

Start with myconf.conf:

![start bloc-service](images/bloc-service/start-conf.png)

## **Restore a existing BLOC wallet with bloc-service**##

We have different option to recover a wallet using **bloc-service**

### Using a old Walletd container file

If you were using Walletd that come with the previous version of BLOC, the previous container file is compatible with the new version. This is the step to follow:

* Copy the your previous configuration file `yourfile.conf` and copy the acual container file `mycontainer`
* Paste this 2 files next to the new `bloc-service` and `BLOCd`
* Open `yourfile.conf` 
* Make sure you remove this line `testnet = no` we are not using this field anymore
* Edit like this:

```
container-file = mycontainer
container-password = mypassword
daemon-port = 2086
bind-port = 8070
bind-address = 127.0.0.1
rpc-password = RPCpassword
```
* Save the file
* Start `bloc-service` using this configuration file
* ```./bloc-service --config=myconf.conf```
* Please wait until the synchronisation is complete
* Your wallet is ready to be used with the **bloc-service** RPC API.

**Expected results**

![start bloc-service](images/bloc-service/restore-old-wallet-file.png)


### Using your private spend key and view key

If you already have a [BLOC Wallet](../wallet/Making-a-Wallet.md) you must know your **private spend key** and your **private view key** to restore your wallet using **bloc-service**. To find how to generate view your private key using your favorite BLOC Wallet software please refer to the . [Wallet manuals available](../wallet/Making-a-Wallet.md).

* Create a txt file with your favorite text editor and open it.
* Check all your required parameters and enter them like in this exemple
* You need to type the arguments without the '--'
* Place this file next to BLOCd
* Save it under the name `myconf.conf`

```
container-file = mycontainer
container-password = mypassword
daemon-port = 2086
bind-port = 8070
bind-address = 127.0.0.1
rpc-password = RPCpassword
```
* Save the file

#### Generate a new container file

Generate a new container file with the following `--view-key` and `--spend-key` commands:

```
Enter your details:
./bloc-service --container-file=mycontainer --container-password=mypassword --view-key=myviewkey --spend-key=myspendkey --generate-container

Example:
./bloc-service --container-file=mycontainer --container-password=mypassword --view-key=e82ebf49b74fccd754e39ac3ca6fabca35277b012dfce0cf8921c216396b3108 --spend-key=cda47a19e5d433060ab79c885817cd20fc394dc7043ac875678a3698804ede01 --generate-container
```

**Expected results**

![start bloc-service](images/bloc-service/restore-using-private-keys.png)


* Start `bloc-service` using your configuration file

```
./bloc-service --config=myconf.conf
```

* Your wallet is now loaded
* Please wait until the synchronisation is complete

**Expected results**

![wallet loading after restore private key](images/bloc-service/wallet-loading-after-restore-private-key.png)


* Your wallet is ready to be used with the **bloc-service** RPC API.

**Expected results**

![wallet ready after restore private key](images/bloc-service/wallet-ready-after-restore-prviate-keys.png)


### Using your mnemonic-seed

If you already have a [BLOC Wallet](../wallet/Making-a-Wallet.md) created after the launch of the **BLOC V3.0** then you you must know your **mnemonic-seed** to restore your wallet using **bloc-service**. To find how to generate view your mnemonic-seed using your favorite **BLOC** Wallet software please refer to the [Wallet manuals available](../wallet/Making-a-Wallet.md).

* Create a txt file with your favorite text editor and open it.
* Check all your required parameters and enter them like in this exemple
* You need to type the arguments without the '--'
* Place this file next to BLOCd
* Save it under the name `mycontainer.conf`

```
container-file = mycontainer
container-password = mypassword
daemon-port = 2086
bind-port = 8070
bind-address = 0.0.0.0
rpc-password = RPCpassword
```
* Save the file

#### Generate a new container file

Generate a new container file with the following `--mnemonic-seed` commands:

```
Enter your details:
./bloc-service --container-file=mycontainer --container-password=mypassword --mnemonic-seed="your-mnemonic-seed" --generate-container

Example:
./bloc-service --container-file=mycontainer --container-password=mypassword --mnemonic-seed="jazz border dude orphans worry absorb slackens public drinks bovine evenings hurried roped jaws drinks snug directed pirate behind zero null cuisine agreed alchemy directed" --generate-container
```

**Expected results**

![start bloc-service](images/bloc-service/restore-using-mnemonic-seed.png)


* Start `bloc-service` using your configuration file

```
./bloc-service --config=myconf.conf
```
* Your wallet is now loaded
* Please wait until the synchronisation is complete

**Expected results**

![wallet ready for bloc-service](images/bloc-service/restore-using-mnemonic-seed-loading.png)

* Your wallet is ready to be used with the **bloc-service** RPC API.

**Expected results**

![wallet ready for bloc-service](images/bloc-service/restore-using-mnemonic-seed-loaded-ok.png)


### Load wallet and exit

Start `bloc-service` to display the 1st wallet address in the container and exit

```
./bloc-service --container-file=mycontainer --container-password=mypassword --rpc-password=RPCpassword --address
```

**Expected results**

![wallet ready for bloc-service](images/bloc-service/load-wallet-and-exit.png)





__________________________________________________________________________________________________






A daemon is a program that runs in the background. The BLOC wallet requires a node (running "BLOCd") to connect to. That process, "BLOCd", is the daemon. It can run on your computer or on a remote computer. Think of a daemon as a service. Its doing stuff in the background so you can do stuff in the foreground.

BLOC Daemon (BLOCd) is responsible for any communication with the network.

* Mining
* Interaction with the blockchain, e.g. blocks relaying, getting info about the block, etc.
* Peer list look up
* Connections look up
* Transaction pool information and relaying

## Source code

* [Source Code](https://github.com/furiousteam/BLOC.git)

## Errors

* Make sure you check the [RPC Errors conditions](../API/rpc-api-error-conditions.md).

## BLOCd RPC Clients

* [Javascript](https://github.com/furiousteam/bloc-rpc): A JavaScript wrapper for the BLOCd daemon RPC interface.
* [NodeJS](https://www.npmjs.com/package/bloc-rpc): This project is designed to make it very easy to interact with various RPC APIs available within the BLOC  Project. This entire project uses Javascript Promises to make things fast, easy, and safe.
* [Go](https://github.com/furiousteam/bloc-rpc-go): A Golang wrapper for the BLOC RPC API. This project makes it easy to send requests to particular RPC server and returns a clear response without any abrupt termination.
* [PHP](https://github.com/furiousteam/bloc-rpc-php): A PHP wrapper for BLOC's RPC interfaces.

See [Daemon HTTP RPC API](daemon-http-rpc-api.md) and [Daemon JSON RPC API](daemon-json-rpc-api.md) for usage.


# BLOCd Command line options

The following exemples are made using a Linux system but the concept is the same for all the OS supported by the BLOCd.

**BLOCd Screenshot**

![--help](images/BLOCd/command-line-options/BLOCd.png)


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

![--help](images/BLOCd/command-line-options/CONF.png)


## Create .CONF file

* Create a txt file with your favorite text editor and open it.
* Check all your required parameters and enter them like in this exemple
* You need to type the arguments without the '--'
* Place this file next to BLOCd

#### Example

```
enable-cors=*
fee-address=abLoc8oL14r8DUdzXBPwN8LPMSBJfS3BaFG96gQPhFWRNBw2g6AHpFoJyuYP7h83cPEcLYxKAgMs9L27S3tBNEHaMkR6JhDsLt5
fee-amount=5
rpc-bind-ip=0.0.0.0
enable_blockexplorer=yes
```
[Download Example](images/BLOCd/command-line-options/BLOC.conf)

**Expected results**

![--help](images/BLOCd/command-line-options/CONF2.png)


## Command line options and settings options

![--help](images/BLOCd/command-line-options/help.png)

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


### --testnet

* Used to deploy test nets. Checkpoints and hardcoded seeds are ignored, network id is changed. Use it with --data-dir flag. The wallet must be launched with --testnet flag.
* We are not using this function since BLOC has a dedicated [TESTNET](../API/BLOC-TESTNET.md)


### --enable-cors arg

* Adds header 'Access-Control-Allow-Origin' to the daemon's RPC responses.
* Uses the value as domain
* Use * for all

#### Exemple

```
./BLOCd --enable-cors=*
./BLOCd --enable-cors=yourdomain.com
```

**Expected results**

![--help](images/BLOCd/command-line-options/enable-cors.png)

**Response Headers**
```
HTTP/1.1 200 OK
Access-Control-Allow-Origin: *
Content-Length: 123
Content-Type: application/json
Server: CryptoNote-based HTTP server

or

HTTP/1.1 200 OK
Access-Control-Allow-Origin: yourdomain.com
Content-Length: 123
Content-Type: application/json
Server: CryptoNote-based HTTP server
```

### --enable_blockexplorer

* To enable block explorer API access (like for getblocks, gettransactionpool, etc.)

#### Exemple

```
./BLOCd --enable_blockexplorer
```

**Expected results**

![--help](images/BLOCd/command-line-options/enable-bloc-explorer.png)


### --print-genesis-tx

* Prints genesis' block tx hex to insert it to config and exits
* Use this method if you like to fork BLOC to generate a new 'GENESIS_COINBASE_TX_HEX' and create your own cryptocurrency
* More details can be found in the CryptoNoteConfig.h

#### Exemple

```
./BLOCd --print-genesis-tx
```

**Expected results**

![--help](images/BLOCd/command-line-options/print-genesis-tx.png)


### --genesis-block-reward-address arg

* Premine wallet address
* Use this method combined with the previous one if you like to generate a premine wallet into your new created cryptocurrency
* More details can be found in the CryptoNoteConfig.h

#### Exemple

```
./BLOCd --print-genesis-tx --genesis-block-reward-address=abLoc9fgn3Lcirw7U6nthwTBgwoffUJajEHr3vtSb9nPPL91XWG1Brt5TNCKRZojEbCGhMdSSjpCQfiMnfGEzMQbfs25N6HC6JR
```

**Expected results**

![--help](images/BLOCd/command-line-options/genesis-block-reward-address.png)


### load-checkpoints arg (=default) <default|filename>

* Use builtin default checkpoints
* Or use checkpoint csv file for faster initial blockchain sync

#### Exemple

```
./BLOCd --load-checkpoints=checkpoints.csv
```

**Expected results**

[Cick here](../using-check-points-with-BLOCd.md).


### --fee-address arg

* This is a new feature implemented in BLOC v3.0
* Read more about [Nodes Fees](../wallets/Using-remote-nodes.md).
* Sets fee address for light wallets that use the daemon
* Make sure you combine this argument with --fee-amount

#### Exemple

```
./BLOCd --fee-address=abLoc9fgn3Lcirw7U6nthwTBgwoffUJajEHr3vtSb9nPPL91XWG1Brt5TNCKRZojEbCGhMdSSjpCQfiMnfGEzMQbfs25N6HC6JR
```


### --fee-amount arg (=0)

* This is a new feature implemented in BLOC v3.0
* Read more about [Nodes Fees](../wallets/Using-remote-nodes.md).
* Sets fee amount for light wallets that use the daemon
* Make sure you combine this argument with --fee-address
* Remember we are using Atomic Units
* --fee-amount=1 means 0.0001 BLOC fees will be sent to the --fee-address specified
* --fee-amount=1000 means 1 BLOC fees will be sent to the -fee-address specified

#### Exemple

```
./BLOCd --fee-address=abLoc9fgn3Lcirw7U6nthwTBgwoffUJajEHr3vtSb9nPPL91XWG1Brt5TNCKRZojEbCGhMdSSjpCQfiMnfGEzMQbfs25N6HC6JR --fee-amount=1
```

**Expected results**

![--help](images/BLOCd/command-line-options/fee-amount.png)


### --rpc-bind-ip arg (=127.0.0.1)

* Interface for RPC service
* Started by default on 127.0.0.1 when running ./BLOCd
* If you want to use local only : 127.0.0.1
* if you want to open to public : 0.0.0.0
* More details about the [HTTP RPC API](../daemon-http-rpc-api.md)
* More details about the [JSON RPC API](../daemon-json-rpc-api.md)

#### Exemple

```
(Public)
./BLOCd --rpc-bind-ip=0.0.0.0

(Local)
./BLOCd --rpc-bind-ip=127.0.0.1
```

**Expected results**

![--help](images/BLOCd/command-line-options/rpc-bind-ip.png)


### --rpc-bind-port arg (=2086)

* Port for the RPC service
* Started by default on 2086 when running ./BLOCd
* You can change this port here
* More details about the [HTTP RPC API](../daemon-http-rpc-api.md)
* More details about the [JSON RPC API](../daemon-json-rpc-api.md)

#### Exemple

```
./BLOCd --rpc-bind-port=10000
```

**Expected results**

![--help](images/BLOCd/command-line-options/rpc-bind-port.png)


### --p2p-bind-ip arg (=0.0.0.0) 

* Interface for p2p network protocol
* Started by default on 0.0.0.0 when running ./BLOCd
* If you want to use local only : 127.0.0.1
* if you want to open to public : 0.0.0.0

#### Exemple

```
(Public)
./BLOCd --p2p-bind-ip=0.0.0.0

(Local)
./BLOCd --p2p-bind-ip=127.0.0.1
```
**Expected results**

![--help](images/BLOCd/command-line-options/p2p-bind-ip.png)


### --p2p-bind-port arg (=2082)

* Port for p2p network protocol
* Started by default on 2082 when running ./BLOCd
* You can change this port here

#### Exemple

```
./BLOCd --p2p-bind-port=3000
```

**Expected results**

![--help](images/BLOCd/command-line-options/p2p-bind-port.png)


### --p2p-external-port arg (=0)

* External port for p2p network protocol (if port forwarding used with NAT)

#### Exemple

```
./BLOCd --p2p-external-port=5000
```

**Expected results**

![--help](images/BLOCd/command-line-options/p2p-external-port.png)


### --allow-local-ip

* Allow local ip add to peer list, mostly in debug purposes

#### Exemple

```
./BLOCd --allow-local-ip
```

**Expected results**

![--help](images/BLOCd/command-line-options/allow-local-ip.png)


### --add-peer arg

* Manually add peer to local peerlist

#### Exemple

```
./BLOCd --add-peer=PEER.IP.ADDRESS
```


### --add-priority-node arg

* Specify list of peers to connect to and attempt to keep the connection open

#### Exemple

```
./BLOCd --add-priority-node=NODE.IP.ADDRESS
```


### --add-exclusive-node arg

* Specify list of peers to connect to only.
* If this option is given the options add-priority-node and seed-node are ignored

#### Exemple

```
./BLOCd --add-exclusive-node=NODE.IP.ADDRESS
```


### --seed-node arg

* Connect to a node to retrieve peer addresses, and disconnect

#### Exemple

```
./BLOCd --seed-node=NODE.IP.ADDRESS
```


### --hide-my-port

* Do not announce yourself as peerlist candidate

#### Exemple

```
./BLOCd --hide-my-port
```


### --db-threads arg (=2)

* Number of background threads used for compaction and flush
* Default is 2

#### Exemple

```
./BLOCd --db-threads=2
```


### --db-max-open-files arg (=100)

* Number of open files that can be used by the DB
* Default is 100

#### Exemple

```
./BLOCd --db-max-open-files=100
```


### --db-write-buffer-size arg (=256)

* Size of data base write buffer in megabytes
* Default is 256

#### Exemple

```
./BLOCd --db-write-buffer-size=256
```


### --db-read-cache-size arg (=10)

* Size of data base read cache in megabytes
* Default is 10

#### Exemple

```
./BLOCd --db-read-cache-size=10
```

## BLOC-DEVELOPER

Make sure you visit the dedicated website [BLOC-DEVELOPER.com](https://bloc-developer.com) to find out more details and test your application.

If anything is missing or seems incorrect, please check the [GitHub issues](https://github.com/furiousteam/BLOC-wiki/issues) for existing known issues or [create a new one](https://github.com/furiousteam/BLOC-wiki/issues/new).