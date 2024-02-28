# Currency Exchange API

This is a simple API built with SpringBoot and Kotlin for currency exchange operations.

## Endpoints

- `POST /currencyExchange`: Exchanges one currency to another. The request body should be in the following format:

```json
{
  "from_currency": "EUR",
  "to_currency": "PLN",
  "amount": 123.33,
  "date": "2023-01-01"
}
```

- `POST /currency`: Adds new currency rates. The request body should be in the following format:

```json
{
  "currencies": [
    {
      "currency": "EUR",
      "price_pln": "4.31",
      "date": "2023-01-01"
    },
    {
      "currency": "EUR",
      "price_pln": "3.98",
      "date": "2023-01-01"
    }
  ]
}
```

- `GET /currency`: Retrieves all currency rates.

## Testing

You can test the API using the provided `test.http` file in IntelliJ. Each request is separated by `###`. You can click on the green arrow to the left of each request to run it. Please replace `localhost:8080` with your server's address and port if they are different.

Alternatively, you can use `curl` commands in the terminal to test the API. Here are the commands for each endpoint:

- `POST /currencyExchange`:

```bash
curl -X POST -H "Content-Type: application/json" -d '{
  "from_currency": "EUR",
  "to_currency": "PLN",
  "amount": 123.33,
  "date": "2023-01-01"
}' http://localhost:8080/currencyExchange
```

- `POST /currency`:

```bash
curl -X POST -H "Content-Type: application/json" -d '{
  "currencies": [
    {
      "currency": "EUR",
      "price_pln": "4.31",
      "date": "2023-01-01"
    },
    {
      "currency": "EUR",
      "price_pln": "3.98",
      "date": "2023-01-01"
    }
  ]
}' http://localhost:8080/currency
```

- `GET /currency`:

```bash
curl -X GET http://localhost:8080/currency
```

Please replace `localhost:8080` with your server's address and port if they are different.

## Credits

This project is based on the [spring initializr](https://start.spring.io/).
