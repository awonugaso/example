# Get Invoices

{% api-method method="get" host="https://api.autocredit.ng/invoices" path="" %}
{% api-method-summary %}
Get Invoice History
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
{% api-method-parameter name="period" type="string" required=false %}
History period `today`, `week`, `month`, `30`, `90`, `year` or `custom`
{% endapi-method-parameter %}

{% api-method-parameter name="start" type="string" required=false %}
Starting date `DD/MM/YYYY`
{% endapi-method-parameter %}

{% api-method-parameter name="end" type="string" required=false %}
End date `DD/MM/YYYY`
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
  "data": {
    "period": "custom", 
    "start": "01/12/2016", 
    "end": "31/12/2016",
    "invoices": [
        { 
            "id": 1,
            "company_id": "1",
            "client_id": "1",
            "reference_code": "j9CbiTN0oJe4vWhglyS2",
            "payment_id": null,
            "fee_bearer": "client",
            "mail_status": "unsent",
            "status": "0",
            "due_date": "1483056000",
            "created_at": "2016-12-21 18:46:30",
            "updated_at": "2016-12-21 18:46:30",
            "deleted_at": null,
            "client": {
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
            },
            "items": [
                {
                    "id": "1",
                    "company_id": "1",
                    "client_id": "1",
                    "name": "Website Design",
                    "description": "5 Pages Website plus 1 Year Web Hosting",
                    "quantity": "1",
                    "unit_cost": "50000.00",
                    "status": "0",
                    "due_date": "1483056000",
                    "created_at": "2016-12-21 17:19:10",
                    "updated_at": "2016-12-21 17:19:10",
                    "deleted_at": null
                }
            ]
        }
    ]    
  }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Request

```bash
curl https://api.autocredit.ng/invoices \
-H "Content-Type: application/json" \
-H "Authorization: Bearer SECRET_KEY" \
-X POST
```

## Response

```javascript
{
  "status": "success",
  "data": {
    "period": "custom", 
    "start": "01/12/2016", 
    "end": "31/12/2016",
    "invoices": [
        { 
            "id": 1,
            "company_id": "1",
            "client_id": "1",
            "reference_code": "j9CbiTN0oJe4vWhglyS2",
            "payment_id": null,
            "fee_bearer": "client",
            "mail_status": "unsent",
            "status": "0",
            "due_date": "1483056000",
            "created_at": "2016-12-21 18:46:30",
            "updated_at": "2016-12-21 18:46:30",
            "deleted_at": null,
            "client": {
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
            },
            "items": [
                {
                    "id": "1",
                    "company_id": "1",
                    "client_id": "1",
                    "name": "Website Design",
                    "description": "5 Pages Website plus 1 Year Web Hosting",
                    "quantity": "1",
                    "unit_cost": "50000.00",
                    "status": "0",
                    "due_date": "1483056000",
                    "created_at": "2016-12-21 17:19:10",
                    "updated_at": "2016-12-21 17:19:10",
                    "deleted_at": null
                }
            ]
        }
    ]    
  }
}
```

