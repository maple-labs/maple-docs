---
description: Authentication related resolvers for Maple Finance
---

# Auth

{% swagger baseUrl="https://api.maple.finance" path="/auth/:address" method="get" summary="Get Auth Challenge" %}
{% swagger-description %}
The message (x-auth-message) is obtained here, which can be then used for signing (x-auth-signature)
{% endswagger-description %}

{% swagger-parameter in="path" name="address" type="string" %}
The Ethereum address that has been used to sign on your wallet (MetaMask/WalletConnect)
{% endswagger-parameter %}

{% swagger-response status="200" description="A valid cryptic message is sent." %}
```
{
    "data": {
        "challenge": [
            { "value": "Maple Finance Authentication" },
            { "value": "<challenge bound with cipher content"> }
        ]
    }
}
```
{% endswagger-response %}

{% swagger-response status="403" description="If address is badly formatted or invalid." %}
```
{ "message": "BAD_ADDRESS" }
```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="https://api.maple.finance" path="/signature/check" method="get" summary="Check Signature" %}
{% swagger-description %}
Checks for valid signature, ensuring authentication.
{% endswagger-description %}

{% swagger-parameter in="header" name="x-auth-signature" type="string" %}
The cryptographic signature, which is received from either MetaMask or any other signing Ethereum wallet.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="x-auth-message" type="string" %}
The message received from the above endpoint
{% endswagger-parameter %}

{% swagger-response status="200" description="The message and signature match and the right user address is sent" %}
```
{
    "owner": "0x3489Dee7e8Fcec81F15e1C00209781779C5AAFF1"
}
```
{% endswagger-response %}

{% swagger-response status="403" description="If address is badly formatted or invalid, or if signature invalid" %}
```
{ "message": "BAD_ADDRESS" / "BAD_SIGNATURE" }
```
{% endswagger-response %}
{% endswagger %}
