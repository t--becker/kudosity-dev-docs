---
title: Kudosity SMS and Webhook Essentials
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: >-
    The document provides a tutorial on using Glitch.com to integrate with
    Kudosity, focusing on sending SMS through the TransmitSMS API and setting up
    a webhook to receive and display SMS messages, emphasizing that the provided
    code is for demonstration purposes and not production-ready.
  robots: index
next:
  description: ''
---
We use [Glitch.com](https://glitch.com/@kudosity) to show how to integrate with Kudosity. We believe that working code beats videos, long-winded tutorials, complicated diagrams, etc, every day of the week. Please Remix, Share, Chat, Post, etc, about our code and help us spread the love and improve our services. Keep in mind, this is just sharable sample code and not production ready.

This tutorial covers

* Sending an SMS through api.transmitsms.com
* Setting up a webhook in Kudosity
* Receiving the SMS webhook and displaying it on the page

## Setup

1. **Sign up**: Register for a free Kudosity developer account: [Kudosity Developer Account](https://kudosity.com/developer-trial?utm_source=website\&utm_medium=banner\&utm_campaign=developer-portal) 
2. **Remix Project**: Remix the Glitch project [sms-kudosity-webhook-example](https://glitch.com/~sms-kudosity-webhook-example).
3. **Configure Webhooks**: Set the **DLR Callback URL** in your Kudosity account to: `yourproject.glitch.me/message`

<Image align="center" src="https://files.readme.io/4d6c96205297a6f9d8abc3c7b2ac0b8780224666c42bf40916c1bf0457280417-Screenshot_2024-11-07_at_5.18.59_pm.png" />

4. Run the project:

   1. Fill in the form details and click send
   2. TO: Only numbers in your “**My Test List**” can be used. Read more about [Kudosity Trial Limitations](https://kudosity.transmitsms.com/u/trial-limitations).
   3. API\_KEY + API Secret: [https://kudosity.transmitsms.com/u/settings/api](https://kudosity.transmitsms.com/u/settings/api)

### Workflow Overview

Once you send the SMS:

1. The project sends and SMS through `api.transmitsms.com`
2. The SMS is delivered to the recipient.
3. The telco provider sends a delivery status update to Kudosity.
4. Kudosity forwards the status as a webhook to your project:`yourproject.glitch.me/message`
5. The project displays the webhook on the page.

<Image align="center" className="border" border={true} src="https://files.readme.io/6fe483efd6d0c8f31bbf36f29638177b71ae668a8a24da2d20f37515b61690bc-Screenshot_2024-11-12_at_10.46.18_am.png" />

<br />

## Key Points About the Code

Below are salient points about the code. Keep in mind this is just sample code for illustration purposes. How you implement this on your production environment may differ.

### Sending SMS

**Endpoint**: `/sendmessage`\
This POST route processes form data and sends a request to the TransmitSMS API.

* **Authorization**: Credentials (API\_KEY and SECRET) are base64-encoded for Basic Authentication.
* **Request Preparation**: Form data is appended using `URLSearchParams`.
* **Request Method**: The `fetch` method sends a POST request to the api.

```Text JavaScript
app.post('/sendmessage', async (req, res) => {
    const to = req.body.to;
    const apiKey = req.body.api_key;
    const secret = req.body.secret;

    const credentials = `${apiKey}:${secret}`;
    const base64Credentials = Buffer.from(credentials, 'ascii').toString('base64');

    const url = 'https://api.transmitsms.com/send-sms.json';
    const data = new URLSearchParams();
    data.append('message', 'Hello from Kudosity');
    data.append('to', to);

    const fetch = (await import('node-fetch')).default;

    try {
        const response = await fetch(url, {
            method: 'POST',
            headers: {
                'Authorization': `Basic ${base64Credentials}`,
                'Content-Type': 'application/x-www-form-urlencoded'
            },
            body: data
        });

        const result = await response.json();
        console.log('SMS API response:', result);

    } catch (error) {
        console.error('Error sending SMS:', error);
        res.status(500).json({ error: 'Failed to send SMS' });
    }

    res.sendStatus(204);
});

```

### Webhook Integration

**Endpoint:** `/message`\
The webhook endpoint receives GET requests from TransmitSMS. Key parameters such as message\_id, mobile, datetime, status, user\_id, and rate are extracted and stored in a global message object.

```Text JavaScript
app.get("/message", function (request, response) {
    message['message_id'] = request.query.message_id;
    message['mobile'] = request.query.mobile;
    message['datetime'] = request.query.datetime;
    message['status'] = request.query.status;
    message['user_id'] = request.query.user_id;
    message['rate'] = request.query.rate;

    response.sendStatus(200);
});
```

Integration Notes\
Webhook Registration: Configure the callback URL (/message) in your TransmitSMS API Settings.\
Security: Add signature verification to validate the webhook's authenticity. Learn more: [Validating Webhook Signatures from Kudosity](validating-webhook-signatures-from-kudosity).
