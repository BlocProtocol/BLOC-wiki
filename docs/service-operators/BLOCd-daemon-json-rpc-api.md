# **Daemon JSON RPC API**

[BLOCd](BLOCd-Overview.md) Daemon provides a **JSON RPC API**, used to receive informations from the blockchain allowing it to be controlled locally or remotely which makes it useful for integration with other software or in larger payment systems. Various commands are made available by the API described on [this page](https://bloc-developer.com/api_BLOCd/json).

## **BLOC-DEVELOPER**

This page is only a short guide how to get you started with the **BLOCd Daemon JSON RPC API**. Please visit the [dedicated section on the BLOC-DEVELOPER](https://bloc-developer.com/api_BLOCd/json) website to view and test all the features available from the [BLOCd Daemon](BLOCd-Overview.md) JSON RPC API.


## **Installing**

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

## **Getting Started**

This section describes [BLOCd Daemon](BLOCd-Overview.md) integration process into your service with BLOCd JSON RPC API. We also have available the [BLOCd HTTP RPC API](BLOCd-daemon-http-rpc-api.md) if you need.
 
Make sure you have started **BLOCd** with the correct configuration to [enable BLOCd JSON RPC API](BLOCd-daemon-arguments.md) before using the following functions. Once is started you will be able to use the [BLOCd Command Inline Options](BLOCd-daemon-cli-options.md) available.


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