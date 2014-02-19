---
title: Getting Started

language_tabs:
  - curl

toc_footers:
 - <a href='/'>Getting Started</a>
 - <a href='/tutorials/'>Tutorials</a>
 - <a href='/reference/'>API Reference</a>
 - <a href='http://www.nutrio.com'>Nutrio</a>
 - <a href='http://github.com/tripit/slate'>Documentation Powered by Slate</a>
---

# Introduction

Nutrio Web Services offers an HTTP API leveraging the standards of REST, CRUD, and JSON.

The following documentation implementation examples use the Backbone.js library.

This API documentation page was created with [Slate](http://github.com/tripit/slate).

# Getting Started

Brief summary on how to get started goes here.


# Authentication

## Cobrand Authentication


In order to access the Nutrio API and act on the behalf of a Cobrand, you need to use the access key provided by Nutrio. This key should be kept secret by the Cobrand. This key is only for access between the Cobrand's servers and the Nutrio API. Never embed this key into a page delivered to a user's browser. Never pass this key over a non-SSL/HTTPS connection. The Cobrand API key is to be passed as the "username" part of an HTTP Authentication request. The "password" part is used for the user API key when appropriate, but can be left blank."

## User Hand-Off

Hand off a user session from the client web site to the Nutrio web site.

### HTTP Request

`POST https://api.nutrio.com/api/v1/user_handoff_tokens`

### Query Parameters

Parameter |  Description
--------- |  -----------
external_user_id | External User ID

```curl
curl \
--insecure \
--verbose \
--user "f1bcb4e1-967b-4ecd-8ffd-df62a5a7eb75:" \
--header "Content-Type: application/json" \
--data '{"external_user_id":"xyzzy"}' \
"https://api.nutrio.com/api/v1/user_handoff_tokens"
```

<aside class="warning">Your Cobrand API key is to be passed as the "username" part of an HTTP Authentication request.</aside>

> Request Sample

```json
{
    "external_user_id": "xyzzy"
}
```


> Response Sample

```json
{
    "external_user_id": "xyzzy",
    "guid": "22f396c373fd4161837f0143b32dace0"
}
```