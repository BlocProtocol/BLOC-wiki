# **BLOCd Daemon HTTP RPC API**

[BLOCd](BLOCd-Overview.md) daemon provides a **HTTP RPC API**, used to receive informations from the blockchain allowing it to be controlled locally or remotely which makes it useful for integration with other software or in larger payment systems. Various commands are made available by the API described on [this page](https://bloc-developer.com/api_BLOCd/http).

## **BLOC-DEVELOPER**

This page is only a short guide how to get you started with the BLOCd Daemon HTTP RPC API. Please visit the [dedicated section on the BLOC-DEVELOPER](https://bloc-developer.com/api_BLOCd/http) website to view and test all the features available from the [BLOCd Daemon](BLOCd-Overview.md) HTTP RPC API.

## **Errors**

* Make sure you check the [RPC Errors conditions](../API/rpc-api-error-conditions.md).

## **Client bindings**

Currently we support the following official client bindings:

* [NodeJS](https://www.npmjs.com/package/bloc-rpc)
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
http://localhost:2086
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
## **Getting started**

This section describes BLOCd daemon integration process into your service with BLOCd HTTP RPC API. We also have available the BLOCd JSON RPC API if you need.
 
Make sure you have started BLOCd with the correct arguments before using the following functions. You can also check out the list of the BLOCd inline commands available.

To start the Daemon JSON RPC API server at `http://localhost:2086`, run:

`BLOCd --rpc-bind-port=2086`

To make the server accessible from another computer, use the `--rpc-bind-ip 0.0.0.0` switch.

`BLOCd --rpc-bind-ip=0.0.0.0 --rpc-bind-port=2086`

To enable block explorer API access (like for `getblocks`, `gettransactionpool`, etc.), use the `--enable_blockexplorer` switch.

`BLOCd --enable-blockexplorer`

The above given switches can be combined to achieve remote access with block explorer methods as shown below.

`BLOCd --enable-blockexplorer --rpc-bind-ip=0.0.0.0 --rpc-bind-port=2086`

This would make the RPC server accessible at

`http://<your ip address>:2086`

and, locally at

`http://localhost:2086`


To make a HTTP RPC request to your Daemon RPC you should use a GET request that looks like this:

`http://<service address>:<service port>`

Parameter            | Description
-------------------- | ------------------------------------------------------------
`<service address>`  | IP of Daemon RPC, if it is located on local machine it is either 127.0.0.1 or localhost
`<service port>`     | Daemon RPC port, by default it is bound to 2086 port, but it can be manually bound to any port you want


## **Example height**

```shell
curl http://localhost:2086/height
```

```javascript
daemon.getHeight().then((result) => {
  // do something
}).catch((error) => {
  // do something
})
```

```go
response := daemon.Height()
fmt.Println(response)
```

> Expected Output:

```json
{
    "height":614214,
    "network_height":614218,
    "status":"OK"
}
```

`height()` returns the height of the daemon and the network

No Input.

### Output

Argument         | Description            | Format
---------------- | ---------------------- | ------
height           | Current daemon height  | int
network_height   | Current Network height | int
status           | Status of request      | string

## **More**

Make sure you check the complete features of [BLOCd HTTP RPC API](https://bloc-developer.com/api_BLOCd/http) from the dedicated [BLOC-DEVELOPER](https://bloc-developer.com) website.