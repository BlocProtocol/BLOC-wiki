# **BLOC-service Wallet RPC API

[BLOC-service](bloc-service-index.md) RPC Wallet is a HTTP server which provides JSON 2.0 RPC interface for [BLOC](https://bloc.money) payment operations and address management. BLOC-service RPC Wallet allows you to accept incoming payments, generate an address for each user via **BLOC-service RPC Wallet JSON RPC API** and much more.

## **BLOC-DEVELOPER**

This page is only a short guide how to get you started with the **BLOC-service JSON RPC API**. Please visit the [dedicated section on the BLOC-DEVELOPER](https://bloc-developer.com/api_bloc-service/json) website to view and test all the features available from the [BLOC-service](bloc-service-index.md) JSON RPC API.

## Errors

* Make sure you check the [RPC Errors conditions](../API/rpc-api-error-conditions.md).

## Installing

Currently we support the following official client bindings:

* [JavaScript](https://www.npmjs.com/package/bloc-rpc)
* [PHP](https://github.com/furiousteam/BLOC-rpc-php)
* [Go](https://github.com/furiousteam/BLOC-rpc-go)

```javascript
npm install bloc-rpc
```

```php
composer require furiousteam/BLOC-rpc-php
```

```go
go get github.com/furiousteam/BLOC-rpc-go
```

## Getting Started

This section describes [BLOC](https://bloc.money) integration process into your service with BLOC e-commerce solution called [BLOC-service](bloc-service-index.md) RPC Wallet.

Each method has its own example and description that can be found by clicking the details button from the [BLOC-DEVELOPER](https://bloc-developer) website.
 
To start using [BLOC-service](bloc-service-index.md) you must first generate a container. Container file is the only file that stores all data required to run your service. It contains user addresses and private keys required to operate them. **Make sure to backup this file regularly**.

To generate a new container visit the [BLOC-service RPC Wallet command line arguments](https://bloc-developer.com/api_bloc-service/cli_arguments) and look at the `--generate-container` function to read the explanation. More on how to start and operate BLOC-service RPC Wallet can be found [here](bloc-service-command-line.md).
 
To start the BLOC-service JSON RPC API server at http://localhost:8070, run:
`./BLOC-service`
 
To make the server accessible from another computer, use the --rpc-bind-ip 0.0.0.0 switch.
`./BLOCd --rpc-bind-ip=0.0.0.0`
 
To make a JSON RPC request to your BLOC-service RPC Wallet you should use POST request that looks like this:
 
`http://<service address>:<service port>/json_rpc`
 
Where:
`<service address> `is an IP of BLOC-service RPC Wallet, if RPC Wallet is located on local machine it is either 127.0.0.1 or localhost,
`<service port>` is BLOC-service RPC Wallet port, by default it is binded to 8070 port, but it can be manually binded to any port you want, read more about this here.
 
Make sure you have filled the connexion details at the top of this page. Once you are ready, scroll down until your favorite function, fill the details and click TRY IT OUT button to send the request and get the the response.


## Interacting with the API

> API endpoint example

```
http://localhost:8070/json_rpc
```

> Configuration and instantiation

```javascript
const BlocService = require('bloc-rpc').BlocService

const service = new BlocService({
  host: '127.0.0.1', // ip address or hostname of the bloc-service host
  port: 8070, // what port is bloc-service running on
  timeout: 2000, // request timeout
  ssl: false, // whether we need to connect using SSL/TLS
  rpcPassword: 'inblocwetrust', // must be set to the password used to run bloc-service

  // RPC API default values
  defaultMixin: false, // the default mixin to use for transactions, the default setting is false which means we don't have a default value
  defaultFee: 1, // the default transaction fee for transactions
  defaultBlockCount: 1, // the default number of blocks when blockCount is required
  decimalDivisor: 1000, // Currency has many decimal places?
  defaultFirstBlockIndex: 1, // the default first block index we will use when it is required
  defaultUnlockTime: 0, // the default unlockTime for transactions
  defaultFusionThreshold: 1, // the default fusionThreshold for fusion transactions
})
```

```php
<?php
use BLOC\BlocService;

$config = [
    'rpcHost'     => 'http://localhost',
    'rpcPort'     => 8070,
    'rpcPassword' => 'passw0rd',
];

$blocService = new BlocService($config);
```

```go
import (
  "fmt"
  trpc "github.com/furiousteam/BLOC-rpc-go"
)

rpcHost := "localhost"
rpcPort := 8070
rpcPassword := "passw0rd"

service := trpc.Walletd{
  URL: rpcHost,
  Port: rpcPort,
  RPCPassword: rpcPassword}
```

To make a JSON RPC request to your TurtleCoin RPC Wallet you should use a POST request that looks like this:

`http://<service address>:<service port>/json_rpc`

Parameter            | Description
-------------------- | ------------------------------------------------------------
`<service address>`  | IP of TurtleCoin RPC Wallet, if RPC Wallet is located on local machine it is either 127.0.0.1 or localhost
`<service port>`     | TurtleCoin RPC Wallet port, by default it is bound to 8070 port, but it can be manually bound to any port you want



## **Example getAddresses**

```shell
curl -d '{"jsonrpc":"2.0","id":1,"password":"passw0rd","method":"getAddresses","params":{}}' http://localhost:8070/json_rpc
```

```javascript
service.getAddresses().then((result) => {
  // do something
}).catch((error) => {
  //do something
})
```

```php
<?php
$response = $blocService->getAddresses();
echo $response;
```

```go
response, err := service.GetAddresses()
if err != nil {
  fmt.Println(err)
} else {
  fmt.Println(response)
}
```

> Expected output:

```json
{
  "id":1,
  "jsonrpc":"2.0",
  "result":{
    "addresses":[
      "abLocxxxx...",
      "abLocxxxx..."
    ]
  }
}
```

`getAddresses()` method returns an array of your RPC Wallet's addresses.

No input.

**Output**

Argument          | Description                                           | Format
----------------- | ----------------------------------------------------- | ------
addresses	      | Array of strings, where each string is an address	  | array


## **More**

Make sure you check the complete features of [BLOCd HTTP RPC API](https://bloc-developer.com/api_BLOCd/http) from the dedicated [BLOC-DEVELOPER](https://bloc-developer.com) website.