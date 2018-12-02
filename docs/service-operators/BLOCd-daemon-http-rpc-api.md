# **BLOCd Daemon HTTP RPC API**

[BLOCd](BLOCd-Overview.md) daemon provides a **HTTP RPC API**, used to receive informations from the blockchain allowing it to be controlled locally or remotely which makes it useful for integration with other software or in larger payment systems. Various commands are made available by the API described on [this page](https://bloc-developer.com/api_BLOCd/http).

## **BLOC-DEVELOPER**

This page is only a short guide how to get you started with the BLOCd Daemon HTTP RPC API. Please visit the [dedicated section on the BLOC-DEVELOPER](https://bloc-developer.com/api_BLOCd/http) website to view and test all the features available from the [BLOCd Daemon](BLOCd-Overview.md) HTTP RPC API.


## **Installing**

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

## **Getting started**

This section describes [BLOCd Daemon](BLOCd-Overview.md) integration process into your service with BLOCd HTTP RPC API. We also have available the [BLOCd JSON RPC API](BLOCd-daemon-json-rpc-api.md) if you need.
 
Make sure you have started **BLOCd** with the correct configuration to [enable BLOCd JSON RPC API](BLOCd-daemon-arguments.md#launch-blocd-to-enable-the-http-rpc-api) before using the following functions.


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