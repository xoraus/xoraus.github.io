---
title: 
date: 2024-04-08 00:00:00 +0530
categories: [Backend, Development]
tags: [rest, api] # TAG names should always be lowercase
---

### REST Introduction and REST Architecture

- **Definition of REST:**
  - **REST** stands for **Representational State Transfer**.
  - Understanding each term:
    - **State**: Represents data.
    - **Representational**: Denotes a data format (e.g., XML, JSON, YAML, HTML, plain text).
    - **Transfer**: Involves transferring data between consumer and provider using HTTP protocol.

- **REST Architecture Overview:**
  - Involves a **client-server model** where a client sends HTTP requests to a server, and the server processes and responds.
  - Clients can be diverse (e.g., Android, iOS, desktop, web applications).
  - **Independence**: Client and server should be independent; changes in one shouldn't affect the other.
  - **Message Exchange Format**: Data exchanged between client and server typically in JSON or XML.

- **Key Points about REST:**
  - **Origin**: Coined by **Roy Fielding**, inventor of HTTP protocol.
  - **Purpose**: Facilitates communication between applications over HTTP, akin to browser-server interaction.
  - **Popularity**: Rapid adoption due to increased mobile device usage, allowing web and mobile clients to consume the same APIs.

- **REST Architectural Constraints:**
  - **Client-Server Architecture**: Client and server are distinct, independent components.
  - **Statelessness**: No session data stored on the server; each request is stateless.
  - **Cacheability**: Clients can cache responses for improved performance.
  - **Uniform Interface**: Provides a consistent, generic interface for interactions, simplifying architecture.
  - **Layered System**: Servers can have multiple layers for scalability and load balancing.
  - **Code on Demand (Optional)**: Allows clients to download and execute code from the server, though rarely used.

- **Conclusion:**
  - RESTful APIs follow these architectural constraints to ensure effective communication between clients and servers.

**Key Terms:**
- REST
- Representational State Transfer
- State
- Representational
- Transfer
- HTTP protocol
- Client
- Server
- Web services
- HTTP request
- HTTP response
- Message Exchange Format
- JSON
- XML
- Roy Fielding
- Client-server architecture
- Independence
- Statelessness
- Cacheability
- Uniform Interface
- Layered System
- Code on Demand

### REST Key Concepts - Resource, URI and Sub-resource

**Notes on REST Key Concepts:**

- **Resource in REST:**
  - In a REST-based system, **everything** is a **resource**.
  - A **resource** is anything exposed to the outside world through the application.
  - Examples of resources in various systems: Employee, Department, Address, Project, Task (Employee Management System); Student, Teacher, Class, Subject, School (Student Management System); Post, Comment, User, Tags, Category (Blog Application).
  - CRUD (Create, Read, Update, Delete) REST APIs are typically created for each resource.
  - Clients consume these REST APIs to perform actions on resources.

- **Uniform Resource Identifier (URI):**
  - **URI** is used to **identify** resources.
  - Each URI should be **unique**.
  - Examples of URIs for CRUD operations on a Post resource: 
    - URL to list posts
    - URL to retrieve a post by ID
    - URL to create a new post
    - URL to update a post
    - URL to delete a post

- **Sub-resource:**
  - **Sub-resources** are used to model relationships in REST APIs.
  - Relationships are modeled by placing a sub-resource after a resource.
  - Pattern: `resource/resource-id/sub-resource/sub-resource-id`.
  - Example: In a blog application, posts can have comments as sub-resources. To retrieve comments for a particular post, the URI would be `post/post-id/comments`.
  - Sub-resources are used when child objects cannot exist without their parent (e.g., comments cannot exist without a post, drivers cannot exist without a car).
  - Deleting the parent resource may also delete the associated sub-resources.

**Key Terms:**
- Resource
- CRUD
- Uniform Resource Identifier (URI)
- Sub-resource
- Relationships
- Parent-child relationship
- HTTP Methods
- HTTP Status Codes

### REST Key Concepts - Http Methods

**Notes on HTTP Methods in RESTful Web Services:**

- **HTTP Methods:**
  - **GET**: Used to retrieve or get a collection or a single resource. Not for modifying or creating resources.
  - **POST**: Utilized to create a new resource. Typically used for adding new entities like employees, students, or users.
  - **PUT**: Employed to update an existing resource. Used when modifying existing entities such as updating employee details or student information.
  - **DELETE**: Used to delete a collection or a single resource. Enables removal of entities like students or specific records identified by their unique identifiers.
  - **PATCH**: Optionally used to partially update an existing resource.

- **Usage Examples:**
  - **GET Method**: Retrieve a list of posts or a single post by ID.
  - **POST Method**: Create a new post in a blog application.
  - **PUT Method**: Update an existing post by specifying its ID.
  - **DELETE Method**: Delete a post or other resources by their IDs.

- **Additional Note:**
  - **PATCH Method**: Used for partial updates to existing resources, updating specific fields without modifying the entire resource.

**Key Terms:**
- HTTP Methods
- GET
- POST
- PUT
- DELETE
- PATCH
- RESTful Web Services
- Resource Modification
- Resource Creation
- Resource Deletion
- Postman

### REST Key Concepts - HTTP Status Codes

**Notes on Important HTTP Status Codes:**

- **Overview:**
  - **HTTP status codes** indicate the outcome of a request made by a client to a server.
  - These status codes help in understanding the status of the request and guide further actions.

- **200 OK:**
  - **Indicates**: Request is successful, and response content is returned to the client as appropriate.
  - **Example**: Retrieving a collection of blog posts or a single post.

- **201 CREATED:**
  - **Indicates**: Request is successful, and a new resource is created.
  - **Example**: Creating a new blog post; server responds with the newly created resource.

- **400 Bad Request:**
  - **Indicates**: Server failed to process the request due to malformed syntax in the request.
  - **Example**: Client passed invalid parameters; server responds with a bad request status code.

- **401 Unauthorized:**
  - **Indicates**: Authentication is required for the resource, and the client needs to provide appropriate credentials.
  - **Example**: Accessing a protected resource without valid authentication; server responds with an unauthorized status code.

- **403 Forbidden:**
  - **Indicates**: Server refuses to respond to the request, even if the request is valid.
  - **Example**: Attempting to access unauthorized resources; server responds with a forbidden status code.

- **404 Not Found:**
  - **Indicates**: Requested resource is not found at the specified location.
  - **Example**: Attempting to delete a blog post that does not exist; server responds with a not found status code.

- **500 Internal Server Error:**
  - **Indicates**: An unexpected error occurred on the server, and the request cannot be fulfilled.
  - **Example**: Server-side error during user authentication or other processing; server responds with an internal server error status code.

**Key Terms:**
- HTTP Status Codes
- 200 OK
- 201 CREATED
- 400 Bad Request
- 401 Unauthorized
- 403 Forbidden
- 404 Not Found
- 500 Internal Server Error
- Client-Server Communication