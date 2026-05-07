system design mastery

- Foundation - the core concepts and principles of system design, including scalability, reliability, maintainability, and performance.
- api design - the principles and best practices for designing APIs, including RESTful design, GraphQL, and gRPC.
- databases - the different types of databases (relational, NoSQL, in-memory) and their use cases, as well as database design and optimization techniques.
- caching - the principles and techniques for caching data to improve performance, including cache invalidation strategies and cache consistency.
- big data - the challenges and solutions for handling large volumes of data, including distributed storage, data processing frameworks, and data pipelines.
- production infrastructure - the tools and techniques for deploying and managing systems in production, including containerization, orchestration, monitoring, and logging.


web browser - the server handles business logic, data storage and presentation using html css and js. the client is responsible for rendering the user interface and handling user interactions.

mobile app - the server handles business logic and data storage, while the client is responsible for rendering the user interface and handling user interactions. mobile apps may also use native features of the device, such as camera or GPS, which require additional considerations for design and implementation.

an single server setup - the server handles all aspects of the application, including business logic, data storage, and presentation. this setup is simple and easy to manage, but may not be scalable or reliable for larger applications. when you hit the app.demo.com, the request goes to the server, the domain name is resolved to an ip address, the server receives the request and processes it. the server may perform various operations, such as querying a database, performing calculations, or generating dynamic content,
 which processes the request and returns the appropriate response. the server may also interact with a database to retrieve or store data as needed.


 identify areas where a single server might fall short as user demand increases.

 to accommedate more user we can seperate our web tier is handling the web and mobile traffic. and data tier is handling the database operations. this way we can scale each tier independently based on the demand. for example, if we have a sudden increase in web traffic, we can add more web servers to handle the load without affecting the database tier. similarly, if we have a sudden increase in database operations, we can add more database servers to handle the load without affecting the web tier. this separation of concerns allows us to design a more scalable and reliable system that can handle increasing user demand.


 choosing the  right type of database
 when comes to select database there are two main options. one is
 
 - Relational databases (SQL) - these databases are based on a structured schema and use SQL for querying. they are suitable for applications that require complex queries, transactions, and data integrity. examples include MySQL, PostgreSQL, and Oracle.
 - NoSQL databases - these databases are designed for unstructured or semi-structured data and do not require a fixed schema. they are suitable for applications that require high scalability, flexibility, and performance. examples include MongoDB, Cassandra, and Redis.

1. Relational databases (SQL) - these databases are based on a structured schema and use SQL for querying. they are suitable for applications that require complex queries, transactions, and data integrity. examples include MySQL, PostgreSQL, and Oracle. the data her is structured and organized into tables with predefined relationships. this allows for complex queries and transactions, making it ideal for applications that require data integrity and consistency. however, relational databases may not be the best choice for applications that require high scalability or flexibility, as they can become bottlenecks as the amount of data and traffic increases. 
   - advantages: 
        - support complex join operations and transactions
        - combine two or more table to  one tble called join operation
        - transaction in sql is a sequence of operations performed as a single logical unit of work. it ensures that either all operations are executed successfully or none of them are, maintaining data integrity and consistency. ACID properties of transactions:
            - Atomicity: ensures that all operations within a transaction are treated as a single unit, meaning that either all operations are executed successfully or none of them are.
            - Consistency: ensures that a transaction brings the database from one valid state to another valid state, maintaining the integrity of the data.
            - Isolation: ensures that concurrent transactions do not interfere with each other, allowing them to execute independently without affecting the outcome of each other.
            - Durability: ensures that once a transaction is committed, its changes are permanent and will survive any subsequent failures, such as power outages or crashes.
  
2. NoSQL databases - these databases are designed for unstructured or semi-structured data and do not require a fixed schema. they are suitable for applications that require high scalability, flexibility, and performance. examples include MongoDB, Cassandra, and Redis. the data here is unstructured or semi-structured, allowing for more flexibility in data storage and retrieval. this makes it ideal for applications that require high scalability and performance, as it can handle large volumes of data and traffic without becoming a bottleneck. however, NoSQL databases may not be the best choice for applications that require complex queries or transactions, as they may lack the features and capabilities of relational databases.
    
    document stores: 
    mongodb: here data is stored in a flexible, JSON-like format called BSON. it allows for dynamic schemas, making it easy to evolve the data model as the application requirements change. it also provides powerful querying capabilities and supports indexing for improved performance.
    side column stores:
    cassandra: here data is stored in a columnar format, which allows for efficient storage and retrieval of large volumes of data. it is designed for high availability and scalability, making it suitable for applications that require fast read and write operations across distributed clusters. it also provides features such as tunable consistency levels and support for multi-data center replication.
    graph databases:
    neo4j: here data is stored in a graph format, which allows for efficient representation and querying of complex relationships between data. it is designed for applications that require traversing and analyzing relationships, such as social networks, recommendation engines, and fraud detection. it provides powerful querying capabilities using the Cypher query language and supports features such as indexing and graph algorithms for improved performance.
    key-value stores:
    redis: here data is stored as key-value pairs, allowing for fast access and retrieval of data based on keys. it is designed for applications that require low latency and high throughput, such as caching, session management, and real-time analytics. it provides features such as in-memory storage, support for various data structures (strings, hashes, lists, sets), and built-in replication and persistence options for improved performance and reliability.
   - advantages:
        - designed to handle large volumes of unstructured or semi-structured data
        - provide high scalability and performance
        - flexible schema allows for easy changes to the data model without downtime
        - - can handle highly dynamic and large data sets because of their flexible schema and distributed architecture we can store id of users in a single document in mongodb, while in relational database we need to create multiple tables and join them together to get the same information. this can lead to better performance and scalability for applications that require handling large volumes of data and traffic. however, NoSQL databases may not be the best choice for applications that require complex queries or transactions, as they may lack the features and capabilities of relational databases.
        - optimised for low latency and scalability
  
  WHEN TO USE RELATIONAL VS NOSQL DATABASES:
- use relational databases when:
    - your application requires complex queries and transactions that involve multiple tables and relationships.
    - if you have an ecommerce application that requires complex queries to retrieve product information, customer data, and order history, a relational database would be a good choice. it allows you to define relationships between tables (e.g., products, customers, orders) and perform complex joins and transactions to ensure data integrity and consistency.
    - strong consistency and transactional integrity.
    - for example, if you have a banking application that requires strong consistency and transactional integrity for financial transactions, a relational database would be a good choice. it allows you to define relationships between tables (e.g., accounts, transactions) and perform complex queries and transactions to ensure data integrity and consistency.
- use NoSQL databases when:
    - your application requires high scalability and performance, and can tolerate eventual consistency.
    - if you have a social media application that needs to handle large volumes of user-generated content and high traffic, a NoSQL database would be a good choice. it allows you to store unstructured or semi-structured data (e.g., posts, comments, likes) and scale horizontally to handle the increasing load without becoming a bottleneck. it also provides flexibility in data modeling, allowing you to evolve the schema as your application requirements change over time.
    - scalable storage for massive data volumes
    - data is unstructured or semi-structured
    - for example, if you have an IoT application that generates large volumes of sensor data with varying formats, a NoSQL database would be a good choice. it allows you to store unstructured or semi-structured data (e.g., sensor readings, device metadata) and scale horizontally to handle the increasing load without becoming a bottleneck. it also provides flexibility in data modeling, allowing you to evolve the schema as your application requirements change over time.


Vertical and horizontal scaling

1 Vertical scaling (scaling up) - this involves adding more resources (CPU, RAM, storage) to a single server to handle increased load. it is a simple and cost-effective way to improve performance, but it has limitations as there is a maximum capacity that a single server can handle. once you reach that limit, you will need to consider horizontal scaling.

limitations of vertical scaling:
- there is a maximum capacity that a single server can handle, which can limit the scalability of the system as user demand increases.
- it can lead to a single point of failure, as all traffic is directed to a single server. if that server goes down, the entire system can become unavailable
- lack of redundancy and fault tolerance, as there is no backup server to take over in case of failure. this can lead to downtime and loss of revenue for applications that require high availability.
- it can be expensive to upgrade to more powerful hardware, especially if you need to scale up frequently to accommodate increasing user demand. this can lead to higher costs compared to horizontal scaling, which allows for more flexible and cost-effective scaling options.

2 Horizontal scaling (scaling out) - this involves adding more servers to a system to handle increased load. it is a more complex approach, but it provides better fault tolerance and can handle larger volumes of traffic. horizontal scaling can be achieved through techniques such as load balancing, where incoming traffic is distributed across multiple servers to ensure that no single server becomes a bottleneck. it can also involve using distributed databases and caching systems to improve performance and scalability. while horizontal scaling can provide better fault tolerance and handle larger volumes of traffic, it also introduces additional complexity in terms of managing and coordinating multiple servers, ensuring data consistency, and handling failures. therefore, it is important to carefully consider the trade-offs between vertical and horizontal scaling based on the specific requirements of your application and the expected growth in traffic.


Load Balancer

load balancers distribute incoming network traffic acrooss multiple  servers to ensure no single server bears too much load.

7 strategies and algorithms used in load balancing:

1. Round Robin - this strategy distributes incoming requests sequentially to each server in a circular manner. it is simple and easy to implement, but it does not take into account the current load on each server, which can lead to uneven distribution of traffic.

2. Least Connections - this strategy directs incoming requests to the server with the fewest active connections. it helps to distribute traffic more evenly based on the current load on each server, but it may not always be the most efficient approach if there are significant differences in server performance or request processing times.

3. Least Response Time - this strategy sends incoming requests to the server that has the lowest response time. it can help to improve performance by directing traffic to the fastest server, but it may not always be the best choice if there are significant differences in server performance or if response times fluctuate frequently.

4. IP Hash - this strategy uses the client's IP address to determine which server to route the request to. it can help to ensure that requests from the same client are consistently directed to the same server, which can be beneficial for session persistence. however, it may not always provide an even distribution of traffic, especially if there are a large number of clients with similar IP addresses.

5. Weighted Round Robin - this strategy assigns weights to each server based on their capacity or performance, and distributes incoming requests accordingly. servers with higher weights receive more traffic, while servers with lower weights receive less traffic. this can help to optimize resource utilization and improve performance, but it requires careful configuration of weights to ensure an even distribution of traffic.

6. Geographical Algorithm - this strategy routes incoming requests to the server that is geographically closest to the client. it can help to reduce latency and improve performance by directing traffic to servers that are physically closer to the client, but it may not always be the best choice if there are significant differences in server performance or if clients are located in regions with limited server availability.

7. Consistent Hashing - this strategy uses a hash function to map incoming requests to specific servers based on the request's attributes (e.g., URL, session ID). it can help to ensure that requests with similar attributes are consistently directed to the same server, which can be beneficial for caching and session persistence. however, it may not always provide an even distribution of traffic, especially if there are a large number of requests with similar attributes.

Health checks are an essential component of load balancers, as they help to ensure that traffic is only directed to healthy and responsive servers. health checks typically involve sending periodic requests to each server to verify that they are functioning properly and can handle incoming traffic. if a server fails a health check, the load balancer can automatically remove it from the pool of available servers until it becomes healthy again. this helps to improve the overall reliability and availability of the system by preventing traffic from being directed to servers that are experiencing issues or downtime.

Software load balancer
Nginx: nginx is a popular open-source web server that can also function as a load balancer. it supports various load balancing algorithms, including round robin, least connections, and IP hash. nginx can be configured to distribute incoming traffic across multiple servers, providing improved performance and fault tolerance for web applications.

HAProxy: HAProxy is another widely used open-source load balancer that is known for its high performance and reliability. it supports a wide range of load balancing algorithms, including round robin, least connections, and weighted round robin. HAProxy can be used to distribute traffic across multiple servers, providing improved scalability and fault tolerance for applications that require high availability.

F5 BIG-IP: F5 BIG-IP is a commercial load balancer that offers advanced features and capabilities for managing and distributing traffic across multiple servers. it supports various load balancing algorithms, including round robin, least connections, and weighted round robin. F5 BIG-IP also provides additional features such as SSL offloading, application acceleration, and security capabilities to enhance the performance and security of applications.

cloud-based load balancer
AWS Elastic Load Balancing (ELB): AWS ELB is a cloud-based load balancing service provided by Amazon Web Services. it offers various load balancing options, including Application Load Balancer (ALB) for HTTP/HTTPS traffic and Network Load Balancer (NLB) for TCP/UDP traffic. AWS ELB automatically distributes incoming traffic across multiple targets (e.g., EC2 instances, containers) and provides features such as health checks, SSL termination, and auto-scaling integration to ensure high availability and performance for applications hosted on AWS.


SPOF (Single Point of Failure) is a critical concept in system design that refers to a component or part of a system that, if it fails, will cause the entire system to fail. it is important to identify and eliminate SPOFs in order to improve the reliability and availability of a system. this can be achieved through techniques such as redundancy, failover mechanisms, and load balancing. by designing systems with multiple components that can take over in case of failure, we can ensure that the system remains operational even if one component fails, thus improving the overall resilience of the system.