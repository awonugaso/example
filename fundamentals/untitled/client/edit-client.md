# edit-client

{% api-method method="put" host="https://api.payant.ng/clients/:id" path="" %}
{% api-method-summary %}
Edit Client
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
Payant secret key prefixed by "Bearer "
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="company\_name" type="string" required=false %}
Client's company full name
{% endapi-method-parameter %}

{% api-method-parameter name="first\_name" type="string" required=true %}
Client's first name
{% endapi-method-parameter %}

{% api-method-parameter name="last\_name" type="string" required=true %}
Client's last name
{% endapi-method-parameter %}

{% api-method-parameter name="email" type="string" required=true %}
Client's email
{% endapi-method-parameter %}

{% api-method-parameter name="phone" type="string" required=true %}
Client's phone number
{% endapi-method-parameter %}

{% api-method-parameter name="address" type="string" required=false %}
Client's address
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
  "message": "Client updated successfully.",
  "data": {
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
    "updated_at": "2016-12-21 17:23:31",
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
curl https://api.payant.ng/clients/1 \
-H "Content-Type: application/json" \
-H "Authorization: Bearer SECRET_KEY" \
-d '{ "company_name": "Albert Specialist Hospital",
    "first_name": "Albert",
    "last_name": "Jane",
    "email": "jane@alberthospital.com",
    "phone": "+2348012345678",
    "website": "http://www.alberthospital.com",
    "address": "Wase II" }' \
-X PUT
```

## Response

```javascript
{
  "status": "success",
  "message": "Client updated successfully.",
  "data": {
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
    "updated_at": "2016-12-21 17:23:31",
    "id": 1
  }
}
```

