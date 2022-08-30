># What does REST stand for?

* ### REST is an architectural style for building distributed systems based on hypermedia
># REST APIs are designed around a ____.

* ### resources
># What is an identifier of a resource? Give an example.

* ### A resource has an identifier, which is a URI that uniquely identifies that resource. For example, the URI for a particular customer order might be:https://adventure-works.com/orders/1 .... Clients interact with a service by exchanging representations of resources. Many web APIs use JSON as the exchange format. For example, a GET request to the URI listed above might return this response body:{"orderId":1,"orderValue":99.90,"productId":1,"quantity":1}
># What are the most common HTTP verbs?

* ### GET, POST, PUT, PATCH, and DELETE.


># What should the URIs be based on?

* ### resources
># Give an example of a good URI.

* ### https://adventure-works.com/customers/3?version=2

># What does it mean to have a ‘chatty’ web API? Is this a good or a bad thing?

* ###  try to avoid "chatty" web APIs that expose a large number of small resources its a bad thing

># What status code does a successful GET request return?

* ### A successful GET method typically returns HTTP status code 200 (OK).

># What status code does an unsuccessful GET request return?

* ### If the resource cannot be found, the method should return 404 (Not Found).

># What status code does a successful POST request return?

* ### it returns HTTP status code 201 (Created).

># What status code does a successful DELETE request return?
* ### Return HTTP status code 202 (Accepted) to indicate the request was accepted for processing but is not completed.