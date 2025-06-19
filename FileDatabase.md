# FileDatabase.java Function Summary

## Class Overview

- __Total Functions__: 15

- __Constructor__: 1

- __Public Methods__: 8 (constructor, sync, add, has_changed, listFiles, count, save, load)

- __Private/Static Methods__: 7

- __Main Purpose__: File system synchronization and database management for tracking file changes

- __Key Features__:

  - File system monitoring and change detection
  - Cassandra and local database synchronization
  - Serializable file database storage
  - Multi-case file state handling (8 different scenarios)
  - Configurable delays and batch processing
  - Cross-platform file path handling
  - Comprehensive logging and error handling

- __Database Support__: Cassandra and local P2P database modes

- __File Operations__: Add, delete, update tracking with MD5 hashing

| Function Name | Lines of Code | Summary |
|---------------|---------------|---------|
| sync(String sNodeName, String sUUID) | 120 | Main synchronization method that compares local files with database and performs CRUD operations |
| loadBackupProps() | 25 | Loads backup configuration properties from www-rtbackup.properties file |
| FileDatabase(String _storage) | 12 | Constructor that initializes storage path, loads database, and sets up logging |
| connectCassandra(String _hostname) | 20 | Static method that establishes connection to Cassandra database with retry logic |
| checkfileCass(String _key, String _path, String _uuid) | 10 | Static method that checks if file exists in Cassandra or local database |
| checkfile(String sStorePath) | 20 | Static method that verifies if a file exists on the filesystem |
| loadDbModeProp() | 13 | Loads database mode configuration from www-server.properties file |
| log(String s) | 10 | Static method that writes timestamped log messages to file and console |
| save() | 12 | Synchronized method that serializes the file database to storage |
| load() | 18 | Method that deserializes the file database from storage |
| p(String s) | 4 | Static method that prints debug messages to stdout with thread ID |
| add(String _canonical_path, long _modified, String _md5) | 2 | Adds a new file entry to the database |
| has_changed(String _canonical_path, long _modified) | 7 | Checks if a file entry has been modified since last recorded |
| listFiles() | 2 | Returns the set of all file paths in the database |
| count() | 2 | Returns the number of entries in the database |