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

```
{ 
    "lendRates": [{
        "apr": 0.08458234,
        "apy": 0.08712394,
        "tokenSymbol": "USDC"
    }], 

    "borrowRates": [{
        "apr": 0.08458234,
        "apy": 0.08712394,
        "tokenSymbol": "USDC"
    }] 
}
```

* **`500: Internal Server Error`**\
  Could not fetch rates

```
{ "statusCode": 500, message: "Unable to fetch rates" }
```
{% endtab %}
{% endtabs %}
