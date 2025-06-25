# RTServer

## Project Summary

__rtserver__ is the core server component of the Alterante platform. 

### Technical Architecture:

- Core HTTP1.1 protocol implementation (HTTP/GET, HTTP/POST, Cookies, User-Agent)
- Core REST API handler
- Uses Cassandra or MapDB for metadata storage
- Netty framework for high-performance networking
- Base64 encoding for file path obfuscation
- AES and RSA Encryption for End-To-End-Encryption sessions
- Supports both Windows and Unix-like filesystems

The system essentially allows users to create their own personal Dropbox-like service on their hardware, with the added benefits of complete privacy control, multi-node support, and extensive customization options.

### Class Summary

**javaapplication1**

| Class Name | Lines of Code | Description |
|------------|---------------|-------------|
| [WebServer](WebServer.md) | 11,458 | Core HTTP server handling all web requests, authentication, file operations, and configuration |
| HtmlFromJSON | 1,335 | Converts JSON data to HTML for displaying files, tags, and search results in the web interface |
| Base64 | 574 | Base64 encoding/decoding utility for converting binary data to text format |
| Main | 450 | Application entry point that starts the HTTP server and handles basic requests |
| CryptLib | 387 | Encryption/decryption library implementing AES encryption with MD5/SHA256 hashing |
| MultiClusterManager | 331 | Manages connections to multiple remote Alterante clusters for distributed file access |
| RemoteAccess | 271 | Handles remote API calls to other Alterante servers for distributed operations |
| Home | 229 | Generates HTML content for the home dashboard including alerts, network status, and file scans |
| RSACrypto | 202 | RSA encryption implementation for secure key exchange and authentication |
| UserSession | 124 | User session management with UUID tokens and encryption parameters |
| StatHat | 114 | Analytics integration for sending usage statistics to StatHat and Google Analytics |
| MultiClusterUser | 95 | Data model representing a user in a multi-cluster environment |

**netty**

| Class Name | Lines of Code | Description |
|------------|---------------|-------------|
| HttpStaticFileServerHandler | 593 | Request handler for static file serving with authentication and file streaming |
| HttpUploadServerHandler | 355 | Request handler for processing multipart file uploads |
| HttpUploadServer | 75 | Netty-based file upload server for handling large file uploads |
| HttpStaticFileServer | 62 | Netty-based static file server implementation for high-performance file serving |
| HttpUploadServerInitializer | 52 | Netty channel pipeline initializer for upload server |
| HttpStaticFileServerInitializer | 30 | Netty channel pipeline initializer for static file server |
