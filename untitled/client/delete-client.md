# delete-client

{% api-method method="delete" host="https://api.autocredit.ng/clients/:id" path="" %}
{% api-method-summary %}
Delete Client
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
  "message": "Client deleted successfully."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## **Request**

```javascript
curl https://api.autocredit.ng/clients/1 \
-H "Content-Type: application/json" \
-H "Authorization: Bearer SECRET_KEY" \
-X DELETE
```

## **Response**

```javascript
{
  "status": "success",
  "message": "Client deleted successfully."
}
```

