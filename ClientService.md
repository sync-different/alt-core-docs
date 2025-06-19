# ClientService

## Summary Statistics:

- __Total Functions:__ 14
- __Largest Function:__ `run()` with 125 lines
- __Smallest Function:__ `printProps()` with 3 lines
- __Average Function Size:__ ~31 lines
- __Total Lines of Code:__ ~437 lines (excluding class fields, imports, and comments)


| Function Name | Lines of Code | Summary |
|---------------|---------------|---------|
| run() | 125 | Main execution loop that handles server discovery, configuration loading, client registration, and periodic communication with the backup server. |
| setnode() | 65 | Registers the client node with the backup server by sending node information including UUID, IP address, backup status, and free space via HTTP request. |
| getServerAddressPortProbe() | 60 | Listens for UDP broadcast packets to discover backup server address and port with retry logic, signature validation, and random wait intervals. |
| UpdateConfig() | 45 | Static utility method to update or create configuration properties in a specified config file with value comparison and file creation logic. |
| ClientService() (Constructor) | 25 | Initializes the client service with server connection parameters, loads configuration, sets up logging, and optionally launches the processing thread. |
| getServerAddressPort() | 25 | Determines local IP address and either initiates server discovery via probe or falls back to loopback mode, then updates server configuration. |
| loadBackupProps() | 25 | Loads backup-specific configuration properties including backup paths, sync paths, UUID path, and node settings from the config file. |
| getLastID() | 20 | Reads the last processed batch and sequence IDs from the lastid.tmp file for backup synchronization tracking. |
| loadProps() | 15 | Loads server properties from www-server.properties file, specifically extracting the local port configuration. |
| log() | 12 | Logs messages to both file and console with timestamp and log level filtering, using thread synchronization. |
| printBackupProps() | 8 | Prints current backup configuration properties to console for debugging and verification purposes. |
| terminate() | 5 | Sets the termination flag and logs the shutdown request for graceful service shutdown. |
| p() | 4 | Static utility method for printing messages to console with thread ID prefix for debugging. |
| printProps() | 3 | Prints current local port configuration to console for debugging purposes. |