# add-invoice

{% api-method method="post" host="https://api.payant.ng/invoices" path="" %}
{% api-method-summary %}
Add Invoice
{% endapi-method-summary %}

{% api-method-description %}
Add Invoices
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Your Payant API Key prefixed with "Bearer "
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="payment\_methods" type="string" required=false %}
Payment methods to be allowed on this invoice seperated by comma "**,**" `card`, `account`, `phone`, `qr`
{% endapi-method-parameter %}

{% api-method-parameter name="currency" type="string" required=false %}
3 Character currency code for invoice `NGN` or `USD`
{% endapi-method-parameter %}

{% api-method-parameter name="client" type="array" required=true %}
Client Data - See Table Below for Structure
{% endapi-method-parameter %}

{% api-method-parameter name="client\_id" type="string" required=true %}
Client ID - Only required if `client` above does not exist in request.
{% endapi-method-parameter %}

{% api-method-parameter name="due\_date" type="string" required=true %}
Invoice due date MM/DD/YYYY
{% endapi-method-parameter %}

{% api-method-parameter name="free bearer" type="string" required=true %}
Invoice fee bearer `account` or `client`
{% endapi-method-parameter %}

{% api-method-parameter name="tokenize" type="string" required=false %}
Tokenize card used to make payment for this invoice `true` or `false`, defaults to false.
{% endapi-method-parameter %}

{% api-method-parameter name="card\_token" type="string" required=false %}
Card token generated from a tokenized transaction to automatically make payment for this invoice.
{% endapi-method-parameter %}

{% api-method-parameter name="items" type="array" required=true %}
Invoice items - See Table Below for Structure
{% endapi-method-parameter %}

{% api-method-parameter name="merchant\_ref" type="string" required=false %}
Merchant's unique invoice reference code
{% endapi-method-parameter %}

{% api-method-parameter name="metadata" type="string" required=false %}
Key-value pairs object
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
  "message": "Invoice created successfully.",
  "data": {
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
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Client Data

| Parameters | **Description** |
| :--- | :--- |


<table>
  <thead>
    <tr>
      <th style="text-align:left">company_name</th>
      <th style="text-align:left">
        <p><b>String</b>
        </p>
        <p>Client&apos;s company or full name</p>
      </th>
    </tr>
  </thead>
  <tbody></tbody>
</table>| first\_name required | **String** Client's first name |
| :--- | :--- |


| last\_name required | **String** Client's last name |
| :--- | :--- |


| email required | **String** Client's email address |
| :--- | :--- |


<table>
  <thead>
    <tr>
      <th style="text-align:left">email_cc</th>
      <th style="text-align:left">
        <p><b>String</b>
        </p>
        <p>Comma separated emails to copy for invoices and payment receipts</p>
      </th>
    </tr>
  </thead>
  <tbody></tbody>
</table>| phone required | **String** Client's phone number |
| :--- | :--- |


| address | **String** Client's address |
| :--- | :--- |


| Parameter | **Description** |
| :--- | :--- |


<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>item</p>
        <p><em>required</em>
        </p>
      </th>
      <th style="text-align:left">
        <p><b>String</b>
        </p>
        <p>Item&apos;s name</p>
      </th>
    </tr>
  </thead>
  <tbody></tbody>
</table>| description _required_ | **String** Item's description |
| :--- | :--- |


| unit\_cost _required_ | **String** Item's unit cost |
| :--- | :--- |


| quantity _required_ | **String** Item's quantity |
| :--- | :--- |


{% hint style="info" %}
**Heads up!**

Please contact [Payant Support](https://payant.ng/support) for you to start tokenizing cards and accepting recurring payments.
{% endhint %}

{% hint style="warning" %}
**Heads up!**

Only one of `client` or `client_id` is required per invoice. The `client` parameter will allow you to add a new customer while invoicing on the fly in case you don't have a `client_id`. Client will not be added if already exist.
{% endhint %}

## Request

```bash
curl https://api.payant.ng/invoices \
-H "Content-Type: application/json" \
-H "Authorization: Bearer SECRET_KEY" \
-d '{ "client": {
            "first_name": "Albert",
            "last_name": "Jane",
            "email": "jane@alberthospital.com",
            "phone": "+2348012345678"
        },
        "due_date": "12/30/2016",
        "fee_bearer": "client",
        "items": [
            "item": "Website Design",
            "description": "5 Pages Website plus 1 Year Web Hosting",
            "unit_cost": "50000.00",
            "quantity": "1"
        ] 
    }' \
-X POST
```

## Response

```javascript
{
  "status": "success",
  "message": "Invoice created successfully.",
  "data": {
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
}
```

