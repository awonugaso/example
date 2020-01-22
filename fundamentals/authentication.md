# authentication

Payant API uses API keys to authenticate requests. You can view and manage your API keys from the [Payant Dashboard](https://dashboard.demo.payant.ng/settings/api).

All requests to the Payant API must be authenticated by including your `private key` in request headers.

Your authorization header should be like:`Authorization: Bearer cd525b1d647942a21c51d03f8c07e2fd43b4e955ec13a8c54c8a5f2d`

All API requests must be made over [HTTPS](http://en.wikipedia.org/wiki/HTTP_Secure). Calls made over plain HTTP will fail. API requests without authentication will also fail.

{% hint style="info" %}
**Heads up!**

Your API keys carry many privileges, so be sure to keep them secure! Do not share your Private API keys in publicly accessible areas such as GitHub, client-side code, and so forth.
{% endhint %}

