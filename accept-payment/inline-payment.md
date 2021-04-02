---
description: >-
  The Autocredit Inline JS allows you to accept payments on almost every device.
  It is the easiest, most convenient , and secure way of invoicing and accepting
  payments from your customers.
---

# Inline Payment

{% api-method method="options" host="" path="" %}
{% api-method-summary %}
Inline Payment
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
{% api-method-parameter name="key " type="string" required=true %}
Invoice refrence code if already exists
{% endapi-method-parameter %}

{% api-method-parameter name="first\_name" type="string" required=true %}
Client's first name
{% endapi-method-parameter %}

{% api-method-parameter name="last\_name" type="string" required=true %}
Client's last name
{% endapi-method-parameter %}

{% api-method-parameter name="email" type="string" required=true %}
Clien't email address
{% endapi-method-parameter %}

{% api-method-parameter name="phone" type="string" required=true %}
Client's phone number
{% endapi-method-parameter %}

{% api-method-parameter name="settlement\_bank" type="string" required=false %}
Clien't settlement bank
{% endapi-method-parameter %}

{% api-method-parameter name="account\_number" type="string" required=false %}
Client's account number
{% endapi-method-parameter %}

{% api-method-parameter name="fee\_bearer " type="string" required=true %}
Invoice fee brearer, `account` or `client`
{% endapi-method-parameter %}

{% api-method-parameter name="items" type="array" required=true %}
Invoice items
{% endapi-method-parameter %}

{% api-method-parameter name="item" type="string" required=true %}
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
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
   "status":"success",
   "message":"Transaction Successfully",
   "orderid":"20150103259d040315bf8",
   "data":{
      "amount":2000,
      "orderid":"20150103259d040315bf8",
      "transid":"ACXXPMATOEUACX",
      "date_paid":"2020-11-19 23:17:26",
      "status":"approved",
      "channel":"CARD",
      "items":"[{\"item\":\"Alumni Fee\",\"description\":\"20150103259 | 2018\/2019 | Alumni Fee | OKON CHRISTOPHER EMMANUEL | 400Level\",\"unit_cost\":\"2000\",\"quantity\":\"1\"}]"
   }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Sample Code

```markup
<form>
  <script src="https://autocredit.cc/js/autocredit.js"></script>
  <button type="button" onclick="payWithAutocredit()"> Pay </button> 
</form>

<script>
  function payWithAutocredit() {
    var handler = Autocredit.invoice({
      "key": "e47aa44e4a320ae2a2b6b8804a4d2fa1b74437ab",
      "orderid" : "8747874",
      "revhead_id": "REV_508587108281",
      "customer": {
            "first_name": "Aremu",
            "last_name": "Idris",
            "email": "aremu@autocredit.ng",
            "phone": "+2348078422238"
        },
      "fee_bearer": "client",
      "items": [
        {
          "item": "Registeration Fee",
          "description": "newsite.com",
          "unit_cost": "2500.00",
          "quantity": "1"
        }
      ],
      callback: function(response) {
        console.log(response);
      },
      onClose: function() {
        console.log('Window Closed.');
      }
    });

    handler.openIframe();
  }
</script>
```

{% hint style="warning" %}
**Heads up!**

Please ensure that you use the right API endpoint for demo `https://.autocredit.cc and`  `https://live.autocredit.cc` for LIVE on the script tag.
{% endhint %}

