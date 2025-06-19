# DatabaseEntry.java Function Summary


## Class Overview

- __Total Functions__: 6

- __Constructors__: 2 (one for NEW files, one for DELETE files)

- __Public Methods__: 2 constructors + 3 static utility methods

- __Private Methods__: 1

- __Main Purpose__: File metadata extraction and database entry creation for indexing system

- __Key Features__:

  - Image thumbnail generation (photos, PDFs)
  - MP3/M4A metadata extraction (artist, title, album art)
  - Document keyword extraction (DOC, DOCX)
  - PDF thumbnail generation
  - File type detection and processing
  - Memory management and exception handling

- __File Types Supported__: Images (JPG, PNG, GIF), Audio (MP3, M4A), Documents (PDF, DOC, DOCX)

- __External Libraries__: JAudioTagger, Thumbnailator, PDFView, Apache POI

| Function Name | Lines of Code | Summary |
|---------------|---------------|---------|
| DatabaseEntry(String _md5, UUID _uuid, File _file, float _thumbnail_compression, long _delay) | 340 | Main constructor that processes files and extracts metadata, thumbnails, and keywords |
| toByteArray(BufferedImage _image, String _format_name, float _compression) | 25 | Static method that converts BufferedImage to compressed byte array |
| copyfile(File _src_file, File _dst_file) | 17 | Static method that copies a file from source to destination |
| close(InputStream c) | 7 | Static utility method that safely closes an InputStream |
| DatabaseEntry(String _md5, UUID _uuid, String _filePath) | 6 | Constructor for creating DELETE action database entries |
| is_photo(String _string) | 9 | Private method that checks if file extension indicates a photo format |