You can adapt HORNET to your needs. The configuration options are shown below.

## Index

- [Autopeering](#Autopeering)
- [Compass](#Compass)
- [Dashboard](#Dashboard)
- [DB](#DB)
- [Graph](#Graph)
- [Logger](#Logger)
- [Milestones](#Milestones)
- [Monitor](#Monitor)
- [MQTT](#MQTT)
- [Network](#Network)
- [Node](#Node)
- [Permaspent](#Permaspent)
- [Profile](#Profile)
- [Protocol](#Protocol)
- [Snapshot](#Snapshot)
- [Spammer](#Spammer)
- [Tipselection](#Tipselection)
- [WebAPI](#WebAPI)
- [ZeroMQ](#ZeroMQ)

## Autopeering

**Type:** Plugin
**Status:** Enabled
**Options:**

- `autopeering.entryNodes` []string
  - List of trusted entry nodes for auto peering
    Default:
    ```json
    ["zEiNuQMDfZ6F8QDisa1ndX32ykBTyYCxbtkO0vkaWd0=@159.69.9.6:18626"]
    ```
- `autopeering.port` int
  - UDP port for incoming peering requests
    Default:
    ```json
    14626
    ```
- `autopeering.seed` string
  - Private key seed used to derive the node identity; optional Base64 encoded 256-bit string
    Default:
    ```json
    ""
    ```
- `autopeering.actAsEntryNode` bool
  - Whether the node should act as an autopeering entry node
    Default:
    ```json
    false
    ```

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

## Dashboard

**Type:** Plugin
**Status:** Enabled
**Options:**

- `dashboard.bindAddress` string
  - Set the host to which the Dashboard listens
    Default:
    ```json
    "127.0.0.1"
    ```
- `dashboard.port` int
  - Set the port to which the Dashboard listens
    Default:
    ```json
    8081
    ```
- `dashboard.dev` bool
  - Activate the dashboard dev mode
    Default:
    ```json
    false
    ```
- `dashboard.basic_auth.enabled` bool
  - Whether to use HTTP Basic Auth
    Default:
    ```json
    true
    ```
- `dashboard.basic_auth.username` string
  - The HTTP Basic Auth username
    Default:
    ```json
    "hornet"
    ```
- `dashboard.basic_auth.password` string
  - The HTTP Basic Auth password
    Default:
    ```json
    "hornet"
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

- `graph.webrootPath` string
  - Path to IOTA Tangle Visualiser webroot files
    Default:
    ```json
    "IOTAtangle/webroot"
    ```
- `graph.socketioPath` string

  - Path to socket.io.js
    Default:
    ```json
    "socket.io-client/dist/socket.io.js"
    ```

- `graph.domain` string
  - Set the domain on which IOTA Tangle Visualiser is served
    Default:
    ```json
    ""
    ```
- `graph.bindAddress` string
  - Set the host to which the IOTA Tangle Visualiser listens
    Default:
    ```json
    "127.0.0.1"
    ```
- `graph.port` int
  - IOTA Tangle Visualiser webserver port
    Default:
    ```json
    8083
    ```
- `graph.networkName` string
  - Name of the network shown in IOTA Tangle Visualiser
    Default:
    ```json
    "meets HORNET"
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

- `monitor.TangleMonitorPath` string
  - Path to tanglemonitor frontend files
    Default:
    ```json
    "tanglemonitor/frontend"
    ```
- `monitor.domain` string
  - Set the domain on which TangleMonitor is served
    Default:
    ```json
    ""
    ```
- `monitor.bindAddress` string
  - Set the host to which the TangleMonitor listens
    Default:
    ```json
    "127.0.0.1"
    ```
- `monitor.port` int
  - TangleMonitor webserver port (do not change unless you redirect back to 4434)
    Default:
    ```json
    4434
    ```
- `monitor.apiPort` int
  - TangleMonitor API port (do not change unless you redirect back to 4433)
    Default:
    ```json
    4433
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

- `network.bindAddress` string
  - Bind address for global services such as [Autopeering](#Autopeering) and Gossip
    Default:
    ```json:
    "0.0.0.0"
    ```
- `network.port` int
  - Bind port for global services such as [Autopeering](#Autopeering) and Gossip
    Default:
    ```json
    15600
    ```
- `network.prefer_ipv6` bool

  - Defines if IPv6 is preferred for neighbors added through the API or [Autopeering](#Autopeering)
    Default:
    ```json
    false
    ```

- `network.externalAddress` string

  - External IP address under which the node is reachable; or 'auto' to determine it automatically
    Default:
    ```json
    "auto"
    ```

- `network.reconnectAttemptIntervalSeconds` int
  - Set the number of seconds to wait before trying to reconnect to a disconnected neighbor
    Default:
    ```json
    60
    ```

## Node

**Type:** Setting
**Status:** n.a.
**Options:**

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

## Permaspent

**Type:** Plugin
**Status:** Enabled
**Options:**

- `permaspent.nodes` []string
  - List of permaspent nodes
    Default:
    ```json
    ["https://permaspent.manapotion.io"]
    ```
- `permaspent.thresholds.noResponseTolerance` float
  - How many not responding nodes are allowed
    Default:
    ```json
    0.25
    ```
- `permaspent.thresholds.quorum` float
  - Quorum threshold
    Default:
    ```json
    0.65
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

- `loadSnapshot` string
  - Which snapshot to load 'local' or 'global'
    Default:
    ```json
    "local"
    ```
- `localSnapshots.enabled` bool
  - Enable local snapshots
    Default:
    ```json
    true
    ```
- `localSnapshots.depth` int
  - The depth, respectively the starting point, at which a local snapshot of the ledger is generated
    Default:
    ```json
    50
    ```
- `localSnapshots.intervalSynced` int
  - Interval, in milestone transactions, at which snapshot files are created if the ledger is fully synchronized
    Default:
    ```json
    50
    ```
- `localSnapshots.intervalUnsynced` int
  - Interval, in milestone transactions, at which snapshot files are created if the ledger is not fully synchronized
    Default:
    ```json
    1000
    ```
- `localSnapshots.path` string
  - Path to the local snapshot file
    Default:
    ```json
    "latest-export.gz.bin"
    ```
- `globalSnapshot.path` string
  - Path to the global snapshot file containing the ledger state
    Default:
    ```json
    "snapshotMainnet.txt"
    ```
- `globalSnapshot.index` int
  - Milestone index of the global snapshot
    Default:
    ```json
    1050000
    ```
- `pruning.enabled` bool
  - Whether to delete old transaction data from the database
    Default:
    ```json
    false
    ```
- `pruning.delay` int
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

## WebAPI

**Type:** Plugin
**Status:** Enabled
**Options:**

- `api.port` int
  - Set the port on which the API listens
    Default:
    ```json
    14265
    ```
- `api.bindAddress` string
  - Set the host to which the API listens
    Default:
    ```json
    "0.0.0.0"
    ```
- `api.permitRemoteAccess` []string
  - Allow remote access to certain API commands
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
- `api.auth.username` string
  - Basic authentication user name
    Default:
    ```json
    ""
    ```
- `api.auth.password` string
  - Basic authentication password
    Default:
    ```json
    ""
    ```
- `api.maxGetTrytes` int
  - Set a maximum number of trytes that may be returned by the getTrytes endpoint
    Default:
    ```json
    10000
    ```
- `api.maxRequestsList` int
  - Set a maximum number of parameters in an API call
    Default:
    ```json
    1000
    ```
- `api.maxFindTransactions` int
  - Set a maximum number of transactions that may be returned by the findTransactions endpoint
    Default:
    ```json
    100000
    ```
- `api.maxBodyLength` int
  - Set a maximum number of characters that the body of an API call may contain
    Default:
    ```json
    1000000
    ```

## ZeroMQ

**Type:** Plugin
**Status:** Disabled
**Options:**

- `zmq.protocol` string
  - Set the protocol used [unix, tcp, udp, inproc]
    Default:
    ```json
    "tcp"
    ```
- `zmq.bindAddress` string
  - Set the host
    Default:
    ```json
    "127.0.0.1"
    ```
- `zmq.port` int
  - Set the port
    Default:
    ```json
    5556
    ```
