---
title: Authentication
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
All API requests require API credentials, which you can find in your account SETTINGS page. Scroll down to API Settings to find your API key and set your API secret.

Your API Secret can be anything you like. Think of the API Secret as a password field where you will need to enter an alphanumeric of your choice. Once you enter your chosen API Secret, click on the UPDATE PROFILE button to save your settings

<Image align="center" src="https://files.readme.io/30c1420-FyMeLX68fF7Q_fjtbi1.png" />

## API Authentication

Our APIs support different authentication methods.

### api.transmitsms.com

The api.transmitsms.com endpoints use **Basic Authentication** for authentication.

* Basic Authentication is a simple authentication scheme built into the HTTP protocol.
* The client sends the API Key and API Secret encoded as a Base64 string in the Authorization header.

Example

```curl Curl
curl --location 'https://api.transmitsms.com/send-sms.json' \
--header 'Authorization: Basic XXXXXXXXXXXXXXXXXXXXXX' \
--form 'message="Hello, World"' \
--form 'to="6140000000"' \
--form 'from="6140000000"'
```

### api.transmitmessage.com

Transmit Message endpoints use [API Key Authentication](https://en.wikipedia.org/wiki/API_key).

* API Key Authentication involves sending a unique key in the request header to authenticate the client.
* The API key acts as a token that allows access to the API, identifying the client making the request.

Example

```curl curl
curl --request POST \
     --url https://api.transmitmessage.com/v2/sms \
     --header 'Content-Type: application/json' \
     --header 'x-api-key: XXXXXXXXXXXXXXXX' \
     --data '
{
  "message": "Hello, world!",
  "sender": "6140000000",
  "recipient": "6140000000"
}
'
```

## API Key related error response

If an API Key is missing, malformed, or invalid, you will receive a 401 Unauthorised response code and the following JSON response

```json json
{  
    "error": {  
        "code": "AUTH_FAILED",  
        "description": "The auth data you have provided is invalid."  
    }  
}
```
