# BroadcastService.java Function Summary

## Class Overview

- __Total Functions__: 7 (including inner class methods)
- __Constructor__: 1
- __Public Methods__: 3 (constructor, terminate, run)
- __Private Methods__: 3
- __Inner Classes__: 1 (RunProbeFromBroadcast with its own run method)
- __Main Purpose__: Network discovery service that broadcasts node presence and responds to discovery requests
- __Key Features__: UDP broadcasting, dual-threaded operation (sender and receiver), cluster identification, configurable ports


| Function Name | Lines of Code | Summary |
|---------------|---------------|---------|
| run() (inner class RunProbeFromBroadcast) | 85 | Listens for incoming broadcast packets and responds with node information |
| run() (main class) | 58 | Main broadcast loop that sends periodic network discovery packets |
| BroadcastService(String _signature) | 12 | Constructor that initializes node signature and starts two broadcast threads |
| loadProps() | 20 | Loads server configuration properties and retrieves cluster ID |
| getClusterID() | 5 | Retrieves the cluster UUID from data/clusterid file |
| p(String s) | 4 | Static method that prints messages to stdout with thread ID prefix |
| terminate() | 4 | Sets termination flag to gracefully stop the broadcast service |

