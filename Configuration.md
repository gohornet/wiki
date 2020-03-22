You can adapt HORNET to your needs. The configuration options are shown below.

## Index

- [Compass](#Compass)
- [Config](#Config)
- [Dashboard](#Dashboard)
- [DB](#DB)
- [Graph](#Graph)
- [httpAPI](#httpAPI)
- [Logger](#Logger)
- [Milestones](#Milestones)
- [Monitor](#Monitor)
- [MQTT](#MQTT)
- [Network](#Network)
- [Node](#Node)
- [Profile](#Profile)
- [Profiling](#Profiling)
- [Protocol](#Protocol)
- [Snapshots](#Snapshots)
- [Spammer](#Spammer)
- [SpentAddresses](#SpentAddresses)
- [Tipselection](#Tipselection)
- [ZeroMQ](#ZeroMQ)

## Compass

**Type:** Setting<br>
**Status:** n.a.<br>
**Options:**<br>

- `compass.loadLSMIAsLMI` bool
  - Set LSM as LSMI if enabled
    Default:<br>
    ```json
    false
    ```

## Config

**Type:** Setting<br>
**Status:** n.a.<br>
**Options:**<br>

- `config` string
  - Filename of the config file without the file extension
    Default:<br>
    ```json
    "config"
    ```
- `config-dir` string
  - Path to the directory containing the config file
    Default:<br>
    ```json
    "."
    ```
- `neighborsconfig` string
  - Filename of the neighbors config file without the file extension
    Default:<br>
    ```json
    "."
    ```
- `profilesconfig` string
  - Filename of the profiles config file without the file extension
    Default:<br>
    ```json
    "profiles"
    ```

## Dashboard

**Type:** Plugin<br>
**Status:** Enabled<br>
**Options:**<br>

- `dashboard.bindAddress` string
  - The bind address on which the dashboard can be access from
    Default:<br>
    ```json
    "localhost:8081"
    ```
- `dashboard.dev` bool
  - Whether to run the dashboard in dev mode
    Default:<br>
    ```json
    false
    ```
- `dashboard.theme` string
  - The theme for the dashboard to use (default or dark)
    Default:<br>
    ```json
    "default"
    ```
- `dashboard.basicAuth.enabled` bool
  - Whether to use HTTP basic auth
    Default:<br>
    ```json
    false
    ```
- `dashboard.basicAuth.username` string
  - The HTTP Basic Auth username
    Default:<br>
    ```json
    ""
    ```
- `dashboard.basicAuth.passwordhash` string
  - The HTTP basic auth password+salt as a sha256 hash (must be lower cased)
    Default:<br>
    ```json
    ""
    ```
- `dashboard.basicAuth.passwordsalt` string
  - The HTTP basic auth salt used for hashing the password (must be lower cased)
    Default:<br>
    ```json
    ""
    ```

## DB

**Type:** Setting<br>
**Status:** n.a.<br>
**Options:**<br>

- `db.path` string
  - Path to the database folder
    Default:<br>
    ```json
    mainnetdb
    ```

## Graph

**Type:** Plugin<br>
**Status:** Disabled<br>
**Options:**<br>

- `graph.webRootPath` string
  - The path to the visualizer web assets
    Default:<br>
    ```json
    "IOTAtangle/webroot"
    ```
- `graph.webSocket.uri` string
  - The websocket URI to use (optional)
    Default:<br>
    ```json
    ""
    ```
- `graph.domain` string
  - Sets the domain name from which the visualizer is served from
    Default:<br>
    ```json
    ""
    ```
- `graph.bindAddress` string
  - The bind address from which the visualizer can be accessed from
    Default:<br>
    ```json
    "localhost:8083"
    ```
- `graph.networkName` string
  - The name of the network to be shown on the visualizer site
    Default:<br>
    ```json
    "meets HORNET"
    ```

## httpAPI

**Type:** Plugin<br>
**Status:** Enabled<br>
**Options:**<br>

- `httpAPI.bindAddress` string
  - The bind address on which the HTTP API listens on
    Default:<br>
    ```json
    "0.0.0.0:14265"
    ```
- `httpAPI.permitRemoteAccess` []string
  - The allowed HTTP API calls which can be called from non whitelisted addresses
    Default:<br>
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
    Default:<br>
    ```json
    []
    ```
- `httpAPI.basicAuth.enabled` bool
  - Whether to use HTTP basic auth for the HTTP API
    Default:<br>
    ```json
    false
    ```
- `httpAPI.basicAuth.username` string
  - The username of the HTTP basic auth
    Default:<br>
    ```json
    ""
    ```
- `httpAPI.basicauth.passwordhash` string
  - The HTTP basic auth password+salt as a sha256 hash (must be lower cased)
    Default:<br>
    ```json
    ""
    ```
- `httpAPI.basicauth.passwordsalt` string
  - The HTTP basic auth salt used for hashing the password (must be lower cased)
    Default:<br>
    ```json
    ""
    ```
- `httpAPI.limits.bodyLengthBytes` int
  - The maximum number of characters that the body of an API call may contain
    Default:<br>
    ```json
    1000000
    ```
- `httpAPI.limits.findTransactions` int
  - The maximum number of transactions that may be returned by the findTransactions endpoint
    Default:<br>
    ```json
    1000
    ```
- `httpAPI.limits.getTrytes` int
  - The maximum number of trytes that may be returned by the getTrytes endpoint
    Default:<br>
    ```json
    1000
    ```
- `httpAPI.limits.requestsList` int
  - The maximum number of parameters in an API call
    Default:<br>
    ```json
    1000
    ```

## Logger

**Type:** Setting<br>
**Status:** n.a.<br>
**Options:**<br>

- `logger.level` string
  - The minimum enabled logging level
    Default:<br>
    ```json
    "info"
    ```
- `logger.disableCaller` bool
  - Stops annotating logs with the calling function's file name and line number
    Default:<br>
    ```json
    true
    ```
- `logger.encoding` string

  - Sets the logger's encoding. Valid values are "json" and "console"
    Default:<br>
    ```json
    "console"
    ```

- `logger.outputPaths` []string

  - A list of URLs, file paths or stdout/stderr to write logging output to
    Default:<br>
    ```json
    ["stdout"]
    ```

- `logger.disableEvents` bool
  - Prevents log messages from being raced as events
    Default:<br>
    ```json
    false
    ```

## Milestones

**Type:** Setting<br>
**Status:** n.a.<br>
**Options:**<br>

- `milestones.coordinator` string
  - The address of the coordinator
    Default:<br>
    ```json
    "EQSAUZXULTTYZCLNJNTXQTQHOMOFZERHTCGTXOLTVAHKSA9OGAZDEKECURBRIXIJWNPFCQIOVFVVXJVD9"
    ```
- `milestones.coordinatorSecurityLevel` int
  - The security level used in coordinator signatures
    Default:<br>
    ```json
    2
    ```
- `milestones.numberOfKeysInAMilestone` int
  - The depth of the Merkle tree which in turn determines the number of leaves (private keys) that the coordinator can use to sign a message
    Default:<br>
    ```json
    23
    ```

## Monitor

**Type:** Plugin<br>
**Status:** Disabled<br>
**Options:**<br>

- `monitor.tangleMonitorPath` string
  - Path to the tanglemonitor web assets
    Default:<br>
    ```json
    "tanglemonitor/frontend"
    ```
- `monitor.domain` string
  - The domain from which the tanglemonitor is served from
    Default:<br>
    ```json
    ""
    ```
- `monitor.webSocket.uri` string
  - The websocket URI to use (optional)
    Default:<br>
    ```json
    ""
    ```
- `monitor.remoteAPIPort` int
  - The remote API port
    Default:<br>
    ```json
    4433
    ```
- `monitor.initialTransactionsCount` int
  - The initial amount of tx to load
    Default:<br>
    ```json
    15000
    ```
- `monitor.webBindAddress` string
  - The bind address on which the monitor can be access from
    Default:<br>
    ```json
    "localhost:4434"
    ```
- `monitor.apiBindAddress` string
  - The bind address on which the API listens on
    Default:<br>
    ```json
    "localhost:4433"
    ```

## MQTT

**Type:** Plugin<br>
**Status:** Disabled<br>
**Options:**<br>

- `mqtt.config` string
  - Path to the MQTT broker config file
    Default:<br>
    ```json
    "mqtt_config.json"
    ```

## Network

**Type:** Setting<br>
**Status:** n.a.<br>
**Options:**<br>

- `network.preferIPv6` bool
  - Defines if IPv6 is preferred for neighbors added through the APIDefines if IPv6 is preferred for neighbors added through the API
    Default:<br>
    ```json:
    false
    ```
- `network.gossip.bindAddress` string
  - The bind address of the gossip TCP server
    Default:<br>
    ```json
    "0.0.0.0:15600"
    ```
- `network.gossip.reconnectAttemptIntervalSeconds` int
  - The number of seconds to wait before trying to reconnect to a disconnected neighbor
    Default:<br>
    ```json
    60
    ```
- `network.autopeering.entryNodes` []string
  - List of autopeering entry nodes to use
    Default:<br>
    ```json
    ["LehlDBPJ6kfcfLOK6kAU4nD7B/BdR7SJhai7yFCbCCM=@enter.hornet.zone:14626"]
    ```
- `network.autopeering.bindAddress` string
  - Bind address for global services such as autopeering and gossip
    Default:<br>
    ```json
    "0.0.0.0:14626"
    ```
- `network.autopeering.externalAddress` string
  - External IP address under which the node is reachable; or 'auto' to determine it automatically
    Default:<br>
    ```json
    "auto"
    ```
- `network.autopeering.seed` string
  - Private key seed used to derive the node identity; optional Base64 encoded 256-bit string
    Default:<br>
    ```json
    ""
    ```
- `network.autopeering.runAsEntryNode` bool
  - Whether the node should act as an autopeering entry node
    Default:<br>
    ```json
    false
    ```

## Node

**Type:** Setting<br>
**Status:** n.a.<br>
**Options:**<br>

- `node.alias` string
  - Set an alias to identify your node
    Default:<br>
    ```json
    ""
    ```
- `node.showAliasInGetNodeInfo` string
  - Defines whether to show the alias in getNodeInfo
    Default:<br>
    ```json
    false
    ```
- `node.disablePlugins` []string
  - Disable plugins
    Default:<br>
    ```json
    []
    ```
- `node.enablePlugins` []string
  - Enable plugins
    Default:<br>
    ```json
    []
    ```

## Profile

**Type:** Setting<br>
**Status:** n.a.<br>
**Options:**<br>

- `useProfile` string
  - Which profile should be used
    Default:<br>
    ```json
    "auto"
    ```

## Profiling

**Type:** Setting<br>
**Status:** n.a.<br>
**Options:**<br>

- `profiling.bindAddress` string
  - The bind address on which the profiler listens on
    Default:<br>
    ```json
    "localhost:6060"
    ```

## Protocol

**Type:** Setting<br>
**Status:** n.a.<br>
**Options:**<br>

- `protocol.mwm` int
  - The minimum weight magnitude is the number of trailing 0s that must appear in the end of a transaction hash. Increasing this number by 1 will result in proof of work that is 3 times as hard
    Default:<br>
    ```json
    14
    ```

## Snapshots

**Type:** Setting<br>
**Status:** n.a.<br>
**Options:**<br>

- `snapshots.loadType` string
  - Which snapshot type to load. 'local' or 'global'
    Default:<br>
    ```json
    "local"
    ```
- `napshots.local.enabled` bool
  - Whether to do local snapshots
    Default:<br>
    ```json
    true
    ```
- `snapshots.local.depth` int
  - The depth, respectively the starting point, at which a local snapshot of the ledger is generated
    Default:<br>
    ```json
    50
    ```
- `snapshots.local.intervalSynced` int
  - Interval, in milestone transactions, at which snapshot files are created if the ledger is fully synchronized
    Default:<br>
    ```json
    50
    ```
- `snapshots.local.intervalUnsynced` int
  - Interval, in milestone transactions, at which snapshot files are created if the ledger is not fully synchronized
    Default:<br>
    ```json
    1000
    ```
- `snapshots.local.path` string
  - Path to the local snapshot file
    Default:<br>
    ```json
    "latest-export.gz.bin"
    ```
- `snapshots.global.path` string
  - Path to the global snapshot file containing the ledger state
    Default:<br>
    ```json
    "snapshotMainnet.txt"
    ```
- `snapshots.global.spentAddressesPath` []string
  - Paths to the spent addresses files
    Default:<br>
    ```json
    [
      "previousEpochsSpentAddresses1.txt",
      "previousEpochsSpentAddresses2.txt",
      "previousEpochsSpentAddresses3.txt"
    ]
    ```
- `snapshots.global.index` int
  - Milestone index of the global snapshot
    Default:<br>
    ```json
    1050000
    ```
- `snapshots.pruning.enabled` bool
  - Whether to delete old transaction data from the database
    Default:<br>
    ```json
    false
    ```
- `snapshots.pruning.delay` int
  - Amount of milestone transactions to keep in the database
    Default:<br>
    ```json
    40000
    ```

## Spammer

**Type:** Plugin<br>
**Status:** Disabled<br>
**Options:**<br>

- `spammer.address` string
  - The address you want to use (you don't have to own it as it's zero value spam)
    Default:<br>
    ```json
    "HORNET99INTEGRATED99SPAMMER999999999999999999999999999999999999999999999999999999"
    ```
- `spammer.message` string
  - The message you want to send with your spam (keep it short)
    Default:<br>
    ```json
    "Spamming with HORNET tipselect"
    ```
- `spammer.tag` string
  - The tag you want to use (can not be longer than 27 trytes [A-Z, 9])
    Default:<br>
    ```json
    "HORNET99SPAMMER999999999999"
    ```
- `spammer.depth` int
  - Depth for tip selection. Set it to `3` if you don't know what this is for.
    Default:<br>
    ```json
    3
    ```
- `spammer.tpsRateLimit` float
  - Defines how many transactions (TX) the spammer should try to send (e.g. `0.1` stands for 0.1 TX per second --> 1 TX every 10 seconds. **NOTE:** the maximum `tpsratelimit` is limited by your used hardware. Start with a lower value and slightly increase it, watch your CPU usage.
    Default:<br>
    ```json
    0.1
    ```
- `spammer.workers` int
  - Number of workers the spammer spins up --> Number of CPU cores you want to use (you should not use all available cores)
    Default:<br>
    ```json
    1
    ```

## SpentAddresses

**Type:** Setting<br>
**Status:** n.a.<br>
**Options:**<br>

- `spentAddresses.enabled` bool
  - Enable support for wereAddressesSpentFrom (needed for Trinity, but local snapshots are much bigger)
    Default:<br>
    ```json
    true
    ```

## Tipselection

**Type:** Setting<br>
**Status:** n.a.<br>
**Options:**<br>

- `tipsel.belowMaxDepthTransactionLimit` int
  - Number of tx to automatically flag them as below the max depth
    Default:<br>
    ```json
    20000
    ```
- `tipsel.maxDepth` int
  - Max. depth for tip selection
    Default:<br>
    ```json
    15
    ```

## ZeroMQ

**Type:** Plugin<br>
**Status:** Disabled<br>
**Options:**<br>

- `zmq.bindAddress` string
  - The bind address of the ZMQ feed
    Default:<br>
    ```json
    "localhost:5556"
    ```
- `zmq.protocol` string
  - Protocol used to connect to the zmq feed [unix, tcp, udp, inproc]
    Default:<br>
    ```json
    "tcp"
    ```
