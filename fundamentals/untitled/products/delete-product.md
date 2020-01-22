# delete-product

{% api-method method="delete" host="https://api.payant.ng/products/:reference\_code" path="" %}
{% api-method-summary %}
Delete Product
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
  "status": "success",
  "message": "Product deleted successfully."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## **Request**

```bash
curl https://api.payant.ng/products/1 \
-H "Content-Type: application/json" \
-H "Authorization: Bearer SECRET_KEY" \
-X DELETE
```

## **Response**

```javascript
{
  "status": "success",
  "message": "Product deleted successfully."
}
```

