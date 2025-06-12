# alt-core-docs

Alt documentation is organized into these key sections:

* 1-Core services: Description of client, server, and cloud services. Click [here](#core-services)
* 2-Data Layer: Data layer where all data is persisted. Click [here](#data-layer)
* 3-Configuration Files: Description of config files. Click [here](#config-files)
* 4-Sequence Diagrams: Diagrams that describe key user case sequences. Click [here](#diagrams)

## <a name="core-services"></a>1-Core Services

The services are divided into 3 categories:

* **client-side** : services that run on a client node
* **server-side** : services that run on a server node
* **cloud** : services that run on a cloud node (e.g. relay HTTP traffic) 

### Client-side Services

These services run on a client node.

Module   | Component           | Description
---------| --------------      | -------------
Scrubber | [ScannerService](ScannerService.md)           | Scans for new/deleted/changes files in filesystem
Scrubber | [ScrubService](ScrubService.md)               | Extract metadata from files
Scrubber | [ClientService](ClientService.md)             | Find Server IP, Send Ping to Server
Scrubber | [ProcessorService](ProcessorService.md)       | Ingest metadata , add to local client index
Scrubber | [TransferService](TransferService.md)         | Package metadata into ZIP files, transfer to server
Scrubber | [BackupClientService](BackupClientService.md) | Process replication orders from server

### Server-side Services

These services run on a server node.

Module      | Component           | Description
----------- | -----------------   | -------------
Scrubber    | BroadcastService                        | Broadcast Server IP address (discovered by Client)
Scrubber    | [ProcessorService](ProcessorService.md) | Ingest metadata, add to main index
Scrubber    | BackupServerService                     | Generate backup orders for clients
Scrubber    | RelayVaultService                       | Communicaton to/from Relay Server (for traffic relay)
RTServer    | WebServer                               | HTTP Web Server for REST API
CloudBackup | AmazonDrive                             | Synchronize files with Amazon S3 bucket
Mailer      | Mailer                                  | Communication with Email mailbox

### Cloud Services

These services run on a cloud node (e.g VM on a Public Cloud such as Amazon, Azure, or GCP)

Module    | Component             | Description
--------- | --------------        | -------------
Relay     | RelayService          | Relay HTTP/API requests from clients to server

## <a name="data-layer"></a>2-Data Layer

### DB records
* **records.db** : Stores records for each file in the system - MD5, file paths, timestamps
* **testdb** : Search Index (files and their metadata)

### LocalDB
* **localdb/Standard1** : Metadata for a specific file (filename = MD5)
* **localdb/NodeInfo**  : Information about a client node (ID, time last seen, free space available, IP Address)
* **localdb/BatchJobs** : Information about a batch job (filename = Batch ID): Number of files, # of metadata inserts
* **localdb/BackupJobs** : Replication orders for each client node (what files to distribute in each client)


## <a name="config-files"></a>3-Config Files

## <a name="diagrams"></a>4-Sequence Diagrams

### 1-ScrubberService
[ScrubberService](ScrubberService.md)

### 2-RTServerService
[RTServerService](RTServerService.md)
