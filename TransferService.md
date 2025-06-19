# TransferService

## Summary Statistics:

- __Total Functions:__ 14
- __Largest Function:__ `ScanProcessingDir()` with 155 lines
- __Smallest Function:__ `printProps()` with 3 lines
- __Average Function Size:__ ~33 lines
- __Total Lines of Code:__ ~465 lines (excluding class fields, imports, and comments)


| Function Name | Lines of Code | Summary |
|---------------|---------------|---------|
| ScanProcessingDir() | 155 | Scans the processing directory for files, creates ZIP archives from database records, and transfers them to the server via HTTP POST or local file copy. |
| getServerAddressPort() | 75 | Listens for UDP broadcast packets to discover transfer server address and port with retry logic, signature validation, and random wait intervals. |
| run() | 45 | Main execution loop that loads configuration, discovers servers, scans processing directories, and manages periodic transfer operations. |
| TransferService() (Constructor) | 35 | Initializes the transfer service with scan directory, server connection parameters, loads configuration, sets up logging, and optionally launches the processing thread. |
| loadBackupProps() | 25 | Loads transfer-specific configuration properties including outgoing directory, UUID path, ZIP maximum size, and operational mode settings. |
| getConfig() | 20 | Utility method to read a specific property value from a given configuration file with error handling. |
| log() | 18 | Logs messages to both file and console with timestamp and log level filtering, using thread synchronization and null checking. |
| copyfile() | 15 | Copies a file from source to destination directory using buffered streams with error handling and cleanup. |
| loadServerProps() | 12 | Loads server properties from www-server.properties file, specifically extracting the local port configuration. |
| loadProps() | 10 | Loads scrubber properties from www-scrubber.properties configuration file. |
| printBackupProps() | 8 | Prints current transfer configuration properties to console for debugging and verification purposes. |
| terminate() | 5 | Sets the termination flag and logs the shutdown request for graceful service shutdown. |
| p() | 4 | Utility method for printing messages to console with thread ID prefix for debugging. |
| printProps() | 3 | Prints current outgoing directory configuration to console for debugging purposes. |