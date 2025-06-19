# ScannerService

## Summary Statistics:

- __Total Functions:__ 10
- __Largest Function:__ `run()` with 135 lines
- __Smallest Function:__ `p()` with 4 lines
- __Average Function Size:__ ~34 lines
- __Total Lines of Code:__ ~344 lines (excluding class fields, imports, and comments)


| Function Name | Lines of Code | Summary |
|---------------|---------------|---------|
| run() | 135 | Main execution loop that handles setup state checking, file scanning, deleted file detection, memory management, and periodic scrubbing operations. |
| getServerAddressPort() | 75 | Listens for UDP broadcast packets to discover server address and port, validating signatures and updating connection information. |
| ScannerService() (Constructor) | 35 | Initializes the scanner service with configuration parameters, sets up logging, and optionally launches the scanning thread. |
| loadBackupProps() | 32 | Loads configuration properties from backup config file including UUID path, scrub counts, debug mode, and scan directories. |
| getConfig() | 20 | Utility method to read a specific property value from a given configuration file. |
| log() | 15 | Logs messages to both file and console with timestamp and log level filtering, using thread synchronization. |
| cleanup() | 14 | Cleans up resources by setting all member variables to null for garbage collection. |
| printProps() | 9 | Prints current configuration properties to console for debugging and verification purposes. |
| terminate() | 5 | Sets the termination flag and logs the shutdown request for graceful service shutdown. |
| p() | 4 | Utility method for printing messages to console with thread ID prefix for debugging. |