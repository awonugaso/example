# edit-product

{% api-method method="put" host="https://api.autocredit.ng/products/:reference\_code" path="" %}
{% api-method-summary %}
Edit Product
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="name" type="string" required=true %}
Product's name
{% endapi-method-parameter %}

{% api-method-parameter name="description" type="string" required=true %}
Product's description
{% endapi-method-parameter %}

{% api-method-parameter name="unit\_cost" type="string" required=true %}
Product's unit cost
{% endapi-method-parameter %}

{% api-method-parameter name="type" type="string" required=true %}
Product type `product` or `service`
{% endapi-method-parameter %}

{% api-method-parameter name="status" type="string" required=true %}
Product satus `1` or `0`
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
curl https://api.autocredit.ng/products/1 \
-H "Content-Type: application/json" \
-H "Authorization: Bearer SECRET_KEY" \
-d '{ "name": "Website Design",
    "description": "5 Pages Website plus 1 Year Web Hosting",
    "unit_cost": "50000.00",
    "type": "service",
    "status": "1" }' \
-X PUT
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=302 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
  "status": "success",
  "message": "Product updated successfully.",
  "data": {
    "company_id": 1,
    "name": "Website Design",
    "description": "5 Pages Website plus 1 Year Web Hosting",
    "unit_cost": "50000.00",
    "type": "service",
    "image": "default.png",
    "status": "1",
    "created_at": "2016-12-21 18:46:30",
    "updated_at": "2016-12-21 18:46:30",
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
curl https://api.autocredit.ng/products/1 \
-H "Content-Type: application/json" \
-H "Authorization: Bearer SECRET_KEY" \
-d '{ "name": "Website Design",
    "description": "5 Pages Website plus 1 Year Web Hosting",
    "unit_cost": "50000.00",
    "list_cost": "60000.00",    
    "status": "1" }' \
-X PUT
```

## Response

```javascript
{
  "status": "success",
  "message": "Product updated successfully.",
  "data": {
    "company_id": 1,
    "name": "Website Design",
    "description": "5 Pages Website plus 1 Year Web Hosting",
    "unit_cost": "50000.00",
    "type": "service",
    "image": "default.png",
    "status": "1",
    "created_at": "2016-12-21 18:46:30",
    "updated_at": "2016-12-21 18:46:30",
    "id": 1
  }
}
```

