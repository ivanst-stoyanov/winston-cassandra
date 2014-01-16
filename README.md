# winston-cassandra

A Cassandra transport for [winston](https://github.com/flatiron/winston).

## Installation
``` bash
  $ npm install winston
  $ npm install winston-cassandra
```

## Usage
``` js
  var winston = require('winston');

  // Add Cassandra transport (it also adds the field `winston.transports.Cassandra`)
  winston.add(require('winston-cassandra'), options);
```

The Cassandra transport accepts the following options.

* __level:__ Level of messages that this transport should log.
* __table:__ The name of the Cassandra column family you wish your logs (default: `'logs'`).
* __partitionBy:__ The name of the Cassandra column family you wish your logs. Possible values `'hour'` and `'day'`(Default).
* __consistency:__ The consistency of the insert query (default: `quorum`).

In addition to the options: accepted by the [Node.js Cassandra driver](https://github.com/jorgebay/node-cassandra-cql)
 [Client][0]

* __hosts:__ Cluster nodes that will handle the write requests.
Array of strings containing the hosts, for example `['host1', 'host2']` (required).
* __keyspace:__ The name of the keyspace that will contain the logs table (required). The keyspace should be already created in the cluster.
* __[...][0]__


[0]: https://github.com/jorgebay/node-cassandra-cql#client