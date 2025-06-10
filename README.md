# alt-core-docs

## Core Services

The documentation for Alt core is organized by services.

### Client-side Services

Module | Component          | Description
------- | --------------    | -------------
Scrubber | ScannerService   | Scans for new/deleted/changes files in filesystem
Scrubber | ClientService    | Communication channel with Server via REST API
Scrubber | ProcessorService | Parse documents, Adds metadata to local index

### Server-side Services

Module | Component          | Description
------- | --------------    | -------------
Scrubber | ProcessorService | Adds files to central index
RTServer | WebServer        | HTTP Web Server for REST API

##High level sequence diagram

[scrubber](scrubber.md)
