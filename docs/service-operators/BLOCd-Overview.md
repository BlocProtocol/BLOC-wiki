# What is BLOCd

A daemon is a program that runs in the background. The BLOC wallet requires a node (running "BLOCd") to connect to. That process, "BLOCd", is the daemon. It can run on your computer or on a remote computer. Think of a daemon as a service. Its doing stuff in the background so you can do stuff in the foreground.

BLOC Daemon (BLOCd) is responsible for any communication with the network.

* Mining
* Interaction with the blockchain, e.g. blocks relaying, getting info about the block, etc.
* Peer list look up
* Connections look up
* Transaction pool information and relaying

Here's a quick image of `BLOCd MAIN NET` in action:

![BLOCd MAIN NET](../wallets/images/BLOCd/BLOC-MAINNET-3.0.0.1.png)

Here's a quick image of `BLOCd TEST NET` in action:

![BLOCd TEST NET](../wallets/images/BLOCd/BLOC-TESTNET-3.0.0.1.jpg)

## **Source code**

* [Source Code](https://github.com/furiousteam/BLOC.git)

## **BLOCd RPC Clients**

* [Javascript](https://github.com/furiousteam/bloc-rpc): A JavaScript wrapper for the BLOCd daemon RPC interface.
* [NodeJS](https://www.npmjs.com/package/bloc-rpc): This project is designed to make it very easy to interact with various RPC APIs available within the BLOC  Project. This entire project uses Javascript Promises to make things fast, easy, and safe.
* [Go](https://github.com/furiousteam/bloc-rpc-go): A Golang wrapper for the BLOCd RPC API. This project makes it easy to send requests to particular RPC server and returns a clear response without any abrupt termination.
* [PHP](https://github.com/furiousteam/bloc-rpc-php): A PHP wrapper for BLOC's RPC interfaces.

See [Daemon HTTP RPC API](BLOCd-daemon-http-rpc-api.md) and [Daemon JSON RPC API](BLOCd-daemon-json-rpc-api.md) for usage.

## **Downloading**

If you wish to compile **BLOCd** yourself you can download the [source Code](https://github.com/furiousteam/BLOC.git).

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

## Starting BLOCd

Make sure you visit the [BLOCd Command Line Arguments](BLOCd-Daemon-arguments.md) to find how to start BLOCd following different configurations.

## **Synchronizing the Blockchain**

Running `BLOCd` will start the **BLOCd** network daemon, which will connect to the network and begin downloading and verifying the BLOC blockchain.  

Because the blockchain is constantly growing, the file size always increases (the blockchain is currently over 2 GB), and **BLOCd must verify every block**, which is both CPU and disk intensive. An SSD with at least this much free disk space is recommended, unless you plan to use [remote nodes](../BLOC-servic#remote-node-options). 

### Using Checkpoints

You can sync a fresh chain from block 0 much quicker by using checkpoints. Follow [this guide](../API/Using-checkpoints-for-BLOCd.md) to learn more.