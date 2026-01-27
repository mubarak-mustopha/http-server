# http-server
An HTTP server that handles GET requests

---

## Features
- **File Request:**
  - Serves the content of any generic file
- **Directory Request:**
  - Serves an `index.html` file in the requested directory
  - Otherwise, serves an HTML file containing href links to the directory contents
- **Proxy:**
  - Directs traffic between clients and a given server

---

## Build Instructions
```bash
make
```

Running `make` produces:
- `httpserver`: a single-threaded HTTP server program
- `forkserver`: multi-process server that forks a process to handle each request
- `threadserver`: multi-threaded server that spawns a thread to handle each request
- `poolserver`: multi-threaded server using producer-consumer pattern; main thread enqueues incoming client requests and spawns worker threads (configurable via `num-threads`) to handle requests

---

## Usage
```bash
./httpserver
Please specify either "--files [DIRECTORY]" or 
                      "--proxy [HOSTNAME:PORT]"
Usage: ./httpserver --files some_directory/ [--port 8000 --num-threads 5]
       ./httpserver --proxy inst.eecs.berkeley.edu:80 [--port 8000 --num-threads 5]
```

### Example Interactive Sessions

**Basic Server:**

https://github.com/user-attachments/assets/a1060434-0458-4b8c-b0cb-f97bc7160d42

**Proxy:**

https://github.com/user-attachments/assets/9e273f8b-9c06-401b-b428-ce746b408d39

---

## Acknowledgements
- Based on skeleton code from **UC Berkeley CS162** coursework
