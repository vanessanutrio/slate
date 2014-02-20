---
title: Getting Started

language_tabs:
  - shell: curl

toc_footers:
 - <a href='/'>Getting Started</a>
 - <a href='/reference/'>API Reference</a>
 - <a href='/tutorials/'>Tutorials</a>
 - <a href='http://www.nutrio.com' target='_blank'>Nutrio</a>
 - <a href='http://github.com/tripit/slate' target='_blank'>Documentation Powered by Slate</a>
---

# Introduction

Nutrio Web Services offers an HTTP API leveraging the standards of REST, CRUD, and JSON.

The following documentation implementation examples use the Backbone.js library.

This API documentation page was created with [Slate](http://github.com/tripit/slate).

# Getting Started

Nutrio’s Web Service API provides powerful tools to help build many health and wellness oriented web or mobile applications for consumers. By using Nutrio’s API you can avoid a number of development obstacles associated with building the nutrition, fitness and wellness tools of a web application yourself, allowing you to concentrate on their design and management.

##The Basics
Nutrio provides secure web services for many of its popular features via REST standards over SSL. With Nutrio’s Web Service, you can have access to high-quality nutrition, fitness and wellness tools and rely on regular database maintenance and updating by our experts.


# Authentication

## Cobrand Authentication


In order to access the Nutrio API and act on the behalf of a Cobrand, you need to use the access key provided by Nutrio. This key should be kept secret by the Cobrand. This key is only for access between the Cobrand's servers and the Nutrio API.  The Cobrand API key is to be passed as the "username" part of an HTTP Authentication request. The "password" part is used for the user API key when appropriate, but can be left blank."

<aside class="warning">Never embed this key into a page delivered to a user's browser.</aside>
<aside class="warning">Never pass this key over a non-SSL/HTTPS connection. </aside>



## User Hand-Off

```shell
curl \
--insecure \
--verbose \
--user "f1bcb4e1-967b-4ecd-8ffd-df62a5a7eb75:" \
--header "Content-Type: application/json" \
--data '{"external_user_id":"xyzzy"}' \
"https://api.nutrio.com/api/v1/user_handoff_tokens"
```


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

Hand off a user session from the client web site to the Nutrio web site.

### HTTP Request

`POST https://api.nutrio.com/api/v1/user_handoff_tokens`

### Query Parameters

Parameter |  Description
--------- |  -----------
external_user_id | External User ID


<aside class="notice">Your Cobrand API key is to be passed as the "username" part of an HTTP Authentication request.</aside>

