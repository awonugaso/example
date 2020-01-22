# get-wallet

{% api-method method="get" host="https://api.autocredit.ng/wallets/:reference\_code" path="" %}
{% api-method-summary %}
Get Wallet
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="reference\_code" type="string" required=true %}
Wallet reference code
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Autocredit secret key prefixed with "Bearer "
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
  "status": "success",
  "data": {
    "company_id": 1,
    "name": "John Doe Wallet",
    "balance": "0.00",
    "currency": "NGN",
    "status": "1",
    "reference_code": "PMojL342gd",
    "status": "1",
    "created_at": "2017-07-27 08:10:33",
    "updated_at": "2017-07-27 08:10:33",
    "id": 1
  }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## **Request**

```bash
curl https://api.autocredit.ng/wallets/PMojL342gd \
-H "Content-Type: application/json" \
-H "Authorization: Bearer SECRET_KEY" \
-X GET
```

## **Response**

```javascript
{
  "status": "success",
  "data": {
    "company_id": 1,
    "name": "John Doe Wallet",
    "balance": "0.00",
    "currency": "NGN",
    "status": "1",
    "reference_code": "PMojL342gd",
    "status": "1",
    "created_at": "2017-07-27 08:10:33",
    "updated_at": "2017-07-27 08:10:33",
    "id": 1
  }
}
```

