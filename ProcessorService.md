# ProcessorService

## Summary Statistics:

- __Total Functions:__ 34
- __Largest Function:__ `processFileRecordData_exp()` with 345 lines
- __Smallest Functions:__ `SetShutdown()`, `isWindows()`, `isHex()`, and `isNumeric()` with 3 lines each
- __Average Function Size:__ ~65 lines
- __Total Lines of Code:__ ~2,200 lines (excluding class fields, imports, and comments)


| Function Name | Lines of Code | Summary |
|---------------|---------------|---------|
| processFileRecordData_exp() | 345 | Processes file records for experimental/peer-to-peer database mode, handling file indexing, substring generation, hashtag creation, and thumbnail storage. |
| processFileRecordData_cass() | 285 | Processes file records for Cassandra database mode, inserting file metadata, creating search indexes, and managing batch operations. |
| ScanProcessingDir() | 180 | Scans the processing directory for files, handles ZIP extraction, mobile backup files, and processes database entries based on file types. |
| processDeleteFileRecordData_cass() | 85 | Handles deletion of file records from Cassandra database, removing paths and associating deleted files with batch operations. |
| processDeleteFileRecordData_p2p() | 85 | Handles deletion of file records from peer-to-peer database, managing batch IDs and updating deletion statistics. |
| addMobileBackupFolder() | 75 | Adds mobile backup folder paths to configuration files and handles cross-platform path resolution for backup directories. |
| addHashStrings() | 65 | Generates and inserts hash strings and substrings from file folder paths for search indexing and autocomplete functionality. |
| storeBatchInfo_exp() | 55 | Stores batch processing statistics and metadata in the experimental/peer-to-peer database system. |
| ProcessorService() (Constructor) | 54 | Initializes the ProcessorService with configuration parameters, loads properties, sets up logging, and starts the processing thread. |
| storeBatchInfo_cass() | 53 | Stores batch processing statistics and metadata in the Cassandra database system. |
| addMP3Info_exp() | 45 | Processes MP3 metadata (artist, title) for experimental database mode, creating searchable substrings and hashtags. |
| insert_remote_link() | 45 | Generates and inserts remote view and play links for files, handling URL creation for file access. |
| addMP3Info_cass() | 43 | Processes MP3 metadata (artist, title) for Cassandra database mode, creating searchable substrings and hashtags. |
| loadProps() | 42 | Loads processor configuration properties from www-processor.properties file, setting various processing parameters. |
| updateNumberOfCopies() | 35 | Updates the number of file copies by creating batch index files and managing file occurrence tracking. |
| filewrite64() | 32 | Writes file data as Base64 encoded content to a specified output file for thumbnail storage. |
| run() | 23 | Main processing loop that continuously scans directories, processes files, and manages batch operations until termination. |
| connectCassandra() | 22 | Establishes connection to Cassandra database server with retry logic and error handling. |
| loadBackupProps() | 21 | Loads backup-specific configuration properties from the specified config file path. |
| loadWebFuncs() | 17 | Initializes WebFuncs utility class with local IP address for web-based file operations. |
| log() | 17 | Logs messages to both file and console with timestamp and log level filtering. |
| storeBatchInfo() | 15 | Determines which database mode to use and delegates batch information storage accordingly. |
| filewrite() | 13 | Writes binary data to a file, typically used for saving thumbnails and other file content. |
| loadDelimiters() | 13 | Loads custom delimiter characters from configuration file for string tokenization during indexing. |
| isHashFile() | 12 | Determines if a filename represents a hash file by checking if it contains hexadecimal characters. |
| printProps() | 9 | Prints current configuration properties to console for debugging and verification purposes. |
| isLocalUUID() | 8 | Checks if a given UUID matches any of the local server UUIDs for identifying local files. |
| loadLocalUUID() | 8 | Loads multiple UUID values from different configuration files for local server identification. |
| terminate() | 5 | Sets the termination flag and logs the shutdown request for graceful service shutdown. |
| p() | 4 | Utility method for printing messages to console with thread ID prefix for debugging. |
| SetShutdown() | 3 | Sets the termination flag to true to stop the processing service. |
| isWindows() | 3 | Checks if the current operating system is Windows by examining system properties. |
| isHex() | 3 | Validates if a string contains only hexadecimal characters using regex pattern matching. |
| isNumeric() | 3 | Validates if a string contains only numeric characters using regex pattern matching. 