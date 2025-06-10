# **Scrubber**

Here's a sequence diagram for the Scrubber project based on the codebase analysis:

![Sequence Diagram](scrubber_sequence_diagram.jpg)

This sequence diagram illustrates the Scrubber project's main workflow:

1. **Initialization**: ScrubberService starts as a threaded service
2. **Continuous Processing**: Runs in a loop until terminated
3. **File Discovery**: Scans specified directories for files to process
4. **File Processing**: Handles different file types (audio, PDF, images) with specialized libraries
5. **Data Management**: Stores metadata in a local database and manages file transfers
6. **Integration**: Communicates with RTServer and performs cloud backups
7. **Configuration**: Uses property files to control processing behavior

The system appears to be designed for automated file processing, metadata extraction, and backup operations with real-time server integration.

```mermaid
sequenceDiagram
    participant User as User/System
    participant SS as ScrubberService
    participant Main as Main Class
    participant DB as Database (records.db)
    participant FS as File System (/Users/)
    participant RT as RTServer (localhost:8081)
    participant Incoming as Incoming Directory
    participant Config as Configuration
    participant CB as CloudBackup
    participant Thumb as Thumbnailator
    participant Audio as JAudioTagger
    participant PDF as PDFRenderer

    User->>SS: Initialize ScrubberService
    SS->>SS: Create new Thread("scrubber")
    SS->>SS: Start thread execution
    
    loop Continuous Processing (while !terminated)
        SS->>Main: Create Main instance
        SS->>Main: Call main() with args
        Note over SS,Main: Args: ["data/records.db", "localhost", "8081", "/Users/", "../rtserver/incoming", "macprd", "config/www-rtbackup.properties"]
        
        Main->>Config: Load www-rtbackup.properties
        Config-->>Main: Configuration loaded
        
        Main->>DB: Connect to records.db
        DB-->>Main: Database connection established
        
        Main->>RT: Connect to RTServer (localhost:8081)
        RT-->>Main: Server connection established
        
        Main->>FS: Scan /Users/ directory
        FS-->>Main: File list returned
        
        loop For each file found
            Main->>Main: Process file based on type
            
            alt Audio File
                Main->>Audio: Extract metadata with JAudioTagger
                Audio-->>Main: Audio metadata
            else PDF File
                Main->>PDF: Render/process with PDFRenderer
                PDF-->>Main: PDF processed
            else Image File
                Main->>Thumb: Generate thumbnail with Thumbnailator
                Thumb-->>Main: Thumbnail created
            end
            
            Main->>DB: Store file metadata/record
            DB-->>Main: Record stored
            
            Main->>Incoming: Move/copy file to incoming directory
            Incoming-->>Main: File transferred
            
            Main->>CB: Backup to cloud storage
            CB-->>Main: Backup completed
            
            Main->>RT: Notify RTServer of new file
            RT-->>Main: Notification acknowledged
        end
        
        Main->>Config: Apply processor settings
        Note over Main,Config: minsubstr=4, maxstrlen=50, autocomplete=true, etc.
        
        Main->>DB: Commit changes (based on commit_timer/commit_puts)
        DB-->>Main: Changes committed
        
        Main-->>SS: Processing cycle complete
        
        alt Exception occurs
            Main->>SS: Throw exception
            SS->>SS: Print stack trace
            SS->>SS: Continue loop (restart processing)
        end
    end
    
    User->>SS: Terminate service
    SS->>SS: Set mTerminated = true
    SS->>SS: Exit run loop
```