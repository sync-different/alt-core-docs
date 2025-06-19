# FfmpegExecutor.java Function Summary

## Class Overview

- __Total Functions__: 3

- __Constructor__: None (uses default constructor)

- __Public Methods__: 1 (execute)

- __Private Methods__: 2 (getCommandWin, getCommandMac)

- __Main Purpose__: Cross-platform FFmpeg wrapper for video processing and streaming preparation

- __Key Features__:

  - Video transcoding to HLS format (m3u8 + ts segments)
  - Thumbnail generation from video files
  - Cross-platform support (Windows/Mac)
  - Template-based command construction
  - Process execution with logging
  - Error stream handling
  - Script generation for Mac execution

- __Output Formats__: HLS streaming (m3u8 playlist + TS segments), JPEG thumbnails

- __Platform Handling__: Separate logic for Windows (ProcessBuilder) and Mac (shell script execution

| Function Name | Lines of Code | Summary |
|---------------|---------------|---------|
| execute(File _input, String _md5, String _outputfolderPath, String _projectsFolderPath, boolean _isWindows) | 130 | Main method that executes FFmpeg commands for video processing and thumbnail generation |
| getCommandWin(String _ffmpegFile, String _projectsFolderPath, File ffmpegexeFile, File _input, File outputm3u8File, String _md5, File outputtsFile, File outputthumbnailFile) | 25 | Builds Windows-specific FFmpeg command arguments from template file |
| getCommandMac(String _projectsFolderPath, File ffmpegexeFile, File _input, File outputm3u8File, String _md5, File outputtsFile, File outputthumbnailFile) | 14 | Builds Mac-specific FFmpeg command string from template file |
