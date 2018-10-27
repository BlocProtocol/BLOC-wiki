# Daemon HTTP RPC API

Daemon HTTP RPC is a HTTP server which provides additional information regarding Network and Daemon connections.

## Errors

* Make sure you check the [RPC Errors conditions](../API/rpc-api-error-conditions.md).

Currently we support the following official client bindings:

* [NodeJS](https://www.npmjs.com/package/bloc-rpc)
* [PHP](https://github.com/furiousteam/BLOC-rpc-php)
* [Go](https://github.com/furiousteam/BLOC-rpc-go)



```php
composer require furiousteam/BLOC-rpc-php
```

```go
go get github.com/furiousteam/BLOC-rpc-go
```

## Interacting with the API

> API endpoint example

```
http://localhost:2086
```

> Configuration and Instantiation

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

To start the Daemon JSON RPC API server at `http://localhost:2086`, run:

`BLOCd --rpc-bind-port=2086`

To make the server accessible from another computer, use the `--rpc-bind-ip 0.0.0.0` switch.

`BLOCd --rpc-bind-ip=0.0.0.0 --rpc-bind-port=2086`

To enable block explorer API access (like for `getblocks`, `gettransactionpool`, etc.), use the `--enable_blockexplorer` switch.

`BLOCd --enable_blockexplorer`

The above given switches can be combined to achieve remote access with block explorer methods as shown below.

`BLOCd --enable_blockexplorer --rpc-bind-ip=0.0.0.0 --rpc-bind-port=2086`

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


## getheight

```shell
curl http://localhost:2086/getheight
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

`getheight()` returns the height of the daemon and the network

No Input.

**Output**

Argument         | Description          | Format
---------------- | -------------------- | ------
height            | Current daemon height | int
network_height    | Current Network height | int
status           | Status of request | string

## getinfo

```shell
curl http://localhost:2086/getinfo
```

```javascript
daemon.getInfo().then((result) => {
  // do something
}).catch((error) => {
  // do something
})
```

```php
<?php
$response = $blocd->getInfo();
echo $response;
```

```go
response := daemon.Info()
fmt.Println(response)
```

> Expected Output:

```json
{
    "alt_blocks_count":1,
    "difficulty":250340644,
    "grey_peerlist_size":493,
    "hashrate":8344688,
    "height":614321,
    "incoming_connections_count":28,
    "last_known_block_index":614319,
    "major_version":4,
    "minor_version":0,
    "network_height":614321,
    "outgoing_connections_count":8,
    "start_time":1531403048,
    "status":"OK",
    "supported_height":620000,
    "synced":true,
    "testnet":false,
    "tx_count":720189,
    "tx_pool_size":0,
    "upgrade_heights":[
        187000,
        350000,
        440000,
        620000,
        .....
    ],
    "version":"0.6.3",
    "white_peerlist_size":43
}
```

`getinfo()` returns information related to the network and daemon connection

No Input.

**Output**

Argument         | Description          | Format
---------------- | -------------------- | ------
alt_blocks_count | - | int
difficulty    | difficulty of the top block | int
gray_peerlist_size | - | int
hashrate | hashrate of the network | int
height | height of the daemon | int
incoming_connections_count | number of incoming connections to the daemon | int
last_known_block_index | - | int
major_version | - | int
minor_version | - | int
network_height | height of the network | int
outgoing_connections_count | number of outgoing connections from the daemon | int
start_time | - | int
status           | Status of request | string
supported_height | supported fork height | int
synced | sync status | bool
testnet | whether the daemon is on testnet or not | bool
tx_count | transaction count in the network | int
tx_pool_size | - | int
upgrade_heights | pre-determined fork heights | array
version | version of the daemon | string
white_peerlist_size | - | int

## gettransactions

```shell
curl http://localhost:2086/gettransactions
```

```javascript
daemon.getTransactions({
  hashes: [
    'f2b15d7c3ce5b80cb02c0c05a4adaf0ad3280faa376b95ba0394e898331fe49c',
    '1c6e0ed8cc3c1a0a9ecc3921e199ff1de0ec242fa8721dfc427e74d2c29884f0'
  ]
}).then((result) => {
  // do something
}).catch((error) => {
  // do something
})
```

```php
<?php
$response = $blocd->getTransactions();
echo $response;
```

```go
Not Implemented
```

> Expected Output:

```json
{
    "missed_tx":[],
    "status":"OK",
    "txs_as_hex":[]
}
```

`gettransactions()` method returns list of missed transactions

No Input

**Output**

Argument         | Description          | Format
---------------- | -------------------- | ------
missed_tx            | array of missed transactions | array
status           | Status of request | string
txs_as_hex   | array of hex values of missed transactions | array

## getpeers

```shell
curl http://localhost:2086/getpeers
```

```php
<?php
$response = $blocd->getPeers();
echo $response;
```

```python
response = blocd.get_peers()
print(response)
```

```go
response := daemon.Peers()
fmt.Println(response)
```

> Expected Output:

```json
{
    "peers":[
        "192.222.157.172:2082",
        "94.23.49.75:2082",
        "112.78.10.43:2082",
        .....
    ],
    "status":"OK"
}
```

`getpeers()` method returns the list of peers connected to the daemon

No Input.

**Output**

Argument         | Description          | Format
---------------- | -------------------- | ------
peers           | array of peers (peer_ip:peer_port) | array
status           | Status of request | string

## feeinfo

```shell
curl http://localhost:2086/feeinfo
```

```javascript
daemon.feeInfo().then((result) => {
  // do something
}).catch((error) => {
  // do something
})
```

```php
<?php
$response = $blocd->getFeeInfo();
echo $response;
```

```go
response := daemon.Fee()
fmt.Println(response)
```

> Expected Output:

```json
{
    "address":"",
    "amount":0,
    "status":"Node's fee address is not set"
}
```

`feeinfo()` method returns information about the fee set for the remote node.

No Input.

**Output**

Argument         | Description          | Format
---------------- | -------------------- | ------
address            | address to which the fee is paid | string
amount    | fee amount | int
status           | Status of fees for the node | string


## License

[![Creative Commons License](/images/cc-by-sa.png)](https://creativecommons.org/licenses/by-sa/3.0/)

The content in this document were originally written by the [Bytecoin (BCN) Developers](https://bytecoin.org/). It is licensed under the [CC BY SA 3.0 license](https://creativecommons.org/licenses/by-sa/3.0/). The source material can be found at the [Bytecoin Wiki](https://wiki.bytecoin.org/).

Also of note, TurtleCoin developers have altered and adapted the content to suit our implementation of the API. This was done independently of the Bytecoin development team. They neither endorse or acknowledge our changes. Feel free to adopt or change our content as per the [CC BY SA 3.0 license](https://creativecommons.org/licenses/by-sa/3.0/) requirements.

_TurtleCoin developers 2018_

Also of note, BLOC developers have altered and adapted the content to suit our implementation of the API. This was done independently of the [TurtleCoin](https://turtlecoin.lol) development team. They neither endorse or acknowledge our changes. Feel free to adopt or change our content as per the [CC BY SA 3.0 license](https://creativecommons.org/licenses/by-sa/3.0/) requirements. 

_BLOC developers 2018_