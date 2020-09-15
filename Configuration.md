You can adapt HORNET to your needs. The configuration options are shown below.

## Index

- [Config](#Config)
- [Coordinator](#Coordinator)
- [Dashboard](#Dashboard)
- [DB](#DB)
- [Graph](#Graph)
- [httpAPI](#httpAPI)
- [Logger](#Logger)
- [Monitor](#Monitor)
- [MQTT](#MQTT)
- [Network](#Network)
- [Node](#Node)
- [Peering](#Peering)
- [Profile](#Profile)
- [Profiling](#Profiling)
- [Prometheus](#Prometheus)
- [Snapshots](#Snapshots)
- [Spammer](#Spammer)
- [SpentAddresses](#SpentAddresses)
- [Tipselection](#Tipselection)
- [ZMQ](#ZMQ)

## Config

**Type:** Flag<br>
**File:** n.a.<br>
**Status:** n.a.<br>
**Options:**<br>

- `config` string
  - Filename of the config file without the file extension
    <br>Default:
    ```json
    "config"
    ```
- `config-dir` string
  - Path to the directory containing the config file
    <br>Default:
    ```json
    "."
    ```
- `peeringConfig` string
  - Filename of the peering config file without the file extension
    <br>Default:
    ```json
    "peering"
    ```
- `profilesConfig` string
  - Filename of the profiles config file without the file extension
    <br>Default:
    ```json
    "profiles"
    ```

## Coordinator

**Type:** Setting<br>
**File:** config.json<br>
**Status:** n.a.<br>
**Options:**<br>

- `coordinator.address` string
  - The address of the coordinator
    <br>Default:
    ```json
    "EQSAUZXULTTYZCLNJNTXQTQHOMOFZERHTCGTXOLTVAHKSA9OGAZDEKECURBRIXIJWNPFCQIOVFVVXJVD9"
    ```
- `coordinator.securityLevel` int
  - The security level used in coordinator signatures
    <br>Default:
    ```json
    2
    ```
- `coordinator.merkleTreeDepth` int
  - The depth of the merkle tree which in turn determines the number of leaves (private keys) that the coordinator can use to sign a message
    <br>Default:
    ```json
    23
    ```
- `coordinator.mwm` int
  - The minimum weight magnitude is the number of trailing 0s that must appear in the end of a transaction hash. Increasing this number by 1 will result in proof of work that is 3 times as hard
    <br>Default:
    ```json
    14
    ```
- `coordinator.stateFilePath` string
  - The path to the state file of the coordinator
    <br>Default:
    ```json
    "coordinator.state"
    ```
- `coordinator.merkleTreeFilePath` string
  - The path to the merkle tree of the coordinator
    <br>Default:
    ```json
    "coordinator.tree"
    ```
- `coordinator.intervalSeconds` int
  - The interval milestones are issued (in seconds)
    <br>Default:
    ```json
    60
    ```
- `coordinator.checkpointTransactions` int
  - The amount of checkpoints issued between two milestones
    <br>Default:
    ```json
    5
    ```

## Dashboard

**Type:** Plugin<br>
**File:** config.json<br>
**Status:** Enabled<br>
**Options:**<br>

- `dashboard.bindAddress` string
  - The bind address on which the dashboard can be access from
    <br>Default:
    ```json
    "localhost:8081"
    ```
- `dashboard.dev` bool
  - Whether to run the dashboard in dev mode
    <br>Default:
    ```json
    false
    ```
- `dashboard.theme` string
  - The theme for the dashboard to use (default or dark)
    <br>Default:
    ```json
    "default"
    ```
- `dashboard.basicAuth.enabled` bool
  - Whether to use HTTP basic auth
    <br>Default:
    ```json
    false
    ```
- `dashboard.basicAuth.username` string
  - The HTTP Basic Auth username
    <br>Default:
    ```json
    ""
    ```
- `dashboard.basicAuth.passwordhash` string
  - The HTTP basic auth password+salt as a sha256 hash (must be lower cased)
    <br>Default:
    ```json
    ""
    ```
- `dashboard.basicAuth.passwordsalt` string
  - The HTTP basic auth salt used for hashing the password (must be lower cased)
    <br>Default:
    ```json
    ""
    ```

## DB

**Type:** Setting<br>
**File:** config.json<br>
**Status:** n.a.<br>
**Options:**<br>

- `db.path` string
  - Path to the database folder
    <br>Default:
    ```json
    mainnetdb
    ```

## Graph

**Type:** Plugin<br>
**File:** config.json<br>
**Status:** Disabled<br>
**Options:**<br>

- `graph.webRootPath` string
  - The path to the visualizer web assets
    <br>Default:
    ```json
    "IOTAtangle/webroot"
    ```
- `graph.webSocket.uri` string
  - The websocket URI to use (optional)
    <br>Default:
    ```json
    ""
    ```
- `graph.domain` string
  - Sets the domain name from which the visualizer is served from
    <br>Default:
    ```json
    ""
    ```
- `graph.bindAddress` string
  - The bind address from which the visualizer can be accessed from
    <br>Default:
    ```json
    "localhost:8083"
    ```
- `graph.networkName` string
  - The name of the network to be shown on the visualizer site
    <br>Default:
    ```json
    "meets HORNET"
    ```
- `graph.explorerTxLink` string
  - The explorer transaction link
    <br>Default:
    ```json
    "http://localhost:8081/explorer/tx/"
    ```
- `graph.explorerBundleLink` string
  - The explorer bundle link
    <br>Default:
    ```json
    "http://localhost:8081/explorer/bundle/"
    ```

## httpAPI

**Type:** Plugin<br>
**File:** config.json<br>
**Status:** Enabled<br>
**Options:**<br>

- `httpAPI.bindAddress` string
  - The bind address on which the HTTP API listens on
    <br>Default:
    ```json
    "0.0.0.0:14265"
    ```
- `httpAPI.permitRemoteAccess` []string
  - The allowed HTTP API calls which can be called from non whitelisted addresses
    <br>Default:
    ```json
    [
      "getNodeInfo",
      "getBalances",
      "checkConsistency",
      "getTransactionsToApprove",
      "getInclusionStates",
      "getNodeAPIConfiguration",
      "wereAddressesSpentFrom",
      "broadcastTransactions",
      "findTransactions",
      "storeTransactions",
      "getTrytes"
    ]
    ```
- `httpAPI.whitelistedAddresses` []string
  - The whitelist of addresses which are allowed to access the HTTP API
    <br>Default:
    ```json
    []
    ```
- `httpAPI.excludeHealthCheckFromAuth` bool
  - Whether to allow the health check route anyways
    <br>Default:
    ```json
    false
    ```
- `httpAPI.basicAuth.enabled` bool
  - Whether to use HTTP basic auth for the HTTP API
    <br>Default:
    ```json
    false
    ```
- `httpAPI.basicAuth.username` string
  - The username of the HTTP basic auth
    <br>Default:
    ```json
    ""
    ```
- `httpAPI.basicauth.passwordhash` string
  - The HTTP basic auth password+salt as a sha256 hash (must be lower cased)
    <br>Default:
    ```json
    ""
    ```
- `httpAPI.basicauth.passwordsalt` string
  - The HTTP basic auth salt used for hashing the password (must be lower cased)
    <br>Default:
    ```json
    ""
    ```
- `httpAPI.limits.bodyLengthBytes` int
  - The maximum number of characters that the body of an API call may contain
    <br>Default:
    ```json
    1000000
    ```
- `httpAPI.limits.findTransactions` int
  - The maximum number of transactions that may be returned by the findTransactions endpoint
    <br>Default:
    ```json
    1000
    ```
- `httpAPI.limits.getTrytes` int
  - The maximum number of trytes that may be returned by the getTrytes endpoint
    <br>Default:
    ```json
    1000
    ```
- `httpAPI.limits.requestsList` int
  - The maximum number of parameters in an API call
    <br>Default:
    ```json
    1000
    ```

## Logger

**Type:** Setting<br>
**File:** config.json<br>
**Status:** n.a.<br>
**Options:**<br>

- `logger.level` string
  - The minimum enabled logging level
    <br>Default:
    ```json
    "info"
    ```
- `logger.disableCaller` bool
  - Stops annotating logs with the calling function's file name and line number
    <br>Default:
    ```json
    true
    ```
- `logger.encoding` string

  - Sets the logger's encoding. Valid values are "json" and "console"
    <br>Default:
    ```json
    "console"
    ```

- `logger.outputPaths` []string

  - A list of URLs, file paths or stdout/stderr to write logging output to
    <br>Default:
    ```json
    ["stdout"]
    ```

- `logger.disableEvents` bool
  - Prevents log messages from being raced as events
    <br>Default:
    ```json
    false
    ```

## Monitor

**Type:** Plugin<br>
**File:** config.json<br>
**Status:** Disabled<br>
**Options:**<br>

- `monitor.tangleMonitorPath` string
  - Path to the tanglemonitor web assets
    <br>Default:
    ```json
    "tanglemonitor/frontend"
    ```
- `monitor.domain` string
  - The domain from which the tanglemonitor is served from
    <br>Default:
    ```json
    ""
    ```
- `monitor.webSocket.uri` string
  - The websocket URI to use (optional)
    <br>Default:
    ```json
    ""
    ```
- `monitor.remoteAPIPort` int
  - The remote API port
    <br>Default:
    ```json
    4433
    ```
- `monitor.initialTransactions` int
  - The initial amount of tx to load
    <br>Default:
    ```json
    15000
    ```
- `monitor.webBindAddress` string
  - The bind address on which the monitor can be access from
    <br>Default:
    ```json
    "localhost:4434"
    ```
- `monitor.apiBindAddress` string
  - The bind address on which the API listens on
    <br>Default:
    ```json
    "localhost:4433"
    ```

## MQTT

**Type:** Plugin<br>
**File:** config.json<br>
**Status:** Disabled<br>
**Options:**<br>

- `mqtt.config` string
  - Path to the MQTT broker config file
    <br>Default:
    ```json
    "mqtt_config.json"
    ```

## Network

**Type:** Setting<br>
**File:** config.json<br>
**Status:** n.a.<br>
**Options:**<br>

- `network.preferIPv6` bool
  - Defines if IPv6 is preferred for neighbors added through the APIDefines if IPv6 is preferred for neighbors added through the API
    <br>Default:
    ```json:
    false
    ```
- `network.gossip.bindAddress` string
  - The bind address of the gossip TCP server
    <br>Default:
    ```json
    "0.0.0.0:15600"
    ```
- `network.gossip.reconnectAttemptIntervalSeconds` int
  - The number of seconds to wait before trying to reconnect to a disconnected neighbor
    <br>Default:
    ```json
    60
    ```
- `network.autopeering.entryNodes` []string
  - List of autopeering entry nodes to use
    <br>Default:
    ```json
    ["LehlDBPJ6kfcfLOK6kAU4nD7B/BdR7SJhai7yFCbCCM=@enter.hornet.zone:14626"]
    ```
- `network.autopeering.bindAddress` string
  - Bind address for global services such as autopeering and gossip
    <br>Default:
    ```json
    "0.0.0.0:14626"
    ```
- `network.autopeering.externalAddress` string
  - External IP address under which the node is reachable; or 'auto' to determine it automatically
    <br>Default:
    ```json
    "auto"
    ```
- `network.autopeering.seed` string
  - Private key seed used to derive the node identity; optional Base64 encoded 256-bit string
    <br>Default:
    ```json
    ""
    ```
- `network.autopeering.runAsEntryNode` bool
  - Whether the node should act as an autopeering entry node
    <br>Default:
    ```json
    false
    ```

## Node

**Type:** Setting<br>
**File:** config.json<br>
**Status:** n.a.<br>
**Options:**<br>

- `node.alias` string
  - Set an alias to identify your node
    <br>Default:
    ```json
    ""
    ```
- `node.showAliasInGetNodeInfo` string
  - Defines whether to show the alias in getNodeInfo
    <br>Default:
    ```json
    false
    ```
- `node.disablePlugins` []string
  - Disable plugins
    <br>Default:
    ```json
    []
    ```
- `node.enablePlugins` []string
  - Enable plugins
    <br>Default:
    ```json
    []
    ```

## Peering

**Type:** Setting<br>
**File:** peering.json<br>
**Status:** n.a.<br>
**Options:**<br>

- `acceptAnyConnection` bool
  - Whether to enable inbound connections from unknown manual peers
    <br>Default:
    ```json
    false
    ```
- `maxPeers` int
  - Set the maximum number of manual peers (excl. max. 4 auto-peers)
    <br>Default:
    ```json
    5
    ```
- `peers` []PeerConfig
  - Set the URLs and IP addresses of manual peers
    <br>Default:
    ```json
    [
      {
        "identity": "example.neighbor.com:15600",
        "alias": "Example Peer",
        "preferIPv6": false
      }
    ]
    ```

## Profile

**Type:** Setting<br>
**File:** config.json<br>
**Status:** n.a.<br>
**Options:**<br>

- `useProfile` string
  - Which profile should be used
    <br>Default:
    ```json
    "auto"
    ```

## Profiling

**Type:** Setting<br>
**File:** config.json<br>
**Status:** n.a.<br>
**Options:**<br>

- `profiling.bindAddress` string
  - The bind address on which the profiler listens on
    <br>Default:
    ```json
    "localhost:6060"
    ```

## Prometheus

**Type:** Plugin<br>
**File:** config.json<br>
**Status:** Disabled<br>
**Options:**<br>

- `prometheus.bindAddress` string
  - The bind address on which the Prometheus exporter listens on
    <br>Default:
    ```json
    "localhost:9311"
    ```
- `prometheus.goMetrics` bool
  - Whether to include go metrics
    <br>Default:
    ```json
    false
    ```
- `prometheus.processMetrics` bool
  - Whether to include process metrics
    <br>Default:
    ```json
    false
    ```
- `prometheus.promhttpMetrics` bool
  - Whether to include promhttp metrics
    <br>Default:
    ```json
    false
    ```

## Snapshots

**Type:** Setting<br>
**File:** config.json<br>
**Status:** n.a.<br>
**Options:**<br>

- `snapshots.loadType` string
  - Which snapshot type to load. 'local' or 'global'
    <br>Default:
    ```json
    "local"
    ```
- `snapshots.local.depth` int
  - The depth, respectively the starting point, at which a local snapshot of the ledger is generated
    <br>Default:
    ```json
    50
    ```
- `snapshots.local.intervalSynced` int
  - Interval, in milestone transactions, at which snapshot files are created if the ledger is fully synchronized
    <br>Default:
    ```json
    50
    ```
- `snapshots.local.intervalUnsynced` int
  - Interval, in milestone transactions, at which snapshot files are created if the ledger is not fully synchronized
    <br>Default:
    ```json
    1000
    ```
- `snapshots.local.path` string
  - Path to the local snapshot file
    <br>Default:
    ```json
    "latest-export.gz.bin"
    ```
- `snapshots.local.downloadURL` string
  - URL to load the local snapshot file from
    <br>Default:
    ```json
    ""
    ```
- `snapshots.global.path` string
  - Path to the global snapshot file containing the ledger state
    <br>Default:
    ```json
    "snapshotMainnet.txt"
    ```
- `snapshots.global.spentAddressesPath` []string
  - Paths to the spent addresses files
    <br>Default:
    ```json
    [
      "previousEpochsSpentAddresses1.txt",
      "previousEpochsSpentAddresses2.txt",
      "previousEpochsSpentAddresses3.txt"
    ]
    ```
- `snapshots.global.index` int
  - Milestone index of the global snapshot
    <br>Default:
    ```json
    1050000
    ```
- `snapshots.pruning.enabled` bool
  - Whether to delete old transaction data from the database
    <br>Default:
    ```json
    false
    ```
- `snapshots.pruning.delay` int
  - Amount of milestone transactions to keep in the database
    <br>Default:
    ```json
    40000
    ```

## Spammer

**Type:** Plugin<br>
**File:** config.json<br>
**Status:** Disabled<br>
**Options:**<br>

- `spammer.address` string
  - The address you want to use (you don't have to own it as it's zero value spam)
    <br>Default:
    ```json
    "HORNET99INTEGRATED99SPAMMER999999999999999999999999999999999999999999999999999999"
    ```
- `spammer.message` string
  - The message you want to send with your spam (keep it short)
    <br>Default:
    ```json
    "Spamming with HORNET tipselect"
    ```
- `spammer.tag` string
  - The tag you want to use (can not be longer than 27 trytes [A-Z, 9])
    <br>Default:
    ```json
    "HORNET99SPAMMER999999999999"
    ```
- `spammer.depth` int
  - Depth for tip selection. Set it to `3` if you don't know what this is for.
    <br>Default:
    ```json
    3
    ```
- `spammer.bundleSize` int
  - The size of the spam bundles
    <br>Default:
    ```json
    1
    ```
- `spammer.valueSpam` bool
  - Enable spamming with value bundles
    <br>Default:
    ```json
    false
    ```
- `spammer.tpsRateLimit` float
  - Defines how many transactions (TX) the spammer should try to send (e.g. `0.1` stands for 0.1 TX per second --> 1 TX every 10 seconds. **NOTE:** the maximum `tpsratelimit` is limited by your used hardware. Start with a lower value and slightly increase it, watch your CPU usage (0 = no limit).
    <br>Default:
    ```json
    0.1
    ```
- `spammer.cpuMaxUsage` float
  - Workers remains idle for a while when cpu usage gets over this limit (0 = disable)
    <br>Default:
    ```json
    0.5
    ```
- `spammer.workers` int
  - Number of workers the spammer spins up --> Number of CPU cores you want to use (you should not use all available cores)
    <br>Default:
    ```json
    1
    ```
- `spammer.autostart` bool
  - Whether to automatically start the spammer on node startup. To start it via the API, use the `/spammer` endpoint (for example: http://localhost:14265/spammer?cmd=start&tpsRateLimit=2.5&valueSpam=false&bundleSize=1&cpuMaxUsage=0.5).
    <br>Default:
    ```json
    false
    ```

## SpentAddresses

**Type:** Setting<br>
**File:** config.json<br>
**Status:** n.a.<br>
**Options:**<br>

- `spentAddresses.enabled` bool
  - Enable support for wereAddressesSpentFrom (needed for Trinity, but local snapshots are much bigger)
    <br>Default:
    ```json
    true
    ```

## Tipselection

**Type:** Setting<br>
**File:** config.json<br>
**Status:** n.a.<br>
**Options:**<br>

- `tipsel.belowMaxDepthTransactionLimit` int
  - Number of tx to automatically flag them as below the max depth
    <br>Default:
    ```json
    20000
    ```
- `tipsel.maxDepth` int
  - Max. depth for tip selection
    <br>Default:
    ```json
    15
    ```

## ZMQ

**Type:** Plugin<br>
**File:** config.json<br>
**Status:** Disabled<br>
**Options:**<br>

- `zmq.bindAddress` string
  - The bind address of the ZMQ feed
    <br>Default:
    ```json
    "localhost:5556"
    ```
- `zmq.protocol` string
  - Protocol used to connect to the zmq feed [unix, tcp, udp, inproc]
    <br>Default:
    ```json
    "tcp"
    ```
