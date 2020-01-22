# withdraw-from-wallet-bulk

{% api-method method="post" host="https://api.payant.ng/wallets/withdraw/bulk/:reference\_code" path="" %}
{% api-method-summary %}

{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="reference\_code" type="string" required=true %}
Wallet reference code
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Payant secret key prefixed by "Bearer "
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="recipients" type="array" required=true %}
Recipients see table below for structure
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
  "message": "Withdrawal queued for processing.",
  "data": { 
    "company_id": "1",
    "wallet_id": "1",
    "wallet_reference_code": "PMojL342gd",
    "currency": "NGN",
    "amount": "1500.00",
    "reference_code": "v0rX5GbWsH4FZB63tnjh",
    "type": "BulkWithdrawal",
    "channel": "Wallet",
    "status": "1",
    "disburse_recipients": "[{\"settlement_bank\":\"044\",\"account_number\":\"0000000000\",\"amount\":\"1500.00\"},{\"settlement_bank\":\"048\",\"account_number\":\"1111111111\",\"amount\":\"1000.00\"}]",
    "created_at": "2016-12-21 18:50:30",
    "updated_at": "2016-12-21 18:50:30",
    "id": 2
    "transaction_date": "2017-07-26T19:50:31.000Z",
    "payment_id": "",
    "referrer": "",
    "gateway_response": "Successful",
    "disburse_status": "1",
    "disburse_ref": "BATCH gaZbf8ULE1BwXnWzhcJq",
    "disburse_response": "Successful",
    "disburse_recipients_response": "{\"status\":\"success\",\"data\":{\"batchId\":1447,\"message\":\"Disbursement queued for processing.\"}}"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Recipients Data

| Parameter | **Description** |
| :--- | :--- |
| settlement\_bank _required_ | **String** Recipient's settlement bank |
| account\_number _required_ | **String** Recipient's account number |
| amount _required_ | **String** Amount to send |

## Request

```bash
curl https://api.payant.ng/wallets/withdraw/bulk/PMojL342gd \
-H "Content-Type: application/json" \
-H "Authorization: Bearer SECRET_KEY" \
-d '{ "recipients": [{
        "settlement_bank": "044",
        "account_number": "0000000000",
        "amount": "1500.00",
    },
    {
        "settlement_bank": "058",
        "account_number": "1111111111",
        "amount": "1000.00",
    }] }' \
-X POST
```

## Response

```javascript
{
  "status": "success",
  "message": "Withdrawal queued for processing.",
  "data": { 
    "company_id": "1",
    "wallet_id": "1",
    "wallet_reference_code": "PMojL342gd",
    "currency": "NGN",
    "amount": "1500.00",
    "reference_code": "v0rX5GbWsH4FZB63tnjh",
    "type": "BulkWithdrawal",
    "channel": "Wallet",
    "status": "1",
    "disburse_recipients": "[{\"settlement_bank\":\"044\",\"account_number\":\"0000000000\",\"amount\":\"1500.00\"},{\"settlement_bank\":\"048\",\"account_number\":\"1111111111\",\"amount\":\"1000.00\"}]",
    "created_at": "2016-12-21 18:50:30",
    "updated_at": "2016-12-21 18:50:30",
    "id": 2
    "transaction_date": "2017-07-26T19:50:31.000Z",
    "payment_id": "",
    "referrer": "",
    "gateway_response": "Successful",
    "disburse_status": "1",
    "disburse_ref": "BATCH gaZbf8ULE1BwXnWzhcJq",
    "disburse_response": "Successful",
    "disburse_recipients_response": "{\"status\":\"success\",\"data\":{\"batchId\":1447,\"message\":\"Disbursement queued for processing.\"}}"
}
```

