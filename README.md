# Simple Single-Threaded Client-Server in Java

This project demonstrates a **basic single-threaded client-server architecture** using Java **sockets**. The **server** listens for incoming connections, and the **client** connects to the server, exchanges messages, and disconnects.

---

## How It Works

### 1. Server
- Starts a **ServerSocket** on port **8010**.
- Waits for a **client connection**.
- When a client connects:
  - Prints the client’s address.
  - Sends a **"Hello World"** message to the client.
  - Closes the connection.

### 2. Client
- Connects to the server on **localhost:8010**.
- Sends a **"Hello World"** message.
- Reads the response from the server.
- Closes the connection.

---

## Project Structure
```
/SingleThreaded
│── Client.java  # Client-side code
│── Server.java  # Server-side code
```

---

## How to Run

### Step 1: Compile the Code
```sh
javac Server.java Client.java
```

### Step 2: Start the Server
```sh
java Server
```
The server will start and wait for client connections.

### Step 3: Start the Client
In a **new terminal**, run:
```sh
java Client
```
The client will send a message and receive a response.

---

## Example Output

### Server Output
```
Server is listening on port: 8010
Connected to /127.0.0.1
```

### Client Output
```
Received from server: Hello World from the server
```

---


# Multi-Threaded Client-Server in Java

This project demonstrates a **multi-threaded client-server model** using Java **sockets**. The **server** listens for client connections and spawns a new thread for each client request. The **client** starts multiple threads to connect to the server concurrently.

---

## How It Works

### 1. Server
- Starts a **ServerSocket** on port **8010**.
- Waits for **client connections**.
- When a client connects:
  - Prints the client’s address.
  - Sends a **"Hello from server"** message.
  - Spawns a new thread to handle each client connection.

### 2. Client
- Spawns **100 threads**, each creating a separate client connection.
- Connects to the server on **localhost:8010**.
- Sends a **"Hello from Client"** message.
- Reads the response from the server.
- Closes the connection.

---

## Project Structure
```
/MultiThreaded
│── Client.java  # Multi-threaded client code
│── Server.java  # Multi-threaded server code
```

---

## How to Run

### Step 1: Compile the Code
```sh
javac Server.java Client.java
```

### Step 2: Start the Server
```sh
java Server
```
The server will start and wait for client connections.

### Step 3: Start the Client
In a **new terminal**, run:
```sh
java Client
```
The client will create multiple threads and send messages to the server concurrently.

---

## Example Output

### Server Output
```
Server is listening on port: 8010
Connected to /127.0.0.1
Connected to /127.0.0.1
...
```

### Client Output
```
Response from Server Hello from server /127.0.0.1
Response from Server Hello from server /127.0.0.1
...
```

---

# Multi-Threaded Server with Thread Pool

This project demonstrates a **multi-threaded server** using **Java sockets** with a **thread pool**. The server efficiently manages multiple client connections by using a fixed-size thread pool instead of creating new threads for each request.

---

## How It Works

### 1. Server
- Starts a **ServerSocket** on port **8010**.
- Uses a **thread pool** (fixed size of 10 threads) to handle client requests.
- When a client connects:
  - Sends a **"Hello from server"** message.
  - Assigns a worker thread from the pool to handle the client.
  - Closes the connection after sending the response.
- Shuts down the thread pool when the server stops.

### 2. Client (Same as Previous Implementation)
- Spawns multiple threads, each creating a separate client connection.
- Connects to the server on **localhost:8010**.
- Sends a **"Hello from Client"** message.
- Reads the response from the server.
- Closes the connection.

---

## Project Structure
```
/ThreadPool
│── Client.java  # Multi-threaded client code
│── Server.java  # Thread-pooled server code
```

---

## How to Run

### Step 1: Compile the Code
```sh
javac Server.java Client.java
```

### Step 2: Start the Server
```sh
java Server
```
The server will start and wait for client connections.

### Step 3: Start the Client
In a **new terminal**, run:
```sh
java Client
```
The client will create multiple threads and send messages to the server concurrently.

---

## Example Output

### Server Output
```
Server is listening on port: 8010
Connected to /127.0.0.1
Connected to /127.0.0.1
...
```

### Client Output
```
Response from Server Hello from server /127.0.0.1
Response from Server Hello from server /127.0.0.1
...
```

---

## Why Use a Thread Pool?
- ✅ **Efficient resource management**: Limits the number of concurrent threads.
- 🚀 **Faster response time**: Reuses threads instead of creating new ones.
- 🔄 **Better scalability**: Handles multiple client requests efficiently.

---





