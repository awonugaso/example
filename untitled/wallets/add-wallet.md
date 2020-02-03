# add-wallet

{% api-method method="post" host="https://api.autocredit.ng/wallets" path="" %}
{% api-method-summary %}
Add Wallet
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Autocredit secret key prefixed with "Bearer "
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="settlementSchedule" type="string" required=true %}
Settlement schedule for wallet `T1` or `MANUAL`
{% endapi-method-parameter %}

{% api-method-parameter name="name" type="string" required=true %}
Wallet's name
{% endapi-method-parameter %}

{% api-method-parameter name="settlementCurrency" type="string" required=true %}
Settlement currency `NGN`
{% endapi-method-parameter %}

{% api-method-parameter name="settlementBank" type="string" required=true %}
Wallet's settlement bank
{% endapi-method-parameter %}

{% api-method-parameter name="accountNumber" type="string" required=true %}
Wallet's account number
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
  "status": "success",
  "message": "Wallet was added successfully.",
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

## Request

```bash
curl https://api.autocredit.ng/wallets \
-H "Content-Type: application/json" \
-H "Authorization: Bearer SECRET_KEY" \
-d '{ "name": "John Doe Wallet",
    "settlementCurrency": "NGN", 
    "settlementBank": "000013",
    "accountNumber": "0123456789",
    "settlementSchedule": "MANUAL" }' \
-X POST
```

## Response

```javascript
{
  "status": "success",
  "message": "Wallet was added successfully.",
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

