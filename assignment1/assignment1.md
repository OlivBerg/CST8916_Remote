# Assignment 1 - Stock Market

## Q1: Explain how both REST and GraphQL could be used to handle the data requests and updates required by the system.

### Rest Implementation

#### Important Definition

**Stocks** : Ticker symbol, company name, current price... (stock representation at current time of request)

**Quotes** : Timestamp, price, Volume... (Historical representation of the stock base on a period of time)

#### Basic Endpoint Structure and Request

This is a basic structure used to simulate data communication for our stock market app. This does not include all possible endpoints, but only includes the basic structure to relay how such communication would be done in this scenario.

##### **/stocks: Base endpoint**

- **GET /stocks :** Retrieves a list of all available stocks. Response can be made in a JSON array of stock object.

##### **/stocks/{ticker}: Operations specific to a stock using their ticker identifier**

- **GET /stocks/{ticker}:** Retrives detailed information about a specific stock ticker.
- **POST /stocks/{ticker} (users would typically not use this, but platform that that manages stock market data will):** Create a new stock.
- **PUT /stocks/{ticker} (users would typically not use this, but platform that that manages stock market data will):** used to update data of a stock
- **DELETE /stocks/{ticker} (users would typically not use this, but platform that that manages stock market data will):** delete a stock.

##### **/quotes/{ticker}: View historical quotes for a particular ticker**

- **GET /quotes/{ticker}:** Retrieves historical data about a specific ticker. This request can be a large request as it is requesting data over a time period.

### GraphQL Implementation

GraphQL, as we learned in class, uses a single point to handle any requests. Here are examples using the our notes code snippets and GraphQL [documentation](https://graphql.org/learn/) as examples.

#### Retrieving/[Query](https://graphql.org/learn/queries/) any stocks

```
query{
    stocks(limit:10){
        ticker
        companyName
        currentPrice
    }
}
```

#### Retrieving/[Query](https://graphql.org/learn/queries/) specific stocks

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
- Can use subscription for real-time (uses Websockets)

#### Cons of GraphQL

- Real-time communication mechanism limitation
- Difficult to implement

We would argue that GraphQL would be the slightly superior system as it prevents data from being over or underfetched by the user. However, both lack mechanisms to communicate in real-time or are not easy to implement.

## Section 2: WebSockets for Real-time Communication

### How would WebSockets work

WebSockets establishes a persistent bi-directional communication channel between the client and the server. This is fundamentally different from a REST and a GraphQL system. Here’s how this would be implemented in our scenario:

#### Connection (Handshake)

The client starts the connection to the server with an HTTP request/handshake. From that handshake, the client demands a communication upgrade, which proceeds the WebSocket connection over a TCP connection.

#### Bi-directional data communication

For example, when the Stock Platform gets updated data about a stock that the user is monitoring, that update is immediately pushed to the user in the form of a live graph or current live pricing. The great thing is that the client does not need to make a new request to the server because the connection was never closed, which eliminates the need to constantly refresh the client.

### WebSockets vs REST & GraphQL

#### Request VS Push

Both REST and GraphQL both fundementaly rely on requests to work which in the scenario is their Downfall: Request relies on the client to constantly be requesting data to work, which can be slow and taxing. WebSockets lets the server push data whenever the data is ready to be pushed. This is a fundamental difference between the two.

#### Connection Persistence

REST and GraphQL both use short-lived HTTP connections, meaning once the data request has Once completed, the connection is done. WebSockets, on the other hand, uses a persistent connection, meaning the connection will be open as long as the client and the server are active.

#### Efficency

Both REST and GraphQL will waste bandwidth and sEver resources in a real-time update usage because the client is constantly requesting more updates when the data has yet to have changed. WebSockets will, because of their persistent connection, update the user on its own without the need for a new request. This will dramatically reduce latency and improve user experience.

## Section 3: Technology Recommendation and Justification

### Our Recommendation

Use **GraphQL for requests and updates** and **WebSockets through GraphQL Subscriptions** for all **real-time** data.

- **GraphQL queries and mutations:** snapshot reads like current stock details and watchlists, and controlled writes like adding or removing items from a watchlist and setting alert rules.
- **GraphQL Subscriptions over WebSockets:** continuous push of live quotes and small deltas such as price, volume, and timestamp as soon as they change.

---

### What GraphQL Handles: Requests and Updates

GraphQL is our single request response API for structured data. It helps avoid over-fetching and under-fetching by letting the client ask for exactly the fields it needs.

- **Reads**
  - Load a user’s watchlist and the current fields for those tickers.
  - Get paged historical quotes to draw charts without huge one-shot payloads.

- **Writes**
  - Manage watchlists: `addToWatchlist`, `removeFromWatchlist`.
  - Manage alert rules: `setPriceAlert`.
  - Update user preferences, such as preferred intervals.

**Example query:**
```graphql
query {
  stock(ticker: "AAPL") {
    ticker
    companyName
    currentPrice
    dailyHigh
    dailyLow
  }
}
```
### *Example (mutation):*

```graphql
mutation {
  setPriceAlert(ticker: "AAPL", threshold: 199.50) {
    ticker
    threshold
    active
  }
}
```
### What WebSockets Handle: Real-time with GraphQL Subscriptions

WebSockets provide a **persistent**, bi-directional channel so the server can **push** updates immediately. Using **GraphQL Subscriptions** on top of that channel keeps real-time events aligned with the same schema and types as queries/mutations.

- The client subscribes to the tickers it is viewing.
- The server pushes small `PRICE_UPDATE` events as soon as the market data changes.

### *Example (subscription):*
```graphql
subscription {
  priceUpdated(ticker: "AAPL") {
    ticker
    price
    volume
    ts
  }
}
```
### Why this is best for the stock market

**Low latency:**  
Subscriptions over WebSockets remove polling. Prices appear as soon as they change, which is important for a market scenario.

**Network efficiency:**  
GraphQL returns only the fields needed for each view. Subscriptions send small deltas like price, volume, and timestamp instead of full documents, which saves bandwidth.

**Throughput:**  
One WebSocket connection can carry many subscriptions for a single user. On the server, updates for a ticker can be broadcast to all subscribers efficiently.

**Scaling:**  
- **GraphQL layer:** stateless resolvers can scale behind a load balancer.  
- **Subscriptions layer:** WebSocket servers can scale out; subscriber registries can be shared so any node can publish updates to all interested clients.  
- **Data access:** historical queries are paged and cache-friendly; live streams are frequent but lightweight.

---

### Why GraphQL Subscriptions instead of plain WebSockets

- **One schema for everything:** queries, mutations, and live events share the same types and naming.
- **Ask for only what you need:** the subscription document selects fields, so payloads stay small.
- **Built-in filtering:** arguments on the subscription act as filters, such as `ticker: "AAPL"`.
- **Many streams over one socket:** multiple subscriptions can share a single connection in a standard way.

## Contributions

### Olivie Bergeron --> Answered Question 1 and 2
I used the ProofRead WritingTool function on Mac to correct my grammar and sentence structures and I used AI to summaries my notes taken in class/from the slides. My AI application was limited to the above. No AI was used to directly answer any of the question above.
### Obaida Kandakji --> Answered Question 3 and Video
I used AI for the formatting and structuring of my markdown code. Solutions come from class notes and Codezup graphql and websockets article for better understanding of material.
