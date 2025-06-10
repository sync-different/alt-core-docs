# alt-core-docs

## Core Services

The documentation for Alt core is organized by services.

### Client-side Services

Module | Component          | Description
------- | --------------    | -------------
Scrubber | ScannerService   | Scans for new/deleted/changes files in filesystem
Scrubber | ClientService    | Communication channel with Server via REST API
Scrubber | ProcessorService | Ingest metadata , add to local index

### Server-side Services

Module | Component          | Description
------- | --------------    | -------------
Scrubber | ProcessorService | Ingest metadata, add to main index
RTServer | WebServer        | HTTP Web Server for REST API

##High level sequence diagrams

### 1-ScannerService - File change detection and metadata extraction
[ScannerService](ScannerService.md)
