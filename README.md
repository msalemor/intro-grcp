# Introduction to gRCP

## Why gRPC ?

- gRPC is a modern open source high performance RPC framework that can run in any environment. 
- It can efficiently connect services in and across data centers with pluggable support for load balancing, tracing, health checking and authentication. 
- It is also applicable in last mile of distributed computing to connect devices, mobile applications and browsers to backend services.

## Benefits of gRPC

gRPC stands above other solutions for the following reasons:

### Performance
- Using HTTP/2 rather than HTTP/1.1 removes the requirement for human-readable messages and instead uses the smaller, faster binary protocol. This is more efficient for computers to parse. HTTP/2 also supports multiplexing requests over a single connection. This support enables responses to be sent as soon as they're ready without the need to wait in a queue. (In HTTP/1.1, this issue is known as "head-of-line (HOL) blocking.") You need fewer resources when using gRPC, which makes it a good solution to use for mobile devices and over slower networks.

### Interoperability
- There are gRPC tools and libraries for all major programming languages and platforms, including .NET, Java, Python, Go, C++, Node.js, Swift, Dart, Ruby, and PHP. Thanks to the Protocol Buffers binary wire format and the efficient code generation for each platform, developers can build performant apps while still enjoying full cross-platform support.
- Dapr for example can leverage gRCP.

### Usability and productivity
- gRPC is a comprehensive RPC solution. It works consistently across multiple languages and platforms. It also provides excellent tooling, with much of the necessary boilerplate code automatically generated. So more developer time is freed up to focus on business logic.

### Streaming
- gRPC has full bidirectional streaming, which provides similar functionality to WCF's full duplex services. gRPC streaming can operate over regular internet connections, load balancers, and service meshes.

### Deadline/timeouts and cancellation
- gRPC allows clients to specify a maximum time for an RPC to finish. If the specified deadline is exceeded, the server can cancel the operation independently of the client. Deadlines and cancellations can be propagated through further gRPC calls to help enforce resource usage limits. Clients can also stop operations when a deadline is exceeded, or earlier if necessary (for example, because of a user interaction).

### Security
- gRPC is implicitly secure when it's using HTTP/2 over a TLS end-to-end encrypted connection. Support for client certificate authentication (see chapter 6) further increases security and trust between client and server.

## gRPC recommended scenarios

gRPC is well suited to the following scenarios:

- ***Microservices:*** gRPC is designed for low latency and high throughput communication. gRPC is great for lightweight microservices where efficiency is critical.
  - https://dzone.com/articles/why-grpc-for-inter-microservice-communication
- ***Point-to-point real-time communication:*** gRPC has excellent support for bi-directional streaming. gRPC services can push messages in real-time without polling.
- ***Polyglot environments:*** gRPC tooling supports all popular development languages, making gRPC a good choice for multi-language environments.
- ***Network constrained environments:*** gRPC messages are serialized with Protobuf, a lightweight message format. A gRPC message is always smaller than an equivalent JSON message.

<!---
## How gRPC approaches RPC (Remote Procedure Call)?

- This pattern aims to make calls to services that run on a different machine, or in a different process, work seamlessly, like method calls in the client application. While the aims of WCF and gRPC are the same, the details of the implementation are quite different.

## Implementation

- Uses proto file to protocol languange buffer (protobuf)
- Language defines messages and service contracts (similar to WCF)
- Uses http/2 and has to be

## Http 1.1 works
- Establishes TCP connection to server
- Based Request/Response model
- Socket is busy until request is processed
- If there are many files, In 1.1, Browser establishs up to 6 TCP connections

## Http 2 works
- Google SPDY protocol
- Establishes single TCP connection
- Multiplexes requests using stream id
- Each package will be assigned a stream id
- Over the same TCP channel, it can process many requests/responses

### Good
- Multiplexing over single connection
- Compression
- Server Push
- Secure by default

### Bad:
- Can be slower when in mixed mode (backend h2 but load balancer is h1 or vice versa)-->


