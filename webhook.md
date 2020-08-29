# Webhook

A webhook allows your application to receive notifications when updates are made on your account on Autocredit. Webhook update notifications are sent as POST requests to a callback URL that you supply.

## **Setting Up a Webhook**

The [Autocredit Dashboard Settings](https://demo.autocredit.ng/) to setup a webhook subscription. You will be required to specify:

* Webhook URL - a URL to your endpoint that can process both verification and notification requests.
* Verify Token - a string you supply which we will include whenever we send a verification request.

## **Webhook URL**

You need to setup a webhook endpoint before you set up a subscription to it on Autocredit. Your endpoint must be [HTTPS](https://en.wikipedia.org/wiki/HTTPS) and must be able to receive both GET and POST requests.

If you need help setting up HTTPs on your endpoint, check out the [Getting Started Guide](https://letsencrypt.org/getting-started/) from Let's Encrypt

## **Verification Request**

We'll send a GET request while setting up your webhook. The request will include the following parameters appended to the end of your webhook URL.

* `type=subscribe`
* `challenge` - A random string
* `verify_token` - a string that you supply to setup the webhook

When your endpoint receives the verification request, it must:

* Verify that the `verify_token` corresponds to the token your supplied when setting up your webhook.
* Respond with the `challenge` value.

## **Notification Request**

Whenever their are changes on your account, we will send a POST request to your webhook endpoint. The request will have a JSON payload as follows:

* `type` - Notification type
* `data` - An array containing the notification data

## **Webhook Server Example**

We have created an example Node.js server for you to get started quickly.

{% tabs %}
{% tab title="JavaScript" %}
* [node-webhook-example](https://github.com/AutoCredit/node-webhook-example) by YoungMaster

```javascript
{
  "name": "node-webhook-example",
  "version": "1.0.0",
  "description": "Webhook Example Node Server for Autocredit.ng",
  "main": "webhook.js",
  "scripts": {
    "start": "node webhook.js"
  },
  "author": "Autocredit Support <hello@autocredit.ng>",
  "license": "ISC",
  "dependencies": {
    "body-parser": "^1.17.2",
    "express": "^4.15.3"
  }
}
```

```javascript
/**
 * Webhook Server
 *
 * @author Autocredit Support <hello@autocredit.ng>
 * @version 1.0.0
 */

const express       =   require('express');
const bodyParser    =   require('body-parser');
let   app         =     express();

app.use(bodyParser.json());

app.get('/webhook', (req, res) => {
    if(req.query.type === 'subscribe' && req.query.verify_token === 'VerifyToken') {
        console.log("Token validation successful.");
        res.status(200).send(req.query.challenge);
    }else {
        console.error("Token validation failed. Make sure the validation tokens match.");
        res.sendStatus(403);  
    }
});

app.post('/webhook', (req, res) => {
    var data = req.body;

    console.log("Data received: ", data);

    //Lastly send back a 200
    res.sendStatus(200);
})

app.listen(process.env.PORT || 8005);
```
{% endtab %}

{% tab title="PHP" %}
```php
<?php


$curl = curl_init();
$reference = isset($_GET['reference']) ? $_GET['reference'] : '';
if(!$reference){
die('No reference supplied');
}

curl_setopt_array($curl, array(
CURLOPT_URL => "https://autocredit.ng/payments" . rawurlencode($reference),
CURLOPT_RETURNTRANSFER => true,
CURLOPT_HTTPHEADER => [
    "accept: application/json",
    "authorization: Bearer SECRET_KEY",
    "cache-control: no-cache"
],
));

$response = curl_exec($curl);
$err = curl_error($curl);

if($err){
    // there was an error contacting the Paystack API
die('Curl returned error: ' . $err);
}

$tranx = json_decode($response);

if(!$tranx->status){
// there was an error from the API
die('API returned error: ' . $tranx->message);
}

if('success' == $tranx->data->status){
// transaction was successful...
// please check other things like whether you already gave value for this ref
// if the email matches the customer who owns the product etc
// Give value
}
```
{% endtab %}
{% endtabs %}

