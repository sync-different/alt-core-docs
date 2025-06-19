# RelayVaultService.java Function Summary

## Class Overview

- __Total Functions__: 24 (including inner class methods)
- __Constructor__: 1 main + 2 inner class constructors
- __Public Methods__: 5 (constructor, terminate, isRunning, unregister, run)
- __Private Methods__: 16
- __Inner Classes__: 2 (ClusterDelegate, RelayBridge)
- __Main Purpose__: Relay service that bridges local cluster operations with remote relay server
- __Key Features__: HTTP client operations, JSON request processing, authentication token management, file streaming, long-polling

| Function Name | Lines of Code | Summary |
|---------------|---------------|---------|
| processRequests() | 58 | Long-polling loop that retrieves and processes pending requests from the relay bridge |
| processRequest(String strRequest) | 158 | Parses JSON requests and dispatches them to appropriate cluster operations |
| run() | 50 | Main service loop that handles cluster registration and starts request processing |
| fileRequestNetty(...) | 48 | Handles media file requests (video/audio) through Netty server with URL construction |
| standardRequest(...) | 32 | Executes standard HTTP requests against the local cluster RT server |
| loginRequest(...) | 31 | Handles user authentication requests with cookie management |
| registerCluster(String clusterId, String clusterName) | 50 | Registers cluster with relay bridge and retrieves authentication token |
| fileRequest(...) | 21 | Processes file download requests from the local cluster |
| httpLocalRequest(...) | 23 | Creates and executes HTTP GET requests to local cluster with error handling |
| postStringResponse(...) | 19 | Sends async string responses back to the relay bridge |
| postFileResponse(...) | 17 | Sends async file responses back to the relay bridge |
| postErrorResponse(...) | 16 | Sends error responses back to the relay bridge when requests fail |
| unregisterCluster(...) | 28 | Unregisters cluster from relay bridge and cleans up authentication |
| RelayVaultService(...) | 12 | Main constructor that initializes all service parameters |
| ClusterDelegate(String host, String port) | 4 | Inner class constructor for cluster operations wrapper |
| RelayBridge(...) | 9 | Inner class constructor for relay bridge API wrapper |
| cleanTokenFile() | 16 | Clears the cluster authentication token file |
| log(String s, int _loglevel) | 12 | Writes timestamped log messages to file and console |
| unregister() | 7 | Public method to unregister cluster and clean token file |
| terminate() | 6 | Sets termination flag and stops bridge operations |
| isRunning() | 12 | Checks if the relay bridge is actively processing requests |
| running() | 12 | Checks if bridge received requests within timeout period |
| stop() | 4 | Stops the bridge request poller |
| p(String s) | 4 | Prints debug messages to stdout with thread ID |