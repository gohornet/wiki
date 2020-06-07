HORNETs functionality is extended by plugins. The available plugins are listed here.  
Plugins can be (de-)activated in your [`config.json`](./Configuration#node)

## Index

- [Autopeering](#Autopeering)
- [Coordinator](#Coordinator)
- [Dashboard](#Dashboard)
- [Graph](#Graph)
- [Monitor](#Monitor)
- [MQTT](#MQTT)
- [Prometheus](#Prometheus)
- [Spammer](#Spammer)
- [WarpSync](#WarpSync)
- [WebAPI](#WebAPI)
- [ZMQ](#ZMQ)

## Autopeering

**Status:** Enabled
**Description:** Searches for peers and manages them.
**Settings**: [link](./Configuration#network)
**How-To**: n.a.

## Coordinator

**Status:** Disabled
**Description:** Runs a coordinator for a private testnet.
**Settings**: [link](./Configuration#coordinator)
**How-To**: [link](./Tutorials%3A-Private-Tangle)

## Dashboard

**Status:** Enabled
**Description:** Runs a dashboard to monitor the node.
**Settings**: [link](./Configuration#Dashboard)
**How-To**: n.a.

## Graph

**Status:** Disabled
**Description:** Runs a [Glumb](https://github.com/glumb/IOTAtangle) tangle viewer.
**Settings**: [link](./Configuration#Graph)
**How-To**: n.a.

## Monitor

**Status:** Disabled
**Description:** Runs a [TangleMonitor](https://github.com/unioproject/tanglemonitor).
**Settings**: [link](./Configuration#Monitor)
**How-To**: n.a.

## MQTT

**Status:** Disabled
**Description:** Runs an MQTT broker.
**Settings**: [link](./Configuration#MQTT)
**How-To**: n.a.

## Prometheus

**Status:** Disabled
**Description:** Runs a Prometheus exporter which will export node and peering stats.
**Settings**: [link](./Configuration#Prometheus)
**How-To**: n.a.

## Spammer

**Status:** Disabled
**Description:** Runs a spammer which will issue zero value transactions.
**Settings**: [link](./Configuration#Spammer)
**How-To**: n.a.

## WarpSync

**Status:** Enabled
**Description:** Enables warp sync to speed up the syncing process.
**Settings**: n.a.
**How-To**: n.a.

## WebAPI

**Status:** Enabled
**Description:** Runs an API server to be able to interact with the node.
**Settings**: [link](Configuration#httpAPI)
**How-To**: n.a.

## ZMQ

**Status:** Disabled
**Description:** Runs an ZMQ publisher.
**Settings**: [link](Configuration#zmq)
**How-To**: n.a.
