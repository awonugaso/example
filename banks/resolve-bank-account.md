# Resolve Bank Account

{% api-method method="post" host="https://api.autocredit.ng/resolve-account" path="" %}
{% api-method-summary %}
Resolve Bank Account
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=false %}
Autocredit secret key prefixed with "Bearer "
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="account\_number" type="string" required=false %}
Customers NUBAN account number
{% endapi-method-parameter %}

{% api-method-parameter name="settlement\_bank" type="string" required=false %}
6 digit bank code gotten from Get Banks
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
  "message": "Account resolved successfully.",
  "data": {
    "settlement_bank": 058,
    "account_number": "01234567890",
    "account_name": "JANE, ALBERT SPECIALIST HOSPITAL"
  }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## **Request**

```bash
curl https://api.autocredit.ng/resolve-account \
-H "Content-Type: application/json" \
-H "Authorization: Bearer SECRET_KEY" \
-d '{ "settlement_bank": "058",
      "account_number": "0123456789" }' \
-X POST
```

## **Response**

```javascript
{
  "status": "success",
  "message": "Account resolved successfully.",
  "data": {
    "settlement_bank": 058,
    "account_number": "01234567890",
    "account_name": "JANE, ALBERT SPECIALIST HOSPITAL"
  }
}
```

