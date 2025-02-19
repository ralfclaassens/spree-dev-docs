# Authenticating requests

Platform API is meant to be used by external applications to perform operations within Spree. Because of that, it uses a different authentication schema than the Storefront API.&#x20;



### Creating an application inside Spree

To generate a valid token for the Platform API, you'll first need to create an application inside Spree.

1.  Go to Spree's admin panel and open `Apps` -> `oAuth Applications` in the menu&#x20;

    <figure><img src="../../.gitbook/assets/Platform API 1.png" alt=""><figcaption></figcaption></figure>
2.  Click on `New oAuth Application`

    <figure><img src="../../.gitbook/assets/Platform API 2.png" alt=""><figcaption></figcaption></figure>
3.  Give you application a name and click `Create`

    <figure><img src="../../.gitbook/assets/Platform API 3.png" alt=""><figcaption></figcaption></figure>
4.  Save your Client ID and Secret - you'll later use it to generate a OAuth token to access the platform API

    <figure><img src="../../.gitbook/assets/Platform API 4.png" alt=""><figcaption></figcaption></figure>

### Generating OAuth token

Once the application is configured inside Spree, you can use its credentials to generate an OAuth token that will give you access to the APIs.&#x20;

To obtain the token, send the following `POST` request to `/spree_oauth/token`

```
{
  "grant_type": "client_credentials",
  "client_id": "xxx",
  "client_secret": "xxx",
  "scope": "admin"
}
```

In the response, you'll receive a token to pass in `Authorization: Bearer {token}` header when making requests to the Platform API.

