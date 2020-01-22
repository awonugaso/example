# wallet-transactions

{% api-method method="post" host="https://api.payant.ng/wallets/transactions/:reference\_code" path="" %}
{% api-method-summary %}
Get Wallet Transactions
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
{% api-method-parameter name="period" type="string" required=true %}
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
    "start": "01/07/2017", 
    "end": "31/07/2017",
    "transactions": [
        { 
            "company_id": "1",
            "client_id": "",
            "invoice_id": "",
            "expense_id": "",
            "wallet_id": "1",
            "payment_id": "4342323",
            "transaction_date": "2017-07-26T19:51:31.000Z",
            "wallet_reference_code": "PMojL342gd",
            "amount": "5000.00",
            "currency": "NGN",
            "reference_code": "HeK01bEwiVRzcnAUGLf2",
            "referrer": "",
            "gateway_response": "Successful",
            "message": "",
            "channel": "Card",
            "disburse_status": "1",
            "disburse_ref": "",
            "disburse_response": "Successful",
            "settlement_bank": "",
            "account_number": "",
            "account_name": "",
            "type": "Funding",
            "status": "1",
            "created_at": "2016-12-21 18:46:30",
            "updated_at": "2016-12-21 18:46:30",
            "id": 1
        },
        { 
            "company_id": "1",
            "client_id": "",
            "invoice_id": "",
            "expense_id": "",
            "wallet_id": "1",
            "payment_id": "",
            "transaction_date": "2017-07-26T19:50:31.000Z",
            "wallet_reference_code": "PMojL342gd",
            "amount": "1500.00",
            "currency": "NGN",
            "reference_code": "v0rX5GbWsH4FZB63tnjh",
            "referrer": "",
            "gateway_response": "Successful",
            "message": "",
            "channel": "Card",
            "disburse_status": "1",
            "disburse_ref": "TTMW000345454546",
            "disburse_response": "Successful",
            "settlement_bank": "044",
            "account_number": "0000000000",
            "account_name": "Test",
            "type": "Withdrawal",
            "status": "1",
            "created_at": "2016-12-21 18:50:30",
            "updated_at": "2016-12-21 18:50:30",
            "id": 2
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
curl https://api.payant.ng/wallets/transactions/PMojL342gd \
-H "Content-Type: application/json" \
-H "Authorization: Bearer SECRET_KEY" \
-d '{ "period": "custom", 
 "start": "01/07/2017", 
 "end": "31/07/2017" }' \
-X POST
```

## Response

```javascript
{
  "status": "success",
  "data": {
    "period": "custom", 
    "start": "01/07/2017", 
    "end": "31/07/2017",
    "transactions": [
        { 
            "company_id": "1",
            "client_id": "",
            "invoice_id": "",
            "expense_id": "",
            "wallet_id": "1",
            "payment_id": "4342323",
            "transaction_date": "2017-07-26T19:51:31.000Z",
            "wallet_reference_code": "PMojL342gd",
            "amount": "5000.00",
            "currency": "NGN",
            "reference_code": "HeK01bEwiVRzcnAUGLf2",
            "referrer": "",
            "gateway_response": "Successful",
            "message": "",
            "channel": "Card",
            "disburse_status": "1",
            "disburse_ref": "",
            "disburse_response": "Successful",
            "settlement_bank": "",
            "account_number": "",
            "account_name": "",
            "type": "Funding",
            "status": "1",
            "created_at": "2016-12-21 18:46:30",
            "updated_at": "2016-12-21 18:46:30",
            "id": 1
        },
        { 
            "company_id": "1",
            "client_id": "",
            "invoice_id": "",
            "expense_id": "",
            "wallet_id": "1",
            "payment_id": "",
            "transaction_date": "2017-07-26T19:50:31.000Z",
            "wallet_reference_code": "PMojL342gd",
            "amount": "1500.00",
            "currency": "NGN",
            "reference_code": "v0rX5GbWsH4FZB63tnjh",
            "referrer": "",
            "gateway_response": "Successful",
            "message": "",
            "channel": "Card",
            "disburse_status": "1",
            "disburse_ref": "TTMW000345454546",
            "disburse_response": "Successful",
            "settlement_bank": "044",
            "account_number": "0000000000",
            "account_name": "Test",
            "type": "Withdrawal",
            "status": "1",
            "created_at": "2016-12-21 18:50:30",
            "updated_at": "2016-12-21 18:50:30",
            "id": 2
        }
    ]    
  }
}
```

