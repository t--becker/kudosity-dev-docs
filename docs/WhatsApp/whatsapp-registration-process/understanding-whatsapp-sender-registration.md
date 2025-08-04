---
title: Understanding WhatsApp Sender Registration
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
Registering a WhatsApp sender is the first step to start using WhatsApp for business communication on the Kudosity platform. This process involves setting up your WhatsApp Business Account (WABA) through Meta's systems.

> 📘 Meta Registration
>
> The WhatsApp sender registration is managed by Meta. However, if you encounter any issues, contact our [Kudosity Support](https://kudosity.com/contact-us).

## Kudosity + WhatsApp Cloud API Integration

Kudosity offers a WhatsApp Cloud Business solution integrated with Meta's Cloud API.

### Message Flow

1. Your business initiates communication by **sending a message** to the Kudosity platform.
2. Kudosity **processes the message**: verifies details, executes billing and routing, and forwards the message to the WhatsApp platform through Meta's **Cloud API**.
3. WhatsApp delivers the message to the end user's device via the WhatsApp network.

<Image align="center" width="400px" src="https://files.readme.io/6f25a3b876d9a667026b7c3f5854b9a185be586bad2a5b48a4ea6ff47488d8f5-ChatGPT_Image_Jun_19_2025_04_06_41_PM.png" />

<br />

***

## Account Types

A **WhatsApp Business Account (WABA)** is required to use the WhatsApp Business Platform for customer communication. It allows businesses to manage senders, message templates, and messaging capabilities. Each WABA can contain multiple phone numbers and supports different account types.

To create and manage a WABA, businesses must have a [Meta business portfolio](https://www.facebook.com/business/tools/business-manager). A Meta business portfolio is a central account used to manage business assets across Meta platforms, including Facebook, Instagram, and WhatsApp. Meta also uses your business portfolio to verify your business through business verification.

### Meta Business Portfolio & WhatsApp Business Account

<Table>
  <thead>
    <tr>
      <th>
        Meta Business Portfolio
      </th>

      <th>
        WhatsApp Business Account
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        • Manage your business operations and customer communication within Meta's ecosystem
        • Centralized control over assets like pages, ad accounts, and user permissions
      </td>

      <td>
        • Prerequisite for accessing the WhatsApp Business Platform\
        • Enables direct communication with customers using the WhatsApp platform\
        • Linked to Meta business portfolio
      </td>
    </tr>
  </tbody>
</Table>

Each WABA can contain multiple phone numbers and support different account types:

* **Verified business account**: A business that has successfully completed the business verification process.
* **Official Business Account (OBA)**: A verified account with a blue checkmark, signifying a notable brand.

***

## Sender Specifications

A WhatsApp sender refers to a **phone number** that serves as your identifier and an associated **display name** to represent your brand in customer interactions. To ensure compliance with WhatsApp policies, both must meet specific criteria before registration.

### Phone Number

You need a valid phone number to register a WhatsApp sender. This number serves as your business identifier and must meet the following criteria:

* **Format**: It must be in [E.164 international format](https://www.kudosity.com/glossary/e164) and be reachable internationally.
* **Verification**: The number must be active during the registration process, meaning it must be able to receive a [two-factor authentication (2FA)](https://www.kudosity.com/blog/what-is-2fa-everything-you-need-to-know) code through SMS or voice call.
* **Restrictions**:
  * [Short codes](https://www.kudosity.com/glossary/short-code) and toll-free numbers are not supported.
  * Numbers under an [IVR (Interactive Voice Response)](https://www.kudosity.com/glossary/interactive-voice-response) system cannot be registered using the standard registration process. Contact your Kudosity account manager or [Support](https://www.kudosity.com/contact/) for assistance if your phone number is under IVR.
  * If you wish to use a phone number already registered with any version of WhatsApp, you must first delete the associated account to enable its use for business purposes.
