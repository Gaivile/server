# Server
Implementation of web server that knows how to serve static content (i.e., files ending in .html, .jpg, et al.) and dynamic content (i.e., files ending in .php).

<b>CS50 Problem Set 6</b>

Usage: ./server [-p port] /path/to/root

Listens for HTTP requests on specified port number (default is 8080 - if not specified). The program enters infinite while loop to first free any previously allocated memory, then checks for SIGINT to stop the server; if the client is connected, parses HTTP request storing its "absolute path" and "query" inside of two arrays that are passed into it by reference. The path is then decoded into local path to show the exact file requested on the server:

<li><ul><b>For directories </b>(that don't have index file) shows the list of directory's contents;</ul></li>
<li><ul><b>For files ending in .php </b>interprets it's content, loads the output into memory and responds to the browser with (dynamically generated) output;</ul></li>
<li><ul><b>For other (supported) files </b>transfers file's content from the server to the client by loading it into memory and responding to the browser.</ul></li>


Handles and responds to most errors accordingly before listening to new requests.

