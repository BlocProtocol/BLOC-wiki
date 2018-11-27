# **What is BLOC-Service**

**BLOC-service RPC Wallet** is a HTTP server which provides JSON 2.0 RPC interface for [BLOC](https://bloc.money) payment operations and address management designed to manage a user's account while operating together with a [BLOCd Node Daemon](../service-operators/BLOCd-Overview.md).

BLOC-service RPC Wallet allows you to accept incoming payments, generate an address for each user via [BLOC-service Wallet JSON RPC API](../wallets/bloc-service-json-api.md) and much more.

Make sure you visit the [BLOC-service command line arguments](../wallets/bloc-service-command-line.md) to find out how to start BLOC-service with a customized configuration depending your needs.

If you are looking to integrate BLOC payment and process transactions into your website or application, **BLOC-service** is what you need.

## **Screenshot**

Here's a quick image of `BLOC-service` in action:

![BLOCd MAIN NET](images/BLOCd-MAIN-NET-v3.0.1.png)

## **Source code**

* [Source Code](https://github.com/furiousteam/BLOC.git)

## **BLOC-service API**

The [BLOC-DEVELOPER](https://bloc-developer.com) website documents the public [API of BLOC-service](https://bloc-developer.com/api_bloc-service).
You can test your application with your own BLOCd node and view code examples in different programming language.

- How to use the [BLOC-service Wallet JSON RPC API](../wallets/bloc-service-json-api.md)

- How to use the [BLOC-service command line arguments](../wallets/bloc-service-command-line.md)

- Testing tool and documentation for [BLOC-service RPC Wallet JSON RPC API](https://bloc-developer.com/api_bloc-service/json)

- Testing tool and documentation for [BLOC-service command line arguments](https://bloc-developer.com/api_bloc-service/cli_arguments)

## **BLOC-service RPC Clients**

Currently we support the following official client bindings:

* [Javascript](https://github.com/furiousteam/bloc-rpc): A JavaScript wrapper for the BLOC-service RPC interface.
* [NodeJS](https://www.npmjs.com/package/bloc-rpc): This project is designed to make it very easy to interact with various RPC APIs available within the BLOC Project. This entire project uses Javascript Promises to make things fast, easy, and safe.
* [Go](https://github.com/furiousteam/bloc-rpc-go): A Golang wrapper for the BLOC RPC API. This project makes it easy to send requests to particular RPC server and returns a clear response without any abrupt termination.
* [PHP](https://github.com/furiousteam/bloc-rpc-php): A PHP wrapper for BLOC's RPC interfaces.

See [BLOC-service RPC API](bloc-service-json-api.md) for usage.

## **Important guides with BLOC-service**

1. View [this guide](../wallets/bloc-service-command-line.md#using-your-mnemonic-seed) for steps on recovering your wallet with your **mnemonic phrase (25 words)** using BLOC-service.

2. View [this guide](../wallets/bloc-service-command-line.md#using-your-private-spend-key-and-view-key) for steps on recovering your wallet with your **private spend and view keys** using BLOC-service.

## **Downloading**

If you wish to compile **BLOC-service** yourself you can download the [source Code](https://github.com/furiousteam/BLOC.git).

Binary distributions can be found on: [GitHub](https://github.com/furiousteam/BLOC/releases) or [BLOC.MONEY](https://bloc.money/download) .

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

## **Starting BLOC-service**

Make sure you visit the [BLOC-service Command Line Arguments](bloc-service-command-line.md) to find how to start BLOC-service following different configurations.