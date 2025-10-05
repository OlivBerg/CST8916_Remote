# Assignment 1 - Stock Market

## Q1: Explain how both REST and GraphQL could be used to handle the data requests and updates required by the system.

### Rest Implementation 
#### Important Definition

**Stocks** : Ticker symbol, company name, current price... (stock representation at current time of request)

**Quotes** : Timestamp, price, Volume... (Historical representation of the stock base on a period of time)


#### Basic Endpoint Structure and Request 
This a basic structure used to simulate data communication for our stock market app. These does not include all possible endpoints, but only include the basic structure to relay how such communication would be done in this scenario. 

##### **/stocks: Base endpoint**

- **GET /stocks :** Retrieves a list of all available stocks. Response can be made in a JSON array of stock object.

##### **/stocks/{ticker}: Operations specific to a stock using their ticker identifier**

- **GET /stocks/{ticker}:** Retrives detailed information about a specific stock ticker.
- **POST /stocks/{ticker} (users would typically not use this, but platform that that manages stock market data will):** Create a new stock.
- **PUT /stocks/{ticker} (users would typically not use this, but platform that that manages stock market data will):** used to update data of a stock
- **DELETE /stocks/{ticker} (users would typically not use this, but platform that that manages stock market data will):** delete a stock.

##### **/quotes/{ticker}: View historical quotes for a particular ticker**

- **GET /quotes/{ticker}:** Retrives historical data about a specific ticker. This request can be a large request as it is requesting data over a time period.

### GraphQL Implementation
GraphQL, as we learned in class uses a single point to handle any requests. Here are example using the our notes code snippets and GraphQL [documentation](https://graphql.org/learn/) as examples.

#### Retrieving/[Query](https://graphql.org/learn/queries/)  any stocks 

```
query{
    stocks(limit:10){
        ticker
        companyName
        currentPrice
    }
}
```
#### Retrieving/[Query](https://graphql.org/learn/queries/)  specific stocks  

```
query{
    stocks(ticker: "AAPL"){ // Apple ticker symbole
        ticker
        companyName
        currentPrice
        dailyHigh
        dailyLow
        ...
    }
}
```

#### Retrieving/[Query](https://graphql.org/learn/queries/) stock quote 

```
query{
    quote(ticker: "AAPL", period: " daily, hourly, 15min, 5min"){ // Apple ticker symbole
        ticker
        price
        volume
        ...
    }
}
```
#### Creating/[Mutating](https://graphql.org/learn/mutations/) stock 

```
mutation{
    createStock(ticker: "AAPL",companyName:"Apple", currentPrice: "199.99$" ){ // Apple ticker symbole
        ticker
        companyName
        currentPrice
        ...
    }
}
```
#### Updating/[Mutating](https://graphql.org/learn/mutations/) stock 

```
mutation{
    updateStock(ticker: "AAPL",companyName:"Apple Inc."){ // Apple ticker symbole
        ticker
        companyName
        ...
    }
}
```

#### Deleting/[Mutating](https://graphql.org/learn/mutations/) stock 

```
mutation{
    deleteStock(ticker: "AAPL",companyName:"Apple", currentPrice: "199.99$" ){ // Apple ticker symbole
        ticker
        companyName
        currentPrice
        ...
    }
}
```


### REST VS GraphQL

#### Pros of REST
- Simple and straightforward to setup. For simple systeme rest is best.
- REST is well-established and used widely. 

#### Cons of REST
- Over/under-Fetching
- Real-time communication mechanism limitation

#### Pros of GraphQL
- Avoides over/under-Fetching, gets you what you need at the request stage

#### Cons of GraphQL
- Real-time communication mechanism limitation


We would argue that GraphQL would be the slight superior system as it prevents data to be over or underfetch by the user. However, both lack mechanism to communicate in real-time.


## Section 2: WebSockets for Real-time Communication

### How would WebSockets work
WebSockets establishes a persistent bi-directional communication channel between the client and the server. This on its own already completely different form a REST and a GraphQL system. Here how this would implement in our scenario:

#### Connection (Handshake)
The client starts the connection to the server with an HTTP request/handshake. From that handshake the client demands a communication upgrade which proceeds the WebSocket connection over a TCP connction.

#### Bi-directional data communication
For example, when the Stock Platform gets updated data about a stock the the user is monitoring, that update is immadiately pushed to the user in a form of live graph or current live pricing. The great thing is that, the client does not need to make a new request to the server because the connection was never closed which eliminate the need to constanly refreshing the client.

### WebSockets vs REST & GraphQL

#### Request VS Push
Both REST and GraphQL both fundementaly rely on requests to work which in the scenario is their downfall. Request rely on the client to constantly be reqesting for data to work which can be slow and taxing. WebSockets Lets the server push data whenever the data is ready to be pushed. This is a fundamental difference between the two.

#### Connection Persistence
REST and GraphQL both use short-lived HTTP connections meaning once the data request has been completed, the connection is done. WebSockets on the other hand, uses persistent connection, meaning the connection will be open as long as the client the server are active.

#### Efficency
Both REST and GraphQL will waste bandwidth and server resources in a real time update usage because the client is constantly requesting more updates when the data has yet to have change. WebSockets will, because of the their persistent connection, update the user on its own without the need a new request. This will dramatically reduce latency and improve user experience. 












## Section 3: Technology Recommendation and Justification

Recommend which technology (or combination of technologies) you would choose for your system: REST, GraphQL, WebSockets, or a hybrid approach.

Justify your recommendation based on your analysis in Sections 1 and 2.

- Consider factors such as data complexity, real-time requirements, scalability, and ease of use for developers.
- Explain why this combination is best suited for your use case in terms of performance, scalability, and real-time capabilities.
