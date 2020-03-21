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

**Type:** Setting
**Status:** n.a.
**Options:**

- `compass.loadLSMIAsLMI` bool
  - Set LSM as LSMI if enabled
    Default:
    ```json
    false
    ```

## Config

**Type:** Setting
**Status:** n.a.
**Options:**

- `config` string
  - Filename of the config file without the file extension
    Default:
    ```json
    "config"
    ```
- `config-dir` string
  - Path to the directory containing the config file
    Default:
    ```json
    "."
    ```
- `neighborsconfig` string
  - Filename of the neighbors config file without the file extension
    Default:
    ```json
    "."
    ```
- `profilesconfig` string
  - Filename of the profiles config file without the file extension
    Default:
    ```json
    "profiles"
    ```

## Dashboard

**Type:** Plugin
**Status:** Enabled
**Options:**

- `dashboard.bindAddress` string
  - The bind address on which the dashboard can be access from
    Default:
    ```json
    "localhost:8081"
    ```
- `dashboard.dev` bool
  - Whether to run the dashboard in dev mode
    Default:
    ```json
    false
    ```
- `dashboard.theme` string
  - The theme for the dashboard to use (default or dark)
    Default:
    ```json
    "default"
    ```
- `dashboard.basicAuth.enabled` bool
  - Whether to use HTTP basic auth
    Default:
    ```json
    false
    ```
- `dashboard.basicAuth.username` string
  - The HTTP Basic Auth username
    Default:
    ```json
    ""
    ```
- `dashboard.basicAuth.passwordhash` string
  - The HTTP basic auth password+salt as a sha256 hash (must be lower cased)
    Default:
    ```json
    ""
    ```
- `dashboard.basicAuth.passwordsalt` string
  - The HTTP basic auth salt used for hashing the password (must be lower cased)
    Default:
    ```json
    ""
    ```

## DB

**Type:** Setting
**Status:** n.a.
**Options:**

- `db.path` string
  - Path to the database folder
    Default:
    ```json
    mainnetdb
    ```

## Graph

**Type:** Plugin
**Status:** Disabled
**Options:**

- `graph.webRootPath` string
  - The path to the visualizer web assets
    Default:
    ```json
    "IOTAtangle/webroot"
    ```
- `graph.webSocket.uri` string
  - The websocket URI to use (optional)
    Default:
    ```json
    ""
    ```
- `graph.domain` string
  - Sets the domain name from which the visualizer is served from
    Default:
    ```json
    ""
    ```
- `graph.bindAddress` string
  - The bind address from which the visualizer can be accessed from
    Default:
    ```json
    "localhost:8083"
    ```
- `graph.networkName` string
  - The name of the network to be shown on the visualizer site
    Default:
    ```json
    "meets HORNET"
    ```

## httpAPI

**Type:** Plugin
**Status:** Enabled
**Options:**

- `httpAPI.bindAddress` string
  - The bind address on which the HTTP API listens on
    Default:
    ```json
    "0.0.0.0:14265"
    ```
- `httpAPI.permitRemoteAccess` []string
  - The allowed HTTP API calls which can be called from non whitelisted addresses
    Default:
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
    Default:
    ```json
    []
    ```
- `httpAPI.basicAuth.enabled` bool
  - Whether to use HTTP basic auth for the HTTP API
    Default:
    ```json
    false
    ```
- `httpAPI.basicAuth.username` string
  - The username of the HTTP basic auth
    Default:
    ```json
    ""
    ```
- `httpAPI.basicauth.passwordhash` string
  - The HTTP basic auth password+salt as a sha256 hash (must be lower cased)
    Default:
    ```json
    ""
    ```
- `httpAPI.basicauth.passwordsalt` string
  - The HTTP basic auth salt used for hashing the password (must be lower cased)
    Default:
    ```json
    ""
    ```
- `httpAPI.limits.bodyLengthBytes` int
  - The maximum number of characters that the body of an API call may contain
    Default:
    ```json
    1000000
    ```
- `httpAPI.limits.findTransactions` int
  - The maximum number of transactions that may be returned by the findTransactions endpoint
    Default:
    ```json
    1000
    ```
- `httpAPI.limits.getTrytes` int
  - The maximum number of trytes that may be returned by the getTrytes endpoint
    Default:
    ```json
    1000
    ```
- `httpAPI.limits.requestsList` int
  - The maximum number of parameters in an API call
    Default:
    ```json
    1000
    ```

## Logger

**Type:** Setting
**Status:** n.a.
**Options:**

- `logger.level` string
  - The minimum enabled logging level
    Default:
    ```json
    "info"
    ```
- `logger.disableCaller` bool
  - Stops annotating logs with the calling function's file name and line number
    Default:
    ```json
    true
    ```
- `logger.encoding` string

  - Sets the logger's encoding. Valid values are "json" and "console"
    Default:
    ```json
    "console"
    ```

- `logger.outputPaths` []string

  - A list of URLs, file paths or stdout/stderr to write logging output to
    Default:
    ```json
    ["stdout"]
    ```

- `logger.disableEvents` bool
  - Prevents log messages from being raced as events
    Default:
    ```json
    false
    ```

## Milestones

**Type:** Setting
**Status:** n.a.
**Options:**

- `milestones.coordinator` string
  - The address of the coordinator
    Default:
    ```json
    "EQSAUZXULTTYZCLNJNTXQTQHOMOFZERHTCGTXOLTVAHKSA9OGAZDEKECURBRIXIJWNPFCQIOVFVVXJVD9"
    ```
- `milestones.coordinatorSecurityLevel` int
  - The security level used in coordinator signatures
    Default:
    ```json
    2
    ```
- `milestones.numberOfKeysInAMilestone` int
  - The depth of the Merkle tree which in turn determines the number of leaves (private keys) that the coordinator can use to sign a message
    Default:
    ```json
    23
    ```

## Monitor

**Type:** Plugin
**Status:** Disabled
**Options:**

- `monitor.tangleMonitorPath` string
  - Path to the tanglemonitor web assets
    Default:
    ```json
    "tanglemonitor/frontend"
    ```
- `monitor.domain` string
  - The domain from which the tanglemonitor is served from
    Default:
    ```json
    ""
    ```
- `monitor.webSocket.uri` string
  - The websocket URI to use (optional)
    Default:
    ```json
    ""
    ```
- `monitor.remoteAPIPort` int
  - The remote API port
    Default:
    ```json
    4433
    ```
- `monitor.initialTransactionsCount` int
  - The initial amount of tx to load
    Default:
    ```json
    15000
    ```
- `monitor.webBindAddress` string
  - The bind address on which the monitor can be access from
    Default:
    ```json
    "localhost:4434"
    ```
- `monitor.apiBindAddress` string
  - The bind address on which the API listens on
    Default:
    ```json
    "localhost:4433"
    ```

## MQTT

**Type:** Plugin
**Status:** Disabled
**Options:**

- `mqtt.config` string
  - Path to the MQTT broker config file
    Default:
    ```json
    "mqtt_config.json"
    ```

## Network

**Type:** Setting
**Status:** n.a.
**Options:**

- `network.preferIPv6` bool
  - Defines if IPv6 is preferred for neighbors added through the APIDefines if IPv6 is preferred for neighbors added through the API
    Default:
    ```json:
    false
    ```
- `network.gossip.bindAddress` string
  - The bind address of the gossip TCP server
    Default:
    ```json
    "0.0.0.0:15600"
    ```
- `network.gossip.reconnectAttemptIntervalSeconds` int
  - The number of seconds to wait before trying to reconnect to a disconnected neighbor
    Default:
    ```json
    60
    ```
- `network.autopeering.entryNodes` []string
  - List of autopeering entry nodes to use
    Default:
    ```json
    ["LehlDBPJ6kfcfLOK6kAU4nD7B/BdR7SJhai7yFCbCCM=@enter.hornet.zone:14626"]
    ```
- `network.autopeering.bindAddress` string
  - Bind address for global services such as autopeering and gossip
    Default:
    ```json
    "0.0.0.0:14626"
    ```
- `network.autopeering.externalAddress` string
  - External IP address under which the node is reachable; or 'auto' to determine it automatically
    Default:
    ```json
    "auto"
    ```
- `network.autopeering.seed` string
  - Private key seed used to derive the node identity; optional Base64 encoded 256-bit string
    Default:
    ```json
    ""
    ```
- `network.autopeering.runAsEntryNode` bool
  - Whether the node should act as an autopeering entry node
    Default:
    ```json
    false
    ```

## Node

**Type:** Setting
**Status:** n.a.
**Options:**

- `node.alias` string
  - Set a alias to identify your node
    Default:
    ```json
    ""
    ```
- `node.showAliasInGetNodeInfo` string
  - Defines whether to show the alias in getNodeInfo
    Default:
    ```json
    false
    ```
- `node.disablePlugins` []string
  - Disable plugins
    Default:
    ```json
    []
    ```
- `node.enablePlugins` []string
  - Enable plugins
    Default:
    ```json
    []
    ```

## Profile

**Type:** Setting
**Status:** n.a.
**Options:**

- `useProfile` string
  - Which profile should be used
    Default:
    ```json
    "auto"
    ```

## Profiling

**Type:** Setting
**Status:** n.a.
**Options:**

- `profiling.bindAddress` string
  - The bind address on which the profiler listens on
    Default:
    ```json
    "localhost:6060"
    ```

## Protocol

**Type:** Setting
**Status:** n.a.
**Options:**

- `protocol.mwm` int
  - The minimum weight magnitude is the number of trailing 0s that must appear in the end of a transaction hash. Increasing this number by 1 will result in proof of work that is 3 times as hard
    Default:
    ```json
    14
    ```

## Snapshot

**Type:** Setting
**Status:** n.a.
**Options:**

- `snapshots.loadType` string
  - Which snapshot type to load. 'local' or 'global'
    Default:
    ```json
    "local"
    ```
- `napshots.local.enabled` bool
  - Whether to do local snapshots
    Default:
    ```json
    true
    ```
- `snapshots.local.depth` int
  - The depth, respectively the starting point, at which a local snapshot of the ledger is generated
    Default:
    ```json
    50
    ```
- `snapshots.local.intervalSynced` int
  - Interval, in milestone transactions, at which snapshot files are created if the ledger is fully synchronized
    Default:
    ```json
    50
    ```
- `snapshots.local.intervalUnsynced` int
  - Interval, in milestone transactions, at which snapshot files are created if the ledger is not fully synchronized
    Default:
    ```json
    1000
    ```
- `snapshots.local.path` string
  - Path to the local snapshot file
    Default:
    ```json
    "latest-export.gz.bin"
    ```
- `snapshots.global.path` string
  - Path to the global snapshot file containing the ledger state
    Default:
    ```json
    "snapshotMainnet.txt"
    ```
- `snapshots.global.spentAddressesPath` []string
  - Paths to the spent addresses files
    Default:
    ```json
    [
      "previousEpochsSpentAddresses1.txt",
      "previousEpochsSpentAddresses2.txt",
      "previousEpochsSpentAddresses3.txt"
    ]
    ```
- `snapshots.global.index` int
  - Milestone index of the global snapshot
    Default:
    ```json
    1050000
    ```
- `snapshots.pruning.enabled` bool
  - Whether to delete old transaction data from the database
    Default:
    ```json
    false
    ```
- `snapshots.pruning.delay` int
  - Amount of milestone transactions to keep in the database
    Default:
    ```json
    40000
    ```

## Spammer

**Type:** Plugin
**Status:** Disabled
**Options:**

- `spammer.address` string
  - The address you want to use (you don't have to own it as it's zero value spam)
    Default:
    ```json
    "HORNET99INTEGRATED99SPAMMER999999999999999999999999999999999999999999999999999999"
    ```
- `spammer.message` string
  - The message you want to send with your spam (keep it short)
    Default:
    ```json
    "Spamming with HORNET tipselect"
    ```
- `spammer.tag` string
  - The tag you want to use (can not be longer than 27 trytes [A-Z, 9])
    Default:
    ```json
    "HORNET99SPAMMER999999999999"
    ```
- `spammer.depth` int
  - Depth for tip selection. Set it to `3` if you don't know what this is for.
    Default:
    ```json
    3
    ```
- `spammer.tpsRateLimit` float
  - Defines how many transactions (TX) the spammer should try to send (e.g. `0.1` stands for 0.1 TX per second --> 1 TX every 10 seconds. **NOTE:** the maximum `tpsratelimit` is limited by your used hardware. Start with a lower value and slightly increase it, watch your CPU usage.
    Default:
    ```json
    0.1
    ```
- `spammer.workers` int
  - Number of workers the spammer spins up --> Number of CPU cores you want to use (you should not use all available cores)
    Default:
    ```json
    1
    ```

## SpentAddresses

**Type:** Setting
**Status:** n.a.
**Options:**

- `spentAddresses.enabled` bool
  - Enable support for wereAddressesSpentFrom (needed for Trinity, but local snapshots are much bigger)
    Default:
    ```json
    true
    ```

## Tipselection

**Type:** Setting
**Status:** n.a.
**Options:**

- `tipsel.belowMaxDepthTransactionLimit` int
  - Number of tx to automatically flag them as below the max depth
    Default:
    ```json
    20000
    ```
- `tipsel.maxDepth` int
  - Max. depth for tip selection
    Default:
    ```json
    15
    ```

## ZeroMQ

**Type:** Plugin
**Status:** Disabled
**Options:**

- `zmq.bindAddress` string
  - The bind address of the ZMQ feed
    Default:
    ```json
    "localhost:5556"
    ```
- `zmq.protocol` string
  - Protocol used to connect to the zmq feed [unix, tcp, udp, inproc]
    Default:
    ```json
    "tcp"
    ```
