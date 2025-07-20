# Multi-Threaded Proxy Server with Cache

This project implements a multi-threaded proxy server in C with an LRU (Least Recently Used) cache mechanism. The proxy server listens for client requests, forwards them to the target server, and caches the responses for future requests to improve performance.

## Features
- Multi-threaded handling of client connections
- LRU cache for storing server responses
- Thread-safe cache operations using mutexes and semaphores
- Handles HTTP GET requests

## How It Works
- When a client requests a URL for the first time, the proxy fetches the data from the remote server and stores it in the cache.
- On subsequent requests for the same URL, the proxy retrieves the data directly from the cache, reducing latency and network usage.
- The cache uses an LRU eviction policy to manage memory usage efficiently.

## Example Output
Below is a screenshot demonstrating the cache behavior:
<img width="2204" height="1511" alt="Image" src="https://github.com/user-attachments/assets/5936a21e-d0c4-4190-b5c5-f4d2008364d0" />

- **Initially:** When a URL is requested for the first time, the output shows `url not found` (cache miss).
- **Subsequent Request:** The same URL is found in the cache (`url found`), and the data is retrieved from the cache (`Data retrived from the Cache`).

## Usage
1. Build the project using the provided `Makefile`:
   ```sh
   make
   ```
2. Run the proxy server:
   ```sh
   ./proxy 8080
   ```
3. Configure your client to use the proxy at `localhost:8080`.

## File Overview
- `proxy_server_with_cache.c`: Main proxy server implementation with cache logic
- `proxy_parse.c/h`: HTTP request parsing utilities
- `Makefile`: Build instructions

---

Feel free to explore and modify the code to suit your needs! 
