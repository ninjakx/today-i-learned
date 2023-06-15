- Date : 2023-06-15
- Tags : #Microservices

## API Composition Pattern in Microservices

source: [API Composition Pattern in Microservices](https://www.youtube.com/watch?v=5pYLlYsy6fQ)

 The API composition pattern is a way to query microservices by using an API composer or aggregator. The composer invokes individual microservices that own the data and combines the results by performing an in-memory join. This pattern simplifies the process of gathering data from multiple microservices and provides a unified interface for clients. However, it may not be suitable for complex queries and large datasets that require in-memory joins, and increasing the number of microservices connected to the API composer can decrease overall system availability and increase operational costs. Tools like API gateways can be used to implement API composition and improve the user experience by reducing latency and the number of API calls made by the client.


