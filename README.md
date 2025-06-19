# Introduction

Alterante is a decentralized filesystem.

For a general overview of Alterante and what it does, start with [FAQ](https://www.hivebot.co/faq.html) first.

In a nutshell, Alterante has 3 main capabilities:

* **Discovery & Organization** - Decentralized Search engine for all files accross all machines. Indexing includes deep metadata extraction for PDF, JPG, MP3, etc.
* **Data Protection** - Automated sync/backup/replication for all files, using free space available on all machines
* **Access** - Access to all files from any browser or mobile device using secure E2E encrypted channels between devices

# Terminology

A **node** is a unit of compute+storage, which runs on a computer (Win, Mac, Linux).
There are 2 two types of nodes - **clients** and **servers**. 

A **cluster** is a collection of **nodes**, with at least 1 **server**.

A **server** node has the following responsibilites:

* keeps track of all **nodes** on the **cluster** and free space available
* keep a centralized index of all the metadata accross all the **nodes**
* create replication orders for each **node**
* index all files and make them available to the API layer
* manage settings for the **cluster** (admin and user settings)

A **client** node has the following responsilibites:

* regularly ping the **server** to inform about uptime, IP, and free space
* extract metadata from files
* index all local files and make them available to API layer
* execute the replication orders issued by the **server**
* transfer metadata to the **server**

# Overview

Alt documentation is organized into these key sections:

* 1- **Core services**: Description of client, server, and cloud services. Click [here](#core-services)
* 2- **Data Layer**: Data layer where all data is persisted. Click [here](#data-layer)
* 3- **Configuration Files**: Description of config files. Click [here](#config-files)
* 4- **Sequence Diagrams**: Diagrams that describe key user case sequences. Click [here](#diagrams)

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
Scrubber    | [BackupServerService](BackupServerService.md)                     | Generate backup orders for clients
Scrubber    | RelayVaultService                       | Communicaton to/from Relay Server (for traffic relay)
RTServer    | [WebServer](WebServer.md)                               | HTTP Web Server for REST API
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
