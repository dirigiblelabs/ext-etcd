# ext-etcd

API Module for Etcd.

Etcd is a key-value store written in [Go](https://golang.org/) which provides a reliable way to store data that needs to be accessed by a distributed system or cluster of machines.

## Prerequisite

For this API to work etcd should be setup and running. You can either download the pre-built binary or build the latest version from the [`master`]( https://github.com/etcd-io/etcd) branch of etcd. Please refer to the official instructions at provided at [etcd docs](https://etcd.io/docs).

## Example

```
// Load the etcd client module.
var etcd = require("etcd/client");

// Initialize the etcd client.
var etcdClient = etcd.getClient();

// Put key value pair where the value is a string.
etcdClient.putStringValue("foo", "bar");

// Get key value pair where value will be returned as a string.
etcdClient.getKvsStringValue("foo"); // => { "foo": "bar" }

// Put key value pair where the value is a byte array.
etcdClient.putByteArrayValue("foo", [98, 97, 114]);

// Get key value pair where value will be returned as a byte array.
etcdClient.getKvsByteArrayValue("foo"); // => { "foo": [98, 97, 114] }

// Delete key value pair.
etcdClient.delete("foo");
```

