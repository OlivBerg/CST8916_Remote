# Assignment 1 - Stock Market

## Q1: Explain how both REST and GraphQL could be used to handle the data requests and updates required by the system.

- For REST, describe how different endpoints could be structured, and how requests such as GET, POST, PUT, and DELETE would manage data.
- or GraphQL, describe how queries and mutations could handle the same data operations and how this approach differs from REST.
- Compare the pros and cons of using REST versus GraphQL for your specific use case.

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
    createStock(ticker: "AAPL", period: " daily, hourly, 15min, 5min"){ // Apple ticker symbole
        ticker
        price
        volume
        ...
    }
}
```







### REST VS GraphQL

## Section 2: WebSockets for Real-time Communication

- Describe how WebSockets could be used to handle real-time communication in your chosen system.

- Discuss how WebSockets differ from REST and GraphQL in managing real-time data flow.

## Section 3: Technology Recommendation and Justification

Recommend which technology (or combination of technologies) you would choose for your system: REST, GraphQL, WebSockets, or a hybrid approach.

Justify your recommendation based on your analysis in Sections 1 and 2.

- Consider factors such as data complexity, real-time requirements, scalability, and ease of use for developers.
- Explain why this combination is best suited for your use case in terms of performance, scalability, and real-time capabilities.
