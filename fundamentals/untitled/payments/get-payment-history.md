# get-payment-history

{% api-method method="post" host="https://api.payant.ng/payments" path="" %}
{% api-method-summary %}
Get Payments
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Your Payant secret key prefixed with "Bearer "
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="start" type="string" required=false %}
Start Date DD/MM/YYYY
{% endapi-method-parameter %}

{% api-method-parameter name="end" type="string" required=false %}
End Date DD/MM/YYYY
{% endapi-method-parameter %}

{% api-method-parameter name="offset" type="string" required=false %}
Current Page. Defaults to `0`
{% endapi-method-parameter %}

{% api-method-parameter name="limit" type="string" required=false %}
Records to return count `1` - `50`
{% endapi-method-parameter %}

{% api-method-parameter name="method" type="string" required=false %}
Channel of payment received `Card`, `Bank`, `USSD`, `mCash`, `QR`
{% endapi-method-parameter %}

{% api-method-parameter name="client\_id" type="string" required=false %}
Client ID
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
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
    "payments": [
        { 
            "company_id": "1",
            "client_id": "1",
            "invoice_id": "1",
            "expense_id": "",
            "amount": "50000.00",
            "currency": "NGN",
            "transaction_date": "1482105600",
            "status": "success",
            "reference_code": "j9CbiTN0oJe4vWhglyS2",
            "payment_id": "",
            "referrer": "",
            "gateway_response": "",
            "message": "",
            "channel": "Cash",
            "type": "Invoice",
            "created_at": "2016-12-21 18:46:30",
            "updated_at": "2016-12-21 18:46:30",
            "id": 1,
            invoice: {
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
             },
             "client": {
                "id": 1
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
curl https://api.payant.ng/payments \
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
    "payments": [
        { 
            "company_id": "1",
            "client_id": "1",
            "invoice_id": "1",
            "expense_id": "",
            "amount": "50000.00",
            "currency": "NGN",
            "transaction_date": "1482105600",
            "status": "success",
            "reference_code": "j9CbiTN0oJe4vWhglyS2",
            "payment_id": "",
            "referrer": "",
            "gateway_response": "",
            "message": "",
            "channel": "Cash",
            "type": "Invoice",
            "created_at": "2016-12-21 18:46:30",
            "updated_at": "2016-12-21 18:46:30",
            "id": 1,
            invoice: {
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
             },
             "client": {
                "id": 1
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
    ]    
  }
}
```

