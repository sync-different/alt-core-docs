# FileUtils.java Function Summary

## Class Overview

- __Total Functions__: 27

- __Constructors__: 2 (default + parameterized)

- __Public Methods__: 15

- __Private/Static Methods__: 12

- __Main Purpose__: Comprehensive file system scanner and indexer with database synchronization

- __Key Features__:

  - Recursive directory scanning with configurable delays
  - MD5 hash calculation (dual methods: Java native + Apache Commons)
  - File change detection and database synchronization
  - Blacklist/whitelist filtering system
  - Video file processing with FFmpeg integration
  - Cross-platform support (Windows/Mac/Unix)
  - Memory management and OOM handling
  - Configurable file type support
  - Thumbnail generation integration
  - Comprehensive logging with levels

- __File Operations__: Add, update, delete tracking with metadata extraction

- __Database Integration__: Serializable file database with pending file management

- __Performance__: Configurable batch processing, sleep intervals, and memory optimization

| Function Name | Lines of Code | Summary |
|---------------|---------------|---------|
| ScanDirectory(String _sPath, Boolean _checkMD5) | 250 | Main recursive directory scanner that processes files and generates database entries |
| FileUtils(String _path, Boolean _debugmode, String _configpath, int _loglevel) | 40 | Constructor that initializes file scanner with configuration and logging |
| ScanDeletedFiles(boolean _bWindowsServer) | 50 | Scans for deleted files in database and generates delete entries |
| loadBackupProps() | 35 | Loads configuration properties from backup properties file |
| saveDatabaseEntry(DatabaseEntry dbe, String _type) | 25 | Saves database entry objects to outgoing directory for processing |
| calcMD5_1(String _filename) | 35 | Java-based MD5 calculation method using MessageDigest |
| calcMD5_2(String _filename) | 10 | Apache Commons-based MD5 calculation method |
| isBlacklistedContains(String _filepath) | 25 | Checks if filepath contains blacklisted directory patterns |
| isBlacklisted(String _filepath, boolean _isdirectory) | 30 | Checks if filepath matches exact blacklisted directory paths |
| savePendingFiles() | 15 | Synchronized method that serializes file database to storage |
| loadPendingFiles() | 20 | Loads serialized file database from storage into memory |
| IsNodeAvailable(String _sPath, boolean _bWindowsServer) | 25 | Checks if network path or volume is available for scanning |
| calcMD5(String _filename) | 10 | Main MD5 calculation method that delegates to specific implementation |
| loadBlacklistMap() | 15 | Static method that loads blacklist patterns from configuration file |
| loadBlacklistContainsMap() | 15 | Static method that loads contains-based blacklist patterns |
| loadFileExtensions() | 15 | Static method that loads supported file extensions from configuration |
| log(String s, int _loglevel) | 12 | Writes timestamped log messages with level filtering |
| checkFileType(String _filename) | 10 | Checks if file extension is supported for processing |
| is_video(String _string) | 8 | Checks if file extension indicates a video format |
| isBlacklisted2(String _directory) | 15 | Legacy blacklist checking method with hardcoded patterns |
| cleanup() | 15 | Memory cleanup method that clears data structures |
| FileUtils() | 2 | Default constructor |
| p(String s) | 6 | Prints timestamped debug messages to stdout |
| pdebug(String s) | 5 | Prints debug messages only when debug mode is enabled |
| printFileCount() | 6 | Returns the number of entries in the file database |
| close(InputStream c) | 6 | Static utility method to safely close input streams |
| close_out(OutputStream c) | 6 | Static utility method to safely close output streams |