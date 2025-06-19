# BackupClientService

## Summary Statistics:

- __Total Functions:__ 22
- __Largest Function:__ `main_client()` with 485 lines
- __Smallest Function:__ `setSuffix()` and `terminate()` with 3 lines each
- __Average Function Size:__ ~55 lines
- __Total Lines of Code:__ ~1,210 lines (excluding class fields, imports, and comments)

| Function Name | Lines of Code | Summary |
|---------------|---------------|---------|
| main_client() | 485 | Main backup client logic that handles file synchronization and backup operations, processing batch files from server and managing local/remote file transfers. |
| processPendingFiles() | 145 | Processes files that were previously unable to be transferred, retrying downloads and managing the pending files queue. |
| BackupClientService() (Constructor) | 30 | Initializes the backup client service with configuration parameters, sets up logging, and optionally launches the processing thread. |
| run() | 28 | Main execution loop that loads pending files, discovers servers, processes backup operations, and manages periodic pending file processing. |
| loadProps() | 95 | Loads comprehensive configuration properties from backup config file including paths, delays, modes, and various operational settings. |
| getServerAddressPort() | 75 | Listens for UDP broadcast packets to discover backup server address and port, with retry logic and signature validation. |
| LoadNodes() | 45 | Downloads and parses node information from server, populating the NodeAddr HashMap with UUID to IP:port mappings. |
| getfile() | 25 | Downloads a file from a remote URL to local storage with retry logic, timeout handling, and temporary file management. |
| printProps() | 18 | Prints current configuration properties to console for debugging and verification purposes. |
| savePendingFiles() | 15 | Serializes the pending files HashMap to disk storage for persistence across service restarts. |
| loadPendingFiles() | 14 | Deserializes the pending files HashMap from disk storage into memory for processing. |
| fillMap() | 14 | Loads router configuration file to populate file extension to path mappings for sync operations. |
| checkfile() | 13 | Checks if a file exists at the specified path and has non-zero length. |
| checknode() | 8 | Extracts node information from URL and checks if the node is available for connection. |
| log() | 8 | Logs messages to both file and console with timestamp and log level filtering, using thread synchronization. |
| isNodeAvailable() | 8 | Tests network connectivity to a specific IP address and port using socket connection with timeout. |
| stripLeadingAndTrailingQuotes() | 8 | Utility method to remove leading and trailing quote characters from strings. |
| isHashFile() | 8 | Determines if a filename represents a hash file by checking for 32-character hexadecimal names. |
| printPendingFiles() | 6 | Prints all pending files in the HashMap to console for debugging purposes. |
| setSuffix() | 3 | Static utility method to add file extension mappings to the global map. |
| terminate() | 3 | Sets the termination flag and logs the shutdown request for graceful service shutdown. |
| p() | 4 | Utility method for printing messages to console with thread ID prefix for debugging. |