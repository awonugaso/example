# delete-invoice

{% api-method method="delete" host="https://api.autocredit.ng/invoices/:reference\_code" path="" %}
{% api-method-summary %}
Delete Invoice
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="reference\_code" type="string" required=true %}
Invoice reference code
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Autocredit secret key prefixed by "Bearer "
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## **Request**

```bash
curl https://api.autocredit.ng/invoices/j9CbiTN0oJe4vWhglyS2 \
-H "Content-Type: application/json" \
-H "Authorization: Bearer SECRET_KEY" \
-X DELETE
```

## **Response**

```javascript
{
  "status": "success",
  "message": "Invoice deleted successfully."
}
```

