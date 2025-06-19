# BackupServerService.java Function Summary

| Function Name | Lines of Code | Summary |
|---------------|---------------|---------|
| `main_server()` | 158 | Main backup processing logic that handles batch jobs and updates database records |
| `checkGenFiles()` | 108 | Processes .gen files by creating backup files and cleaning up temporary files |
| `loadProps()` | 95 | Loads application configuration properties from www-rtbackup.properties file |
| `run()` | 65 | Main thread execution loop that monitors file counts and runs backup operations |
| `isBackupBatch(String _filename)` | 23 | Determines if a batch file belongs to a backup node by checking UUID |
| `BackupServerService(Boolean _dothread, int _loglevel)` | 17 | Constructor that initializes logging and optionally starts a new thread for backup operations |
| `loadPropsDB()` | 16 | Loads database configuration properties from www-processor.properties file |
| `connectCassandra()` | 16 | Establishes connection to Cassandra database with retry logic |
| `printProps()` | 15 | Prints all loaded configuration properties to console |
| `getNumberOfIncomingFiles()` | 12 | Counts the number of files in the incoming directory |
| `getNumberOfIDXFiles()` | 12 | Counts non-backup IDX files in the rtserver directory |
| `log(String s, int _loglevel)` | 12 | Writes timestamped log messages to file and console based on log level |
| `p(String s)` | 4 | Prints messages to stdout with thread ID prefix |
| `terminate()` | 4 | Sets termination flag to gracefully stop the backup service |

## Class Overview
- **Total Functions**: 14
- **Constructor**: 1
- **Public Methods**: 4 (constructor, terminate, run, checkGenFiles, main_server)
- **Private/Protected Methods**: 9
- **Main Purpose**: Automated backup service that processes batch jobs and manages file replication
- **Key Features**: Multi-threaded operation, Cassandra integration, configurable parameters, comprehensive logging
