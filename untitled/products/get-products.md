# get-products

{% api-method method="get" host="https://api.autocredit.ng/products" path="" %}
{% api-method-summary %}
Get Products
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
  "data": [
    {
        "id": 1
        "company_id": 1,
        "name": "Website Design",
        "description": "5 Pages Website plus 1 Year Web Hosting",
        "unit_cost": "50000.00",
        "type": "service",
        "image": "default.png",
        "status": "1",
        "created_at": "2016-12-21 18:46:30",
        "updated_at": "2016-12-21 18:46:30",
        "deleted_at": null
    }
  ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## **Request**

```bash
curl https://api.autocredit.ng/products \
-H "Content-Type: application/json" \
-H "Authorization: Bearer SECRET_KEY" \
-X GET
```

## **Response**

```javascript
{
  "status": "success",
  "data": [
    {
        "id": 1
        "company_id": 1,
        "name": "Website Design",
        "description": "5 Pages Website plus 1 Year Web Hosting",
        "unit_cost": "50000.00",
        "type": "service",
        "image": "default.png",
        "status": "1",
        "created_at": "2016-12-21 18:46:30",
        "updated_at": "2016-12-21 18:46:30",
        "deleted_at": null
    }
  ]
}
```

