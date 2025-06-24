# Main workflow
**Steps**

1. User saves new file in local folder
2. File detected by ScannerService
3.	Metadata extracted from File
4. Metadata sent to RTServer
5. RTServer ingests metadata into Core Index
6. BackupServer creates replication order
7. Client fetches and executes replication order
8. File is replicated on Client
9. File detected by Client ScannerService
10. New file notification sent to Server

## Sequence Diagram

```mermaid
sequenceDiagram
    participant User as User/System
    participant FS as File System (/Users/)
    participant SCS as ScannerService
    participant PDF as PDFRenderer
    participant TS as TransferService
    participant Incoming as Incoming Directory
    participant RT as RTServer (localhost:8081)
    participant DB as Database (records.db)
    participant BSS as BackupServerService
    participant BCS as BackupClientService
    participant IncomingClient as Incoming Directory
    participant BO as BackupOrder Directory
    participant RTCS as RTServerCS (localhost:8081)
    participant DBCS as DatabaseCS (records.db)

    User->>FS: User saves new file in local folder
	 FS->>SCS: File detected
	 SCS->>PDF: Extract metadata from PDF
	 SCS->>TS: Store metadata in /outgoing
	 TS->>Incoming: Send files via HTTP to RTServer
	 Incoming->>RT: New files detected
	 RT->>DB: Store metadata in Core Index
	 BSS->>BO:  Create replication orders for clients
	 BO->>BCS: Fetch BackupOrder from Server
	 BCS->>IncomingCS: Execute replication, fetch & store files 
	 IncomingCS->>RTCS: New files detected (client side)
	 RTCS->>DBCS: Store metadata in Local Index
    
```
