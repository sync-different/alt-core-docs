# ZipFolder.java Function Summary

## Class Overview

- __Total Functions__: 6

- __Constructor__: 1

- __Public Methods__: 6 (all methods are public)

- __Private Methods__: 0

- __Main Purpose__: Utility class for creating and extracting ZIP archives from folders

- __Key Features__:

  - Recursive folder compression to ZIP format
  - ZIP file extraction with directory structure preservation
  - File name handling and path management
  - Error handling with exception catching
  - Support for nested folder structures
  - Buffer-based file I/O for efficiency

- __Use Cases__:

  - Backup and archival operations
  - File transfer preparation
  - Data compression for storage
  - Batch file processing

- __File Operations__: Read, write, compress, decompress with proper resource management

- __Error Handling__: Try-catch blocks with cleanup in finally blocks

| Function Name | Lines of Code | Summary |
|---------------|---------------|---------|
| unzipFile(String sourceZipFile, String destFolder) | 40 | Extracts all files from a ZIP archive to a destination folder |
| zipFolder(String srcFolder, String destZipFile) | 10 | Creates a ZIP archive from a source folder |
| addFileToZip(String path, String srcFile, ZipOutputStream zip) | 25 | Adds a single file or folder to an existing ZIP output stream |
| addFolderToZip(String path, String srcFolder, ZipOutputStream zip) | 15 | Recursively adds all files in a folder to a ZIP output stream |
| main(String[] a) | 10 | Test method that demonstrates zipping and unzipping functionality |
| ZipFolder() | 3 | Constructor that prints initialization message |
