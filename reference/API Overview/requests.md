---
title: Using JSON and XML
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
The Transmit SMS API (**api.transmitsms.com**) supports both JSON and XML. But the Transmit Message API (**api.transmitmessage.com**) only supports JSON.

For **api.transmitsms.com**, you can choose which response you want by selecting the appropriate suffix (.json OR .xml) in your request. You can find both JSON and XML in code examples for each endpoint in the api.transmitsms.com API documentation.

**XML Example **

Request

```curl
curl --location 'https://api.transmitsms.com/get-sms.xml' \
--header 'Authorization: Basic XXXXXXXXXX' \
--form 'message_id=XXXXXXXX'
```

Response

```xml
<?xml version="1.0"?>
<response>
    <message_id>XXXXXXXXX</message_id>
    <send_at>2020-06-18 02:42:06</send_at>
    <recipients>1</recipients>
    <cost>0.087</cost>
    <sms>1</sms>
    <list>
        <id>4070887</id>
        <name>My Test List</name>
    </list>
    <delivery_stats>
        <delivered>0</delivered>
        <pending>0</pending>
        <bounced>0</bounced>
        <responses>0</responses>
        <optouts>0</optouts>
    </delivery_stats>
    <error>
        <code>SUCCESS</code>
        <description>OK</description>
        <header>200</header>
    </error>
</response>
```