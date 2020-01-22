---
description: GET
---

# get-banks

{% api-method method="get" host="https://api.autocredit.ng/banks" path="" %}
{% api-method-summary %}
Get Banks
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=false %}
Autocredit secret key prefixed with "Bearer "
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
  "status": "success",
  "data": {
      "214": "FIRST CITY MONUMENT BANK PLC",
      "215": "UNITY BANK PLC",
      .....,
      .....,
      .....,
      "035": "WEMA BANK PLC",
      "057": "ZENITH BANK PLC"
    }
  }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## **Request**

```bash
curl https://api.autocredit.ng/banks \
-H "Content-Type: application/json" \
-H "Authorization: Bearer SECRET_KEY" \
-X GET
```

## **Response**

```javascript
{
  "status": "success",
  "data": {
      "214": "FIRST CITY MONUMENT BANK PLC",
      "215": "UNITY BANK PLC",
      .....,
      .....,
      .....,
      "035": "WEMA BANK PLC",
      "057": "ZENITH BANK PLC"
    }
  }
}
```

