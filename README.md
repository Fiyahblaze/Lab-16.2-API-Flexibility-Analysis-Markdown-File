mark down
Over-fetching is when the API sends back more information than your application needs.
example, so like we did in our library app a page might only need a book’s title and author, but the REST endpoint returns the description, publication date, and a bunch of other details too. That extra information is overfetching.

Under-fetching is like it sounds pretty much the opposite of over fetching but its when one request does not provide enough information, so the app has to make more requests. so again like the library app a book endpoint might return the book details, but another request is needed to get information about its author.

GraphQL helps with both problems by letting the frontend specify the fields it needs. It can also request related information together, as long as your schema supports it.

Endpoint and schema philosophy 

A typical REST API has different endpoints for different resources, like '/books', '/author', and '/user'. The frontend choose the endpoint based on the information it needs, and the server determines what that endpoint returns.

GraphQL usually uses one endpoint, like `/graphql'. The query sent to that endpoint describes the information being requested.

GraphQL’s strongly typed schema defines the available fields, its data types, and how they connect. To me, this kinda makes frontend development easier because developers can see what information is available and what kind of response to expect. Development tools can use the schema to provide suggestions and identify invalid queries. This removes the guessing game when connecting your frontend to the backend.

Caching and Complexity

Caching means storing a result so it can be reused instead of retrieving the same information again. 
In REST HTTP caching simpler because GET requests use identifiable URLs, and the server can provide headers that control how responses are cached.

GraphQL now caching takes way more planning. Thats because different queries can go to the same endpoint and request different fields. Requests usually use POST and standard HTTP caches do not usually cache automatically. GraphQL can still use caching, but its setup must account for the query, variables, or individual records.

Like I said before I would choose REST for a smaller application with straightforward data needs. And I would consider maybe GraphQL for like a dashboard that combines users, orders, and products in different ways and because of the flexibility it could reduce extra requests and unnecessary data.