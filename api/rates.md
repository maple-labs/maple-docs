---
description: Maple Lend and Borrow rates
---

# Rates

### Get Lending and Borrowing Rates

#### URL: [https://api.maple.finance/rates](https://api.maple.finance/rates)

{% tabs %}
{% tab title="Response" %}
* **`200: OK`**\
  Borrow and lend rates successfully retrieved

```json
{
    "lendRates": [
        {
            "apr": 0.08909545157218274,
            "tokenSymbol": "USDC",
            "apy": 0.09142956489738086
        }
    ],
    "borrowRates": [
        {
            "apr": 0,
            "tokenSymbol": "USDC",
            "apy": 0
        }
    ]
}
```

* **`500: Internal Server Error`**\
  Could not fetch rates

```json
{
  "statusCode": 500,
  "message": "Unable to fetch rates"
}
```
{% endtab %}
{% endtabs %}
