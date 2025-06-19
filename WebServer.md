# WebServer.java Function Analysis

| Function Name | Lines of Code | Summary |
|---------------|---------------|---------|
| handleClient() | 2,847 | Main request handler that processes HTTP GET/POST requests, handles authentication, file operations, and various web endpoints |
| main(String[] a) | 154 | Application entry point that initializes the server, loads configurations, starts worker threads, and accepts client connections |
| loadProps() | 147 | Loads server configuration properties from www-server.properties file including ports, timeouts, logging, and various server settings |
| printHeaders(File, PrintStream, boolean, String, boolean, String, boolean, String, String, boolean, String, String, String, String, boolean, int, String, String) | 146 | Generates and sends HTTP response headers including content type, authentication cookies, and CORS headers |
| GetScanDirectories(String) | 145 | Retrieves and formats scan directory configurations from backup properties files for the web interface |
| updateFrompage2(String) | 144 | Updates configuration settings from setup wizard page 2 including scan modes, backup paths, and blacklist management |
| GetFileExtensions() | 143 | Generates HTML form elements for file extension selection in the setup wizard interface |
| updateFrompage8() | 142 | Updates configuration settings from setup wizard page 8 including backup/sync modes and directory paths |
| getNodeInfo() | 141 | Generates JSON response containing detailed information about all nodes in the cluster including status and statistics |
| applytag(String, WebFuncs, String) | 140 | Processes tag application/removal operations on files including hidden tags and share token creation |
| sendFile(File, PrintStream) | 139 | Streams file content to client with chunked transfer and error handling |
| processPost(PrintStream, int) | 138 | Parses HTTP POST request data and extracts file uploads and form parameters |
| GetEmailInfo(String) | 137 | Populates email configuration form fields with current SMTP/POP3 settings from properties |
| updateFromPage1() | 136 | Updates configuration settings from setup wizard page 1 including server mode, signatures, and user accounts |
| sharepage(String, WebFuncs, FileOutputStream, boolean) | 135 | Generates the shares management page with current share configurations and user interface |
| getNavbarMenu(boolean, String, String, boolean, boolean) | 134 | Generates navigation menu HTML based on user authentication status and permissions |
| openFile(String, boolean, String, boolean) | 133 | Opens files or directories using OS-specific commands (Windows Explorer, Mac Finder, etc.) |
| printHeadersRedirect(File, PrintStream, String, boolean, boolean, String, boolean) | 132 | Sends HTTP redirect response and triggers file/directory opening on the client system |
| run() | 131 | Worker thread main loop that handles client socket connections and delegates to handleClient() |
| loadPropsMailer() | 130 | Loads email server configuration from www-mailer.properties including SMTP/POP3 settings |
| getAlteranteServers() | 129 | Discovers and returns list of available Alterante servers on the network |
| createInvitationModal(ShareToken) | 128 | Generates HTML modal dialog for sharing files/folders with invitation links and email options |
| getSharesTableContent(boolean) | 127 | Generates HTML table content showing current shares with edit/remove actions |
| fillMap() | 126 | Populates MIME type mappings for file extensions used in HTTP Content-Type headers |
| getExtensions() | 125 | Generates JSON response containing all supported file extensions organized by category |
| send_tls2(String, String, String, String, String, String, String, String, String) | 124 | Sends email with attachment using TLS/SMTP authentication |
| GetEmailDomainsInfo(String) | 123 | Generates JavaScript code for auto-configuring email settings based on domain detection |
| getnodesfn() | 122 | Returns HTML option elements for node selection dropdowns in the web interface |
| StoreFileExtensions(String) | 121 | Saves selected file extensions from setup wizard to configuration file |
| GetConfig(String, String) | 120 | Retrieves configuration value from specified properties file |
| UpdateConfig(String, String, String) | 119 | Updates configuration property in specified file with new value |
| getComputerName() | 118 | Determines computer name from environment variables or network hostname |
| loadPropsAnalytics() | 117 | Loads analytics configuration for Google Analytics and StatHat integration |
| loadPropsCloud() | 116 | Loads cloud storage configuration settings from www-cloud.properties |
| GetSyncDirectories(String) | 115 | Retrieves sync directory configuration for specified backup node |
| GetBackupDirectories(String) | 114 | Retrieves backup directory configuration for specified backup node |
| GetBlackList(String) | 113 | Loads blacklisted directories from configuration file for specified node |
| printProps() | 112 | Logs all loaded configuration properties to console and log file |
| read_config(String, String, String) | 111 | Reads configuration file and generates HTML form for editing properties |
| write_config(String) | 110 | Parses form submission and writes updated configuration to properties file |
| sendFilePartial(File, PrintStream, int, int) | 109 | Sends partial file content for HTTP range requests |
| loadFileStr(File) | 108 | Reads entire file content into a string |
| getVersion() | 107 | Retrieves application version from update files |
| findtag(String) | 106 | Extracts tag information from URL parameters |
| printHeadersPost(File, PrintStream) | 105 | Generates HTTP response headers for POST requests |
| send404(File, PrintStream) | 104 | Sends HTTP 404 Not Found response |
| fixName(String) | 103 | Determines if filename needs Content-Disposition header for browser downloads |
| PrintStateInfo() | 102 | Returns HTML describing current setup wizard state |
| isUUIDValid(String) | 101 | Validates user session UUID against active session map |
| sendFilePost(File, PrintStream) | 100 | Sends file content in response to POST request |
| send404_1(File, PrintStream) | 99 | Alternative 404 error response method |
| listDirectory(File, PrintStream) | 98 | Generates HTML directory listing for folder browsing |
| get_vault_file(int, String) | 97 | Retrieves files from vault storage using socket communication |
| storeFile(File, InputStream) | 96 | Saves incoming file stream to specified file location |
| getLocalAddress() | 95 | Discovers local non-loopback IP address for network communication |
| LoadAccounts(String) | 94 | Loads user accounts from file and returns HTML option elements |
| LoadAccountsWithGroups(String) | 93 | Loads accounts with group associations and generates JavaScript arrays |
| LoadAccountsInArray() | 92 | Loads accounts into JavaScript array format |
| LoadGroupsWithAccounts() | 91 | Loads email groups with associated accounts for JavaScript |
| GetMailGroups() | 90 | Retrieves list of configured email groups |
| LoadMailGroups() | 89 | Generates HTML checkboxes for email group selection |
| LoadSyncRules(String, String) | 88 | Loads synchronization rules from file and formats for display |
| replaceSpecialCharacters(String) | 87 | Converts special characters to HTML entities |
| CheckBlacklistedDirectories(WebFuncs, String, String) | 86 | Validates directories against blacklist configuration |
| GetNumberofFilesInDir(String, String) | 85 | Counts files in directory matching optional filter criteria |
| getAlteranteServerURL(String) | 84 | Resolves server name to HTTP URL for communication |
| isPathInFile(String, String) | 83 | Checks if specified path exists in configuration file |
| CheckIPValid_Server(String) | 82 | Validates IP address against known server signatures |
| CheckIPValid(String) | 81 | Validates IP address against registered cluster nodes |
| isPathBackup(String, String) | 80 | Determines if path is configured as backup location |
| CheckPathValid(String) | 79 | Validates if file path is in allowed scan or backup directories |
| getFileMD5(String) | 78 | Retrieves MD5 hash for specified filename from database |
| getFileExtension(String) | 77 | Extracts file extension from filename |
| isUserAdmin(String) | 76 | Checks if authenticated user has administrator privileges |
| validIP(String) | 75 | Validates IP address format using regex pattern |
| getClusterID() | 74 | Retrieves unique cluster identifier from configuration |
| getClusterToken() | 73 | Retrieves cluster authentication token from file |
| isValidMultiClusterID(String) | 72 | Validates if cluster ID represents remote cluster |
| AddInbox(String) | 71 | Adds inbox directory to scan configuration for email processing |
| setAppendage() | 70 | Sets application path variables for macOS app bundle structure |
| loadPropsProcessor() | 69 | Loads image processing configuration from scrubber properties |
| setSuffix(String, String) | 68 | Helper method to populate MIME type mappings |
| load_setup_props() | 67 | Loads setup wizard state from configuration file |
| UpdateConfigProp(String, String, String) | 66 | Updates single configuration property in specified file |
| Worker() | 65 | Constructor for worker thread handling client connections |
| setSocket(Socket) | 64 | Assigns client socket to worker thread for processing |
| serviceRequest(int) | 63 | Handles Windows service control requests |
| serviceMain(String[]) | 62 | Main method for Windows service execution |
| p(String) | 61 | Prints debug messages to console with thread ID |
| log(String, int) | 60 | Writes timestamped log messages to file and console |
