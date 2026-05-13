## API DESIGN:

* what is an API? And Their role in system architecture 
  api stands for application programming interface, and it is a set of rules and protocols that allow different software applications to communicate with each other. APIs play a crucial role in system architecture as they enable different components of a system to interact and exchange data seamlessly. They provide a standardized way for developers to access and utilize the functionality of a system, allowing for modularity, scalability, and flexibility in software development.

  a contract that defines: whate requests can be made, how to make them,what response to expect.

  core api styles:
    - REST (Representational State Transfer): REST is an architectural style that uses standard HTTP methods (GET, POST, PUT, DELETE) to perform operations on resources. It is stateless and relies on a client-server model, where the client sends requests to the server and receives responses. RESTful APIs are widely used for web services and are known for their simplicity and scalability. most use for web and mobile applications.
    - resource based endpoints
    - multiple requests for related data
    - http methods define operations on resources
    - fixed response structure
    - explicit versioning
    - built-in caching and statelessness
  
  - GraphQL: GraphQL is a query language for APIs that allows clients to request only the data they need. It provides a more flexible and efficient way to interact with APIs compared to REST. With GraphQL, clients can specify the structure of the response, reducing over-fetching and under-fetching of data. It is particularly useful for applications with complex data requirements. use for comple uis and microservices.
  - single endpoint for all data
  - single request for precise data
  - query language defines operations on data
  - client specifies response structure
  - schema evolution without versioning
  - application level caching and statefulness

  - gRPC (Google Remote Procedure Call): gRPC is a high-performance, open-source framework for building APIs. It uses Protocol Buffers (protobuf) as its interface definition language and supports multiple programming languages. gRPC is designed for low-latency and high-throughput communication, making it suitable for microservices and real-time applications.

The 5 Key Design Principles of APIs:
1. Simplicity: APIs should be easy to understand and use, with clear documentation and intuitive endpoints.
2. Consistency: APIs should follow consistent design patterns and conventions to ensure a predictable and cohesive experience for developers.
3. Flexibility: APIs should be flexible enough to accommodate changes and new features without breaking existing functionality.
4. Security: APIs should implement robust security measures to protect data
5. performance: APIs should be designed to minimize latency and maximize throughput, ensuring efficient communication between components. pagination, filtering, and sorting can help improve performance by reducing the amount of data transferred in each request.

API PROTOCOLS:
- HTTP/HTTPS: The most common protocol for web APIs, using standard HTTP methods for communication.
- WebSockets: A protocol for real-time communication between clients and servers, allowing for bidirectional communication.
- gRPC: A high-performance protocol that uses Protocol Buffers for efficient communication between services
- GraphQL: A query language for APIs that allows clients to request only the data they need, reducing over-fetching and under-fetching of data.

The API DESIGN PROCESS:
1. Define the purpose and goals of the API: Understand the needs of the users and the functionality that the API should provide.
2. Identify the resources and endpoints: Determine the key resources that the API will expose and design the endpoints for accessing those resources.
3. Choose the appropriate API style: Decide whether to use REST, GraphQL, gRPC, or another API style based on the requirements of the application and the preferences of the development team.
4. Design the request and response formats: Define the structure of the requests and responses, including the data formats (e.g., JSON, XML) and the fields that will be included in the responses.
5. Implement authentication and authorization: Determine how users will authenticate with the API and what permissions they will have to access different resources.
6. Document the API: Create comprehensive documentation that explains how to use the API, including examples of requests and responses, error handling, and any special considerations for developers.
7. Test the API: Thoroughly test the API to ensure that it functions as expected and handles edge cases gracefully. This includes unit testing, integration testing, and performance testing.
8. Monitor and maintain the API: Continuously monitor the API for performance, security, and usage patterns. Regularly update the API to fix bugs, add new features, and improve performance based on user feedback and changing requirements.

Design Approaches:
- Top-down design: Start with a high-level overview of the system and break it down into smaller components and APIs. This approach allows for a clear understanding of the overall architecture and how different components interact with each other.
- Bottom-up design: Start with the implementation of individual components and APIs, and then integrate them into a larger system. This approach allows for more flexibility and adaptability as the design evolves based on the implementation details and requirements that arise during development.
- contract first design: Define the API contract (the interface and expected behavior) before implementing the underlying functionality. This approach ensures that the API is designed with the needs of the clients in mind and allows for better collaboration between frontend and backend teams. It also promotes a clear separation of concerns and can lead to more maintainable and scalable APIs.

lifecycle of an API:
1. Design: The API is designed based on the requirements and goals of the application, following best practices and design principles.
2. Development: The API is implemented based on the design specifications,including the request and response formats, authentication mechanisms, and any necessary business logic.
3. deployment: The API is deployed to a production environment where it can be accessed by clients. This may involve setting up servers, configuring load balancers, and ensuring that the API is scalable and reliable.
4. monitoring: The API is continuously monitored for performance, security, and usage patterns. This includes tracking metrics such as response times, error rates, and user engagement to identify any issues or areas for improvement.
5. maintenance: The API is regularly updated and maintained to fix bugs, add new features, and improve performance based on user feedback and changing requirements. This may involve releasing new versions of the API and ensuring backward compatibility for existing clients.
6. deprecation: When an API is no longer needed or has been replaced by a newer version, it may be deprecated. This involves communicating the deprecation to users, providing a timeline for when the API will be retired, and offering alternatives or migration paths for users to transition to newer APIs.
7. retirement: The API is officially retired and is no longer available for use. This may involve shutting down servers, removing documentation, and ensuring that any remaining users are aware of the retirement and have transitioned to alternative APIs.

API Protocols:

choosing wrong protocol can lead to performance issues, security vulnerabilities, and compatibility problems. For example, using HTTP/HTTPS for real-time communication may result in increased latency and reduced performance compared to using WebSockets or gRPC. Similarly, using a protocol that does not support the required features or data formats may lead to compatibility issues and hinder the development process. It is important to carefully evaluate the requirements of the application and choose the appropriate protocol that best meets those needs.

1. The role of application protocols in the network stack
2. http/https: The most common protocol for web APIs, using standard HTTP methods for communication. It is widely supported and easy to implement, making it a popular choice for web services and mobile applications.
3. WebSockets: A protocol for real-time communication between clients and servers, allowing for bidirectional communication. It is ideal for applications that require low latency and real-time updates, such as chat applications, online gaming, and collaborative tools.
4. gRPC: A high-performance protocol that uses Protocol Buffers for efficient communication between services. It is designed for low-latency and high-throughput communication, making it suitable for microservices and real-time applications. gRPC supports multiple programming languages and provides features such as authentication, load balancing, and streaming, making it a powerful choice for building APIs in complex systems.
5. GraphQL: A query language for APIs that allows clients to request only the data they need, reducing over-fetching and under-fetching of data. It provides a more flexible and efficient way to interact with APIs compared to REST. With GraphQL, clients can specify the structure of the response, allowing for more efficient data retrieval and reducing the amount of data transferred over the network. GraphQL is particularly useful for applications with complex data requirements, such as those with multiple related resources or those that require real-time updates. It also allows for schema evolution without the need for versioning, making it easier to maintain and evolve APIs over time.


# Application protocols in the network stack

application layer: This is the topmost layer of the network stack, where application protocols operate. It is responsible for providing services directly to end-users and applications. Application protocols define the rules and conventions for communication between applications over a network. Examples of application protocols include HTTP/HTTPS, WebSockets, gRPC, and GraphQL. these define messaging formats, request/response patterns, and other conventions for how applications should interact with each other.


HTTP/HTTPS: The most common protocol for web APIs, using standard HTTP methods for communication. It is widely supported and easy to implement, making it a popular choice for web services and mobile applications. HTTP/HTTPS operates at the application layer and provides a request-response model for communication between clients and servers. It is stateless, meaning that each request is independent and does not rely on previous requests, which allows for scalability and flexibility in API design.

http methods
- GET: Used to retrieve data from the server. It is a read-only operation and should not have any side effects on the server.
- POST: Used to create new resources on the server. It is a write operation and can have side effects on the server, such as modifying data or triggering actions.
- PUT: Used to update existing resources on the server. It is a write operation and can have side effects on the server, such as modifying data or triggering actions.
- DELETE: Used to delete resources from the server. It is a write operation and can have side effects on the server, such as modifying data or triggering actions.

status codes
- 200 OK: The request was successful and the server returned the requested data.
- 201 Created: The request was successful and a new resource was created on the server.
- 400 Bad Request: The request was invalid or malformed, and the server could not process it.
- 401 Unauthorized: The request requires authentication, and the client has not provided valid credentials.
- 403 Forbidden: The client does not have permission to access the requested resource.
- 404 Not Found: The requested resource could not be found on the server.
- 500 Internal Server Error: An error occurred on the server while processing the request.
- 503 Service Unavailable: The server is currently unavailable, usually due to maintenance or overload.

common headers
- Content-Type: Specifies the media type of the request or response body, such as application/json or text/html.
- Authorization: Contains credentials for authenticating the client with the server, such as a bearer token or basic authentication credentials.
- Accept: Specifies the media types that the client is willing to accept in the response, such as application/json or text/html.
- Cache-Control: Specifies caching directives for the request or response, such as no-cache or max-age.
- User-Agent: Contains information about the client application making the request, such as the browser or mobile app version.
- Host: Specifies the domain name of the server being requested, such as api.example.com.
- Content-Length: Specifies the size of the request or response body in bytes.

# https :
 Hypertext Transfer Protocol Secure (HTTPS) is an extension of HTTP that adds a layer of security by encrypting the communication between the client and server using SSL/TLS. This ensures that sensitive data, such as login credentials or personal information, is protected from interception and tampering by malicious actors. HTTPS is essential for securing web applications and APIs, especially those that handle sensitive data or require user authentication. It also helps to build trust with users by providing a secure browsing experience.]
benefits of using https:
1. Data encryption: HTTPS encrypts the data transmitted between the client and server, making it difficult for attackers to intercept and read the data. This is especially important for sensitive information such as login credentials, personal data, and financial information.
2. Data integrity: HTTPS ensures that the data sent between the client and server is not tampered with or modified by attackers. This helps to maintain the integrity of the data and prevent unauthorized changes.
3. Authentication: HTTPS provides a mechanism for authenticating the server to the client, ensuring that the client is communicating with the intended server and not an imposter. This helps to prevent man-in-the-middle attacks and build trust with users.
4. SEO benefits: Search engines like Google give preference to secure websites using HTTPS, which can improve search engine rankings and increase visibility for the website or API.
5. Compliance requirements: Many industries and regulations require the use of HTTPS to protect sensitive data, such as the Payment Card Industry Data Security Standard (PCI DSS) for handling credit card information. Using HTTPS can help organizations meet these compliance requirements and avoid potential legal and financial consequences of data breaches.

# WebSockets:
WebSockets is a protocol for real-time communication between clients and servers, allowing for bidirectional communication. It is ideal for applications that require low latency and real-time updates, such as chat applications, online gaming, and collaborative tools. WebSockets operates at the application layer and provides a full-duplex communication channel over a single TCP connection. This allows for efficient and low-latency communication between clients and servers, making it suitable for applications that require real-time updates or interactive features. WebSockets also supports features such as message framing, which allows for efficient transmission of large messages, and subprotocols, which allow for custom communication patterns between clients and servers.

advantages of WebSockets:
1. Real-time communication: WebSockets allows for real-time communication between clients and servers, enabling applications to provide instant updates and interactive features without the need for constant polling or refreshing.
2. Low latency: WebSockets provides a low-latency communication channel, allowing for fast and responsive interactions between clients and servers. This is particularly beneficial for applications that require real-time updates, such as chat applications, online gaming, and collaborative tools.
3. Efficient use of resources: WebSockets uses a single TCP connection for bidirectional communication, which can reduce the overhead associated with establishing multiple connections for each request and response. This can lead to improved performance and reduced resource consumption on both the client and server sides.
4. Support for message framing: WebSockets supports message framing, which allows for efficient transmission of large messages by breaking them into smaller frames. This can help to improve performance and reduce latency when transmitting large amounts of data between clients and servers.
5. Subprotocols: WebSockets allows for the use of subprotocols, which enable custom communication patterns between clients and servers. This can provide flexibility in designing APIs and allow for specialized communication patterns that may not be supported by other protocols, such as REST or gRPC. Subprotocols can be used to implement features such as multiplexing, where multiple logical channels can be established over a single WebSocket connection, or to define custom message formats and communication patterns specific to the application's needs.

disadvantages of WebSockets:
1. increase latency for simple requests: WebSockets may introduce additional latency for simple requests that do not require real-time communication, as the overhead of establishing and maintaining a WebSocket connection may outweigh the benefits for these types of interactions.
2. Complexity: Implementing WebSockets can be more complex than traditional HTTP-based APIs, as it requires handling connection management, message framing, and potential issues such as connection drops or network interruptions. This can increase the development time and effort required to build and maintain WebSocket-based APIs.
3. Limited browser support: While WebSockets are widely supported in modern browsers, there may still be some older browsers or environments that do not support WebSockets, which can limit the accessibility of WebSocket-based APIs for certain users or applications.
4. Security considerations: WebSockets can introduce security risks if not implemented properly, such as potential vulnerabilities to cross-site scripting (XSS) attacks or denial of service (DoS) attacks. It is important to implement proper security measures, such as input validation, authentication.

# AMQP (Advanced Message Queuing Protocol):
AMQP is a messaging protocol that enables communication between different components of a system using message queues. It is designed for high reliability and scalability, making it suitable for distributed systems and microservices architectures. AMQP allows for asynchronous communication between components, where messages can be sent and received independently of each other. It provides features such as message routing, message persistence, and support for multiple messaging patterns (e.g., publish-subscribe, request-response). AMQP is often used in scenarios where decoupling of components is desired, such as in event-driven architectures or when integrating with third-party services. It can be implemented using various messaging brokers, such as RabbitMQ or Apache ActiveMQ, which provide the necessary infrastructure for managing message queues and facilitating communication between components.

                  publishers/                                               consumers
producers ----------------------------> message broker (AMQP) ----------------------------> consumers
webservices                             exchange messages                             order processing
payments systems                        queues                                        notification systems
 
exchange types:
1. Direct Exchange: In a direct exchange, messages are routed to queues based on a specific routing key. The producer specifies a routing key when sending a message, and the exchange routes the message to the queue(s) that are bound to that routing key. This allows for precise routing of messages to specific queues based on the routing key, making it suitable for scenarios where messages need to be delivered to specific consumers or groups of consumers.
2. Fanout Exchange: In a fanout exchange, messages are broadcast to all queues that are bound to the exchange, regardless of the routing key. This means that all consumers that are subscribed to the exchange will receive the message. This is useful for scenarios where messages need to be delivered to multiple consumers or when the routing of messages is not important, such as in a publish-subscribe pattern.
3. Topic Exchange: In a topic exchange, messages are routed to queues based on pattern matching of the routing key. The producer specifies a routing key when sending a message, and the exchange routes the message to queues that are bound to the exchange with a matching pattern. This allows for more flexible routing of messages based on patterns in the routing key, making it suitable for scenarios where messages need to be delivered to specific consumers based on certain criteria or when there is a need for more complex routing logic.


# gRPC (Google Remote Procedure Call):
gRPC is a high-performance, open-source framework for building APIs. It uses Protocol Buffers (protobuf) as its interface definition language and supports multiple programming languages. gRPC is designed for low-latency and high-throughput communication, making it suitable for microservices and real-time applications. gRPC operates at the application layer and provides a remote procedure call (RPC) model for communication between clients and servers. It allows clients to call methods on a server as if they were local, abstracting away the underlying network communication. gRPC supports features such as authentication, load balancing, and streaming, making it a powerful choice for building APIs in complex systems. It is particularly well-suited for scenarios where performance and efficiency are critical, such as in microservices architectures or when handling large volumes of data.


client                           protocol buffers             server
stubs  -------------------------------------------------------services
type safety                                                   streaming

choosing the right protocols:
. interaction patterns: Consider the communication patterns required by your application, such as request-response, publish-subscribe, or real-time updates. Choose a protocol that supports the necessary interaction patterns for your use case.
2. performance requirements: Evaluate the performance requirements of your application, such as latency and throughput. Choose a protocol that can meet those requirements, especially if you are building a high-performance or real-time application.
3. language and platform support: Consider the programming languages and platforms you are using for your application. Choose a protocol that has good support for those languages and platforms to ensure ease of development and integration.
4. security considerations: Evaluate the security requirements of your application and choose a protocol that provides the necessary security features, such as encryption, authentication, and authorization, to protect your data and ensure secure communication between components.
5. scalability and maintainability: Consider the scalability and maintainability of your application. Choose a protocol that can scale with your application's growth and is easy to maintain and evolve over time, especially if you anticipate changes in requirements or the need for new features in the future.
6. payload size and complexity: Evaluate the size and complexity of the data being transmitted between components. Choose a protocol that can efficiently handle the payload size and complexity, especially if you are dealing with large volumes of data or complex data structures.
7. security needs: Consider the security requirements of your application and choose a protocol that provides the necessary security features, such as encryption, authentication, and authorization, to protect your data and ensure secure communication between components.


Transport Layer : how the request going through internet
The transport layer is responsible for providing reliable and efficient communication between applications over a network. It ensures that data is delivered accurately and in the correct order, and it manages the flow of data between the sender and receiver. The transport layer provides services such as error detection and correction, flow control, and congestion control to ensure that data is transmitted reliably and efficiently. Common transport layer protocols include TCP (Transmission Control Protocol) and UDP (User Datagram Protocol). TCP provides reliable, connection-oriented communication, while UDP provides faster, connectionless communication with less overhead. The choice of transport layer protocol depends on the requirements of the application, such as the need for reliability, latency sensitivity, and the size of the data being transmitted.

TCP vs UDP:
1. TCP (Transmission Control Protocol): reliavble but slower. TCP is a connection-oriented protocol that provides reliable communication between applications. It establishes a connection between the sender and receiver before transmitting data and ensures that data is delivered accurately and in the correct order. TCP uses acknowledgments and retransmissions to guarantee delivery, making it suitable for applications that require reliability, such as web browsing, email, and file transfer. However, TCP can introduce additional latency due to the overhead of establishing and maintaining connections, as well as the need for acknowledgments and retransmissions.
   use cases for TCP include:
   - Web browsing: TCP is used for HTTP/HTTPS communication, ensuring that web pages and resources are delivered reliably to users.
   - Email: TCP is used for protocols such as SMTP, POP3, and IMAP to ensure that email messages are delivered accurately and in the correct order.
   - File transfer: TCP is used for protocols such as FTP and SFTP to ensure that files are transferred reliably between clients and servers.


2. UDP (User Datagram Protocol): unrealable but fast and efficient. no deliver guarentee. UDP is a connectionless protocol that provides faster communication between applications. It does not establish a connection before transmitting data and does not guarantee delivery or order of messages. UDP is suitable for applications that require low latency and can tolerate some loss of data, such as  real-time streaming, online gaming, and voice over IP (VoIP). However, UDP can lead to data loss or out-of-order delivery, which may not be acceptable for applications that require reliability.

  use cases of udp include:
  - Real-time streaming: UDP is commonly used for streaming media applications, such as video streaming and audio streaming, where low latency is crucial and some loss of data can be tolerated.
  - Online gaming: UDP is often used for online multiplayer games, where real-time communication between players is essential and some loss of data can be acceptable.
  - Voice over IP (VoIP): UDP is frequently used for VoIP applications, where low latency is important for real-time communication, and some loss of data can be tolerated without significantly impacting the user experience.

