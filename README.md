# gRPC Server TP

This repository contains the **gRPC server** implementation for the Calculator TP in the "Architecture des composants d’entreprise" module.  
The server supports all four gRPC communication models:

1. **Unary** – client sends a single request, server responds once.
2. **Server Streaming** – client sends one request, server streams multiple responses.
3. **Client Streaming** – client streams multiple requests, server responds once.
4. **Bidirectional Streaming** – client and server both stream messages asynchronously.

---

## Features

- Calculator service (`CalculatorService`) with methods:
    - `sum` (Unary)
    - `getOperationStream` (Server Streaming)
    - `performStream` (Client Streaming)
    - `fullStream` (Bidirectional Streaming)
- Uses **Protocol Buffers (ProtoBuf)** for serialization.
- Written in **Java 17** using **Maven**.
- Compatible with **BloomRPC** or any gRPC client.

---

## Project Structure

```
grpc-server-tp/
├─ src/
│ ├─ main/
│ │ ├─ java/
│ │ │ └─ ma/formations/grpc/
│ │ │ ├─ service/CalculatorService.java
│ │ │ └─ server/GrpcServer.java
│ │ └─ resources/
│ │ └─ calculator.proto
├─ pom.xml
└─ README.md
```


---

## How to Run

1. Compile and generate gRPC stubs:

```bash
mvn clean install

```
2. Run the server:
```bash
cd target/classes
java ma.formations.grpc.server.GrpcServer
```

3. The server will start on port 9999.

# Testing
- Use BloomRPC or any gRPC client.

- Load calculator.proto, connect to localhost:9999.

- Test all four methods.

# Notes
- Ensure you have Java 17 and Maven installed.

- .proto file is located in src/main/resources.
