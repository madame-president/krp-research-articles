# Overview

This article describes a proof of concept method for retrieving historical transaction data, using the REST API service by [mempool.space](https://mempool.space/docs/api/rest).

This program has multiple functionalities, including:

- Fetching transaction details
- Calculating net amounts sent or received
- Logging bitcoin prices

## Dependencies

- `requests`: to handle HTTP requests
- `datetime`: to handle dates and timestamps

## Code-base

- `get_transactions`:

```bash
    def get_transactions(user_address):
    fetched_transactions = []
    address_url = "https://mempool.space/api/address/"
    endpoint = f"{address_url}{user_address}/txs"

    after_txid = None # To handle better pagination = None {first request}
    while True:
        # If after_txid is set, append it to the endpoint URL
        # to fetch the next page of confirmed transactions
        url = f"{endpoint}?after_txid={after_txid}" if after_txid else endpoint

        response = requests.get(url)
        if response.status_code == 200:
            paginated_transactions = response.json()
            if not paginated_transactions:
                break #Exit loop if no more transactions are returned

            fetched_transactions.extend(paginated_transactions)
            # Updates after_txid for the next page with the last confirmed tx's tx_id
            # Sorts newest to oldest
            after_txid = paginated_transactions[-1]['txid']
        else:
            print(f"Failed retreiving transactions,"
                    f" status code: {response.status_code}")
            break

    return fetched_transactions
```
- `get_price`:

```bash
    def get_price(currency='USD', timestamp=None):
    historical_price_url = f"https://mempool.space/api/v1/historical-price?currency={currency}&timestamp={timestamp}"
    response = requests.get(historical_price_url)
    if response.status_code == 200:
        data = response.json()
        if data['prices']:
            price_data = data['prices'][0]
            # Return the price in requested currency
            return price_data[currency]
        else:
            return None
    else:
            return None
```

### Details

The functions `get_transactions` and `get_price` are part of a much larger repository, but they serve as references.

### Author

Norma Escobar
*nescobar@krpgroup.com*

