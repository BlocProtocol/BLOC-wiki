# **What is BLOC-Service**

bloc-service RPC Wallet is a HTTP server which provides [JSON 2.0 RPC](../wallets/bloc-service-json-api.md) interface for [BLOC](https://bloc.money) payment operations and address management designed to manage a user's account while operating together with a [BLOCd Node Daemon](../service-operators/BLOCd-Overview.md). [bloc-service RPC wallet](../wallets/bloc-service-index.md) allows you to accept incoming payments, generate an address for each user via bloc-service RPC Wallet JSON RPC API and much more.

Make sure you visit the [bloc-service command line arguments](../wallets/bloc-service-command-line.md) to find out how to start bloc-service with a customized configuration depending your needs.

If you are looking to integrate BLOC payment and process transactions into your website or application, **bloc-service** is what you need.

## **bloc-service API**

We provide a complete API documentation and an online testing tool to use and integrate BLOC payments into your website or application.

Make sure to visit the dedicated website [BLOC-DEVELOPER](https://bloc-developer.com) including the [bloc-service category](https://bloc-developer.com/api_bloc-service?lang=english).

- How to use the [bloc-service RPC wallet](../wallets/bloc-service-json-api.md)

- How to use the [bloc-service command line arguments](../wallets/bloc-service-command-line.md)

- BLOC-DEVELOPER [bloc-service RPC Wallet JSON RPC API](https://bloc-developer.com/api_bloc-service/json)

- BLOC-DEVELOPER [bloc-service command line arguments](https://bloc-developer.com/api_bloc-service/cli_arguments)

## **bloc-service RPC Clients**

Currently we support the following official client bindings:

* [Javascript](https://github.com/furiousteam/bloc-rpc): A JavaScript wrapper for the bloc-service RPC interface.
* [NodeJS](https://www.npmjs.com/package/bloc-rpc): This project is designed to make it very easy to interact with various RPC APIs available within the BLOC Project. This entire project uses Javascript Promises to make things fast, easy, and safe.
* [Go](https://github.com/furiousteam/bloc-rpc-go): A Golang wrapper for the BLOC RPC API. This project makes it easy to send requests to particular RPC server and returns a clear response without any abrupt termination.
* [PHP](https://github.com/furiousteam/bloc-rpc-php): A PHP wrapper for BLOC's RPC interfaces.

See [bloc-service RPC API](wallet-rpc-api.md) for usage.

## **Important guides with bloc-service**

1. View [this guide](../wallets/bloc-service-command-line.md#using-your-mnemonic-seed) for steps on recovering your wallet with your mnemonic phrase (25 words) using **[bloc-service](../wallets/bloc-service-index.md)**.

2. View [this guide](../wallets/bloc-service-command-line.md#using-your-private-spend-key-and-view-key) for steps on recovering your wallet with your private spend and view keys using **[bloc-service](../wallets/bloc-service-index.md)**.