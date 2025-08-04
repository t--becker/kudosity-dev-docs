---
title: Introduction to RCS
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: >-
    RCS Business Messaging (RBM) is an advanced evolution of SMS, offering
    interactive, branded communication through default messaging apps on Android
    and select iPhones, with features like verified business profiles, smart SMS
    fallback, and a spam-resistant channel, all accessible via a
    developer-friendly API.
  robots: index
next:
  description: ''
---
[RCS Business Messaging ](https://developers.google.com/business-communications/rcs-business-messaging/guides/get-started/how-it-works)(RBM) is the modern evolution of SMS — a richer, interactive channel built into the default messaging apps on Android, and now increasingly available on iPhones in select markets.

With support for branded, app-like experiences and full conversational interactivity, RCS empowers businesses to connect with customers in a far more engaging way — no app installs, no redirects, no clunky mobile web.

Our RCS API is intended for the developers  who plan to integrate their systems with the Kudosity Messaging API to send RCS messages to their users and/or to build an RCS Conversation bot.

> ⚙️ This documentation is for developers integrating with our RCS API. At this time, we’re API-first — no UI required (or available) yet

## Why It Matters — For You and Your Customers

If you're a developer building for internal stakeholders or client businesses, RCS unlocks powerful capabilities:

- **Verified by Google** – Messages come from your official, branded business profile, so customers know it’s really you.
- **Smart delivery fallback** – If RCS isn’t supported, we can automatically fall back and send via SMS — ensuring your messages get through.
- **Spam-free by design** – RCS traffic is tightly controlled and verified, avoiding the spam filters that increasingly block legitimate SMS.
- **Boost conversions** - with media-rich, action-oriented messages, customers are seeing high conversion rates. 2-3x higher than SMS!!
- **Simple API Integration**  - Clean, RESTful API to send and receive responses.

## Key RCS Value Propositions

[block:parameters]
{
  "data": {
    "h-0": "✅ Verified Business Presence on Google",
    "h-1": "🔁 Smart Routing with SMS Fallback",
    "0-0": "Messages come from your official brand profile, verified by Google. No random numbers. No confusion.  \nCustomers can see your logo, brand name, colors, and trust they’re hearing from you — not a scammer.  \n![](https://files.readme.io/a66ce8f4895672803c4f23f0ef8a0a4447c6aed5136daa701c68e2827806b7ef-Screenshot_2025-06-04_at_10.22.40_am.png)",
    "0-1": "If an RCS message can’t be delivered (e.g. unsupported device or network), we automatically route it via SMS — no extra code, no manual failovers.![](https://files.readme.io/2455ad3bbdb494c8be19bd20bd3ee9fd257ccb78828fde545b23851fda3ff830-failover.png)"
  },
  "cols": 2,
  "rows": 1,
  "align": [
    "left",
    "left"
  ]
}
[/block]


[block:parameters]
{
  "data": {
    "h-0": ":lock: Tightly governed, Trusted Channel-low SPAM",
    "h-1": "Built for Developers",
    "0-0": "RCS offers a spam-resistant channel — only verified businesses can send messages, and traffic is tightly governed by carrier and platform rules.  \nIn some countries, aggressive SMS spam filtering is catching even valid messages. RCS changes that. Your messages will get through.![](https://files.readme.io/0077389c620d4bb2e3eb277f02c0bb4d52ee32c5cde70c936f3b4aa1f7f9950f-verified-messages.png)",
    "0-1": "Our RCS platform is API-first by design, so you can integrate messaging into your product or workflow without waiting for a frontend.  \nThe structure, logic, and endpoints feel familiar — making it simple to adopt, extend, or switch between channels.![](https://files.readme.io/cbb0464109ed157a306e278fa472db0c47f44d9e2c10063f9cf8338c6421d816-ChatGPT_Image_Jun_6_2025_11_01_02_AM.png)"
  },
  "cols": 2,
  "rows": 1,
  "align": [
    "left",
    "left"
  ]
}
[/block]