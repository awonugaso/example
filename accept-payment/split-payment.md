---
description: >-
  Autocredit's Inline API can be extended to allow split payments. This allows
  you to split the payment between several revenue accounts.
---

# Split Payment

## **Rules**

1. The split type must either be `flat` or `percentage`.
2. When splitting by a`flat` amount, the total values in the receivers array must equal the total invoice amount.
3. When splitting by `percentage`, the total values in the receivers array must equal 100%.

## **Fee Bearer**

Fees are applied to split transactions the same way fees are applied to normal transactions on Autocredit. 

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

{% api-method-parameter name="orderid" type="string" required=true %}
Unique Invoice orderid 
{% endapi-method-parameter %}

{% api-method-parameter name="revhead\_id" type="object" required=true %}
Revenue ID 
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

{% api-method-parameter name="- settlement\_bank" type="string" required=false %}
Client's settlement bank
{% endapi-method-parameter %}

{% api-method-parameter name="client\_id" type="string" required=false %}
Client ID
{% endapi-method-parameter %}

{% api-method-parameter name="fee\_bearer" type="string" required=true %}
Invoice fee bearer, `merchant` or `client`
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

{% api-method-parameter name="split\_details" type="object" required=false %}
Split details
{% endapi-method-parameter %}

{% api-method-parameter name="type" type="string" required=false %}
Split type `percentage` or `flat`
{% endapi-method-parameter %}

{% api-method-parameter name="fee\_bearer" type="string" required=true %}
Fee bearer `merchant` or `client`
{% endapi-method-parameter %}

{% api-method-parameter name="subAccountCode" type="array" required=true %}
Revenue ID for slip 
{% endapi-method-parameter %}

{% api-method-parameter name="feePercentage" type="integer" required=true %}
Value in % `80.5`
{% endapi-method-parameter %}

{% api-method-parameter name="feeFlat" type="number" required=false %}
Enter the amount to give slip account
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```markup

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% tabs %}
{% tab title="Request" %}
200: OK

```markup
<form>
  <script src="https://autocredit.cc/js/autocredit.js"></script>
  <button type="button" onclick="payWithPayant()"> Pay </button> 
</form>

<script>
    function payWithAutocredit() {
        var handler = PayDirect.invoice({
        "key": "PUB_DEMO_098794FC56C7D49",
        "orderid" : "2019LUX8008d6258e3488",
        "revhead_id": "REV_50858708281",
        "customer": {
                "first_name": "ADEJUMO",
                "last_name": "AYOMIDE",
                "email": "ayomide@gmail.com",
                "phone": "09009090717"
            },

        "fee_bearer": "merchant",
        "items": [
            {
            "item": "Miscellaneous payments",
            "description": " Miscellaneous payments | ADEJUMO MALEEK AYOMIDE | 100Level",
            "unit_cost": "20000",
            "quantity": "1"
            }],
        "split_details":[ {
                "subAccountCode": "REV_50858709090",
                "feePercentage": 90
            },{
                "subAccountCode": "REV_72849988998",
                "feePercentage": 10
            }
        ],
        callback: function(response) {
            window.location.replace("response.php?tranxid="+response.reference_code);

        },
        onClose: function() {
            console.log('Window Closed.');
            window.history.back();
        }
        });

        handler.openIframe();
    }
</script>
```
{% endtab %}

{% tab title="Response" %}

{% endtab %}
{% endtabs %}

