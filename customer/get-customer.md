# Get Customer

{% api-method method="get" host="https://api.autocredit.ng/clients/:id" path="" %}
{% api-method-summary %}
Get Client
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
Client ID
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
    "id": 1,
    "company_id": 1,
    "name": "Albert Specialist Hospital",
    "first_name": "Albert",
    "last_name": "Jane",
    "email": "jane@alberthospital.com",
    "phone": "+2348012345678",
    "website": "http://www.alberthospital.com",
    "address": "Wase II",
    "type": "Customer",
    "settlement_bank": "",
    "account_name": "",
    "account_number": "",
    "status": "1",
    "created_at": "2016-12-21 17:19:10",
    "updated_at": "2016-12-21 17:19:10",
    "deleted_at": null
  }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## **Request**

```bash
curl https://api.autocredit.ng/clients/1 \
-H "Content-Type: application/json" \
-H "Authorization: Bearer SECRET_KEY" \
-X GET
```

## **Response**

```javascript
{
  "status": "success",
  "data": {
    "id": 1,
    "company_id": 1,
    "name": "Albert Specialist Hospital",
    "first_name": "Albert",
    "last_name": "Jane",
    "email": "jane@alberthospital.com",
    "phone": "+2348012345678",
    "website": "http://www.alberthospital.com",
    "address": "Wase II",
    "type": "Customer",
    "settlement_bank": "",
    "account_name": "",
    "account_number": "",
    "status": "1",
    "created_at": "2016-12-21 17:19:10",
    "updated_at": "2016-12-21 17:19:10",
    "deleted_at": null
  }
}
```

