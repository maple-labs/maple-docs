---
description: Authentication related resolvers for Maple Finance
---

# Auth

{% api-method method="post" host="https://api.maple.finance" path="/auth/:address" %}
{% api-method-summary %}
Get Auth Challenge
{% endapi-method-summary %}

{% api-method-description %}
The message \(x-auth-message\) is obtained here, which can be then used for signing \(x-auth-signature\)
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="address" type="string" required=true %}
The Ethereum address that has been used to sign on your wallet \(MetaMask/WalletConnect\)
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
A valid cryptic message is sent.
{% endapi-method-response-example-description %}

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
{% endapi-method-response-example %}

{% api-method-response-example httpCode=403 %}
{% api-method-response-example-description %}
If address is badly formatted or invalid.
{% endapi-method-response-example-description %}

```
{ "message": "BAD_ADDRESS" }
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://api.maple.finance" path="/signature/check" %}
{% api-method-summary %}
Check Signature
{% endapi-method-summary %}

{% api-method-description %}
Checks for valid signature, ensuring authentication.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="x-auth-signature" type="string" required=true %}
The cryptographic signature, which is received from either MetaMask or any other signing Ethereum wallet.
{% endapi-method-parameter %}

{% api-method-parameter name="x-auth-message" type="string" required=true %}
The message received from the above endpoint
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
The message and signature match and the right user address is sent
{% endapi-method-response-example-description %}

```
{
    "owner": "0x3489Dee7e8Fcec81F15e1C00209781779C5AAFF1"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=403 %}
{% api-method-response-example-description %}
If address is badly formatted or invalid, or if signature invalid
{% endapi-method-response-example-description %}

```
{ "message": "BAD_ADDRESS" / "BAD_SIGNATURE" }
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

