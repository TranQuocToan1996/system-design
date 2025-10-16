**Origin requiments :**

Implement a Node.js service that demonstrates the use of streams and file handling. The service should read a large text file, compress it, and save the compressed file to disk.

**Requirements:**

*   Create an HTTP server using the http module that listens on port 3000.
    
*   When a request is received on the endpoint /compress, the server should read a specified large text file, compress it using a suitable compression algorithm, and save the compressed file to the disk.
    
*   The server should handle large files efficiently using streams to prevent high memory usage.
    

**Performance Measures:**

*   Correctness: The server must correctly compress and save the file.




----
**My assumption to implement :**
*   Max size: 4Gb each file
*   Storage: Use multipart upload to sign-URL S3 instead save on disk
*   Async compression after upload to S3
*   Infra: Assume use AWS
*   Skip authenticate and authoziration for simple
*   Assume the user will download the upload files which is compressed.


