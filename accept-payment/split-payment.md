---
description: >-
  The Autocredit's Inline API can be extended to allow split payments. This
  allows you to invoice your customers and split the payment between several
  wallets.
---

# Split Payment

## **Rules**

1. The split type must either be `flat` or `percentage`.
2. When splitting by a`flat` amount, the total values in the receivers array must equal the total invoice amount.
3. When splitting by `percentage`, the total values in the receivers array must equal 100%.
4. Split transactions must have at least 2 receivers and at most 6 receivers.
5. One of the receivers must always be marked primary.

## **Fee Bearer**

Fees are applied to split transactions the same way fees are applied to normal transactions on Autocredit. The only difference is that when the `fee_bearer` of the invoice is an`account`, you can specify who bearers the fees in the split transaction. You can either spread the transaction fees across the receivers or choose a single receiver to bear the fees. When the selected receiver's settlement value is less than the fees, we would automatically spread fees across all receivers.

{% api-method method="options" host="" path="" %}
{% api-method-summary %}
Split payment
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
{% api-method-parameter name="key" type="string" required=true %}
API Public key
{% endapi-method-parameter %}

{% api-method-parameter name="reference\_code" type="string" required=true %}
Invoice refence code if it already exists
{% endapi-method-parameter %}

{% api-method-parameter name="client" type="object" required=true %}
Client Data
{% endapi-method-parameter %}

{% api-method-parameter name="company\_name" type="string" required=true %}
Client's company name
{% endapi-method-parameter %}

{% api-method-parameter name="first\_name" type="string" required=true %}
Client's first name
{% endapi-method-parameter %}

{% api-method-parameter name="last\_name" type="string" required=true %}
Client's last name
{% endapi-method-parameter %}

{% api-method-parameter name="email" type="string" required=true %}
Client's email
{% endapi-method-parameter %}

{% api-method-parameter name="phone" type="string" required=true %}
Client's number
{% endapi-method-parameter %}

{% api-method-parameter name="address" type="string" required=false %}
Client's address
{% endapi-method-parameter %}

{% api-method-parameter name="type" type="string" required=false %}
Client's type, `customer`, `staff` or `vendor`
{% endapi-method-parameter %}

{% api-method-parameter name="settlement\_bank" type="string" required=false %}
Client's settlement bank
{% endapi-method-parameter %}

{% api-method-parameter name="account\_number" type="string" required=false %}
Client's account number
{% endapi-method-parameter %}

{% api-method-parameter name="client\_id" type="string" required=true %}
Client ID
{% endapi-method-parameter %}

{% api-method-parameter name="due\_date" type="string" required=true %}
Invice Due date `MM/DD/YYYY`
{% endapi-method-parameter %}

{% api-method-parameter name="fee\_bearer" type="string" required=true %}
Invoice fee bearer, `account` or `client`
{% endapi-method-parameter %}

{% api-method-parameter name="items" type="array" required=true %}
Invoice items
{% endapi-method-parameter %}

{% api-method-parameter name="item" type="string" required=false %}
Item's name
{% endapi-method-parameter %}

{% api-method-parameter name="description" type="string" required=true %}
Item's description
{% endapi-method-parameter %}

{% api-method-parameter name="unit\_cost" type="string" required=true %}
Item's unit cost
{% endapi-method-parameter %}

{% api-method-parameter name="quantity" type="string" required=true %}
Item's quantity
{% endapi-method-parameter %}

{% api-method-parameter name="tokenize" type="string" required=false %}
Tokenize card, `True` or `false`, default is `false`
{% endapi-method-parameter %}

{% api-method-parameter name="payment\_methods" type="array" required=false %}
Payment method to show on checkout can be a combination of `card`, `bank`, `phone` and `QR`. Example `["card", "phone"]` for card and phone payments only.
{% endapi-method-parameter %}

{% api-method-parameter name="split\_details" type="object" required=false %}
Split details
{% endapi-method-parameter %}

{% api-method-parameter name="type" type="string" required=false %}
Split type `percentage` or `flat`
{% endapi-method-parameter %}

{% api-method-parameter name="fee\_bearer" type="string" required=true %}
Fee bearer `client`, `each_receiver` or `primary_receiver`
{% endapi-method-parameter %}

{% api-method-parameter name="receivers" type="array" required=true %}
Split Receivers
{% endapi-method-parameter %}

{% api-method-parameter name="wallet\_reference\_code" type="string" required=true %}
Waller Reference code
{% endapi-method-parameter %}

{% api-method-parameter name="value" type="string" required=false %}
Value
{% endapi-method-parameter %}

{% api-method-parameter name="primary" type="string" required=true %}
Primary `true` or `false`
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```markup
<form>
  <script src="https://api.autocredit.ng/assets/js/inline.min.js"></script>
  <button type="button" onclick="payWithPayant()"> Pay </button> 
</form>

<script>
  function payWithPayant() {
    var handler = Autocredit.invoice({
      "key": "e47aa44e4a320ae2a2b6b8804a4d2fa1b74437ab",
      "client": {
            "first_name": "Albert",
            "last_name": "Jane",
            "email": "jane@alberthospital.com",
            "phone": "+2348012345678"
        },
      "due_date": "12/30/2016",
      "fee_bearer": "account",
      "items": [
        {
          "item": ".Com Domain Name Registration",
          "description": "alberthostpital.com",
          "unit_cost": "2500.00",
          "quantity": "1"
        }
      ],
      "split_details": {
        "type": "percentage",
        "fee_bearer": "each_receiver",
        "receivers": [
        {
          "wallet_reference_code": "xVKsW9vnpI",
          "value": "30",
          "primary": "true"
        },
        {
          "wallet_reference_code": "9vnpIxVKsW",
          "value": "70",
          "primary": "false"
        }
      ]
    },
      callback: function(response) {
        console.log(response);
      },
      onClose: function() {
        console.log('Window Closed.');
      }
    });

    handler.openIframe();
  }
</script>Sp
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="info" %}
**Heads up!**

Only one of `client` or `client_id` is required per invoice object. The `client` parameter will allow you to add a new customer while invoicing on the fly in case you don't have a `client_id`. Client will not be added if already exist. All fields are not required if `reference_code` is available.
{% endhint %}

