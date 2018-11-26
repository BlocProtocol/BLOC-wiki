# **Daemon JSON RPC API**

[BLOCd](BLOCd-Overview.md) Daemon provides a **JSON RPC API**, used to receive informations from the blockchain allowing it to be controlled locally or remotely which makes it useful for integration with other software or in larger payment systems. Various commands are made available by the API described on [this page](https://bloc-developer.com/api_BLOCd/json).

## **BLOC-DEVELOPER**

This page is only a short guide how to get you started with the BLOCd Daemon JSON RPC API. Please visit the [dedicated section on the BLOC-DEVELOPER](https://bloc-developer.com/api_BLOCd/json) website to view and test all the features available from the [BLOCd Daemon](BLOCd-Overview.md) JSON RPC API.

## **Errors**

* Make sure you check the [RPC Errors conditions](../API/rpc-api-error-conditions.md).

## **Client bindings**

Currently we support the following official client bindings:

* [JavaScript](https://www.npmjs.com/package/bloc-rpc)
* [PHP](https://github.com/furiousteam/BLOC-rpc-php)
* [Go](https://github.com/furiousteam/BLOC-rpc-go)

```javascript
npm install bloc-rpc
```

```php
composer require github.com/furiousteam/BLOC-rpc-php
```

```go
go get github.com/furiousteam/BLOC-rpc-go
```

## **Interacting with the API**

> API endpoint example

```
http://localhost:2086/json_rpc
```

> Configuration and Installation

```javascript
const BLOCd = require('bloc-rpc').BLOCd

const daemon = new BLOCd({
  host: '0.0.0.0', // ip address or hostname of the BLOCd host
  port: 2086, // what port is the RPC server running on
  timeout: 2000, // request timeout
  ssl: false // whether we need to connect using SSL/TLS
})
```

```php
<?php
use BLOC\BLOCd;

$config = [
    'rpcHost' => 'http://localhost',
    'rpcPort' => 2086,
];

$blocd = new BLOCd($config);
```

```go
import (
    "fmt"
    trpc "github.com/furiousteam/BLOC-rpc-go"
)

rpcHost := "localhost"
rpcPort := 2086

daemon := trpc.BLOCd{
    URL: rpcHost,
    Port: rpcPort}
```
## **Getting Started**

To start the Daemon JSON RPC API server at `http://localhost:2086/json_rpc`, run:

`BLOCd --rpc-bind-port=2086`

To make the server accessible from another computer, use the `--rpc-bind-ip 0.0.0.0` switch.

`BLOCd --rpc-bind-ip=0.0.0.0 --rpc-bind-port=2086`

To enable block explorer API access (like for `getblocks`, `gettransactionpool`, etc.), use the `--enable_blockexplorer` switch.

`BLOCd --enable-blockexplorer`

The above given switches can be combined to achieve remote access with block explorer methods as shown below.

`BLOCd --enable-blockexplorer --rpc-bind-ip=0.0.0.0 --rpc-bind-port=2086`

This would make the RPC server accessible at

`http://<your ip address>:2086/json_rpc`

and, locally at

`http://localhost:2086/json_rpc`


To make a JSON RPC request to your Daemon RPC you should use a POST request that looks like this:

`http://<service address>:<service port>/json_rpc`

Parameter            | Description
-------------------- | ------------------------------------------------------------
`<service address>`  | IP of Daemon RPC, if it is located on local machine it is either 127.0.0.1 or localhost
`<service port>`     | Daemon RPC port, by default it is bound to 2086 port, but it can be manually bound to any port you want


## **Example getblockcount**

```shell
curl -d '{"jsonrpc":"2.0", "method":"getblockcount", "params":{}}' http://localhost:2086/json_rpc
```

```javascript
daemon.getBlockCount().then((blockCount) => {
  // do something
}).catch((error) => {
  // do something
})
```

```php
<?php
$response = $blocd->getBlockCount();
echo $response;
```

```go
response := daemon.GetBlockCount()
fmt.Println(response)
```

> Expected Output

```json
{
    "jsonrpc":"2.0",
    "result":{
        "count":560915,
        "status":"OK"
    }
}
```

`getblockcount()` method returns the current chain height.

No Input.

**Output**

Argument         | Description          | Format
---------------- | -------------------- | ------
count            | Current chain height | int
status           | Status of request | string

## **More**

Make sure you check the complete features of [BLOCd JSON RPC API](https://bloc-developer.com/api_BLOCd/json) from the dedicated [BLOC-DEVELOPER](https://bloc-developer.com) website.