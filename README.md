# alt-core-docs

## Core Services

The documentation for Alt core is organized by services.

The services are divide into 3 categories:

* **client-side** : services that run on client node
* **server-side** : services that run on a server node
* **cloud** : services that run on a cloud node (relay traffic) 

### Client-side Services

Module  | Component           | Description
---------| --------------      | -------------
Scrubber | ScannerService      | Scans for new/deleted/changes files in filesystem
Scrubber | ScrubService        | Extract metadata from files
Scrubber | ClientService       | Communication channel with Server via REST API
Scrubber | ProcessorService    | Ingest metadata , add to local index
Scrubber | TransferService     | Package metadata into ZIP files, transfer to server
Scrubber | BackupClientService | Process replication orders from server

### Server-side Services

Module | Component             | Description
----------- | -----------------   | -------------
Scrubber    | BroadcastService    | Ingest metadata, add to main index
Scrubber    | ProcessorService    | Ingest metadata, add to main index
Scrubber    | BackupServerService | Generate backup orders for clients
Scrubber    | RelayVaultService   | Communicaton to/from Relay Server (for traffic relay)
RTServer    | WebServer           | HTTP Web Server for REST API
CloudBackup | AmazonDrive         | Synchronize files with Amazon S3 bucket
Mailer      | Mailer              | Communication with Email mailbox

### Cloud Services

Module    | Component             | Description
--------- | --------------        | -------------
Relay     | RelayService          | Relay API requests from clients to server

## High level sequence diagrams

### 1-ScrubberService
[ScrubberService](ScrubberService.md)
