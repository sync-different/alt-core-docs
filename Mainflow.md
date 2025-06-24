```mermaid
sequenceDiagram
    participant User as User/System
    participant FS as File System (/Users/)
    participant ScaS as ScrubberService
    participant TS as TransferService
    participant DB as Database (records.db)
    participant RT as RTServer (localhost:8081)
    participant Incoming as Incoming Directory
    participant Config as Configuration
    participant CB as CloudBackup
    participant Thumb as Thumbnailator
    participant Audio as JAudioTagger
    participant PDF as PDFRenderer

    User->>FS: User saves new file in local folder
	 FS->>ScaS: File detected
	 SCaS-TS: New files detected and scanned, stored in /outgoing
	 TS->>RT: Send files via HTTP to RTServer	 RT->>DB: Index files
    
```