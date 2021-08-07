## [API Design Best Practices](https://docs.microsoft.com/en-us/azure/architecture/best-practices/api-design)

1. What does REST stand for? 
    - Representational State Transfer
2. REST APIs are designed around a ***RESOURCE***.
3. What is an identifer of a resource? Give an example.
4. What are the most common HTTP verbs? 
    - GET
    - POST
    - PUT
    - PATCH
    - DELETE
5. What should the URIs be based on?
    - Nouns
6. Give an example of a good URI.  
    Good URI:  https://adventure-works.com/orders  
    Bad URI:  https://adventure-works.com/create-order  
7. What does it mean to have a ‘chatty’ web API? Is this a good or a bad thing?
     - A 'chatty' API is a bad thing because it exposes a large number of small resources which can overload a server.
8. What status code does a successful GET request return?
    - 200
9. What status code does an unsuccessful GET request return?
    - 404
10. What status code does a successful POST request return?
    - 201
11. What status code does a successful DELETE request return?
    - 204


### [RegExr](https://regexr.com/)- Pay particular attention to the cheatsheet

1. How would you match your name using RegEx?  
    - 
