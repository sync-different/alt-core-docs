# alt-core-docs

* Core services: click [here](#core-services)
* Data Layer: click [here](#data-layer)
* Configuration Files: click [here](#config-files)
* Sequence Diagrams: click [here](#diagrams)

## <a name="core-services"></a>Core Services

The documentation for Alt core is organized by services.

The services are divided into 3 categories:

* **client-side** : services that run on a client node
* **server-side** : services that run on a server node
* **cloud** : services that run on a cloud node (e.g. relay HTTP traffic) 

### Client-side Services

These services run on a client node.

Module  | Component           | Description
---------| --------------      | -------------
Scrubber | ScannerService      | Scans for new/deleted/changes files in filesystem
Scrubber | ScrubService        | Extract metadata from files
Scrubber | ClientService       | Communication channel with Server via HTTP/REST API
Scrubber | ProcessorService    | Ingest metadata , add to local index
Scrubber | TransferService     | Package metadata into ZIP files, transfer to server
Scrubber | BackupClientService | Process replication orders from server

### Server-side Services

These services run on a server node.

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

These services run on a cloud node (e.g VM on a Public Cloud such as Amazon, Azure, or GCP)

Module    | Component             | Description
--------- | --------------        | -------------
Relay     | RelayService          | Relay HTTP/API requests from clients to server

## <a name="data-layer"></a>Data Layer

### DB records
* **records.db** : Stores records for each file in the system - MD5, file paths, timestamps
* **testdb** : Search Index (files and their metadata)

### LocalDB
* **localdb/Standard1** : Metadata for a specific file (filename = MD5)
* **localdb/NodeInfo**  : Information about a client node (ID, time last seen, free space available, IP Address)
* **localdb/BatchJobs** : Information about a batch job (filename = Batch ID): Number of files, # of metadata inserts
* **localdb/BackupJobs** : Replication orders for each client node (what files to distribute in each client)


## <a name="config-files"></a>Config Files

## <a name="diagrams"></a>Sequence Diagrams

### 1-ScrubberService
[ScrubberService](ScrubberService.md)

### 2-RTServerService
[RTServerService](RTServerService.md)
