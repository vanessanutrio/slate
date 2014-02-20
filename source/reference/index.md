---
title: API Reference

language_tabs:
  - shell: curl

toc_footers:
 - <a href='/'>Getting Started</a>
 - <a href='/reference/'>API Reference</a>
 - <a href='/tutorials/'>Tutorials</a>
 - <a href='http://www.nutrio.com' target='_blank'>Nutrio</a>
 - <a href='http://github.com/tripit/slate' target='_blank'>Documentation Powered by Slate</a>
---


#User



##User Authentication

>Create

```shell
curl \
--insecure \
--verbose \
--user "f1bcb4e1-967b-4ecd-8ffd-df62a5a7eb75:" \
--header "Content-Type: application/json" \
--data '{"external_user_id":"xyzzy","email":"ted.davis@nutrio.com"}' \
"https://api.nutrio.com/api/v2/users"
```

>Read

```shell
curl \
--insecure \
--verbose \
--user "f1bcb4e1-967b-4ecd-8ffd-df62a5a7eb75:" \
--header "Content-Type: application/json" \
"https://api.nutrio.com/api/v2/users/447293.json"
```


>Update

```shell
curl \
--insecure \
--verbose \
--user "f1bcb4e1-967b-4ecd-8ffd-df62a5a7eb75:" \
--header "Content-Type: application/json" \
--request "PUT" \
--data '{"external_user_id":"xyzzy","email":"ted.davis@nutrio.com"}' \
"https://api.nutrio.com/api/v2/users/447293.json"
```

>Search

```shell
curl \
--insecure \
--verbose \
--user "f1bcb4e1-967b-4ecd-8ffd-df62a5a7eb75:" \
--header "Content-Type: application/json" \
--request "GET" \
--data '{"external_user_id":"xyzzy","email":"ted.davis@nutrio.com"}' \
"https://api.nutrio.com/api/v2/users.json"
```



In order to access the Nutrio API as an end user, the user needs to have an API key. This key is obtained by registering the user with Nutrio using your Cobrand API key. This is generally the only time you use your Cobrand API key for access; all other forms of access to the Nutrio API should be done through a user API key.

Unless a token expiration strategy is requested, the Cobrand is welcome to cache the user's API key on their end so they don't need to re-request it every time. When accessing the Nutrio API, the user API key is passed as the "password" part of an HTTP Authentication request. The "username" part is reserved for the Cobrand API key and can be blank."

For user registration and creation, pass your internal unique never-changing identifier as the "external_user_id" parameter. From that point forward, you may use that same ID to access the user record for update and retrieval.

### Resource

`https://api.nutrio.com/api/v2/users`

### Request Parameters

Parameter |  Description
--------- |  -----------
id | How Nutrio uniquely identifies this user
external_user_id | How you uniquely identify this user
email | Optional

### Response Parameters

Parameter |  Description
--------- |  -----------
id | How Nutrio uniquely identifies this user
external_user_id | How you uniquely identify this user
email | Optional
api_key | User API key
errors | Errors



<aside class="notice">The user API key is passed as the "password" part of an HTTP Authentication request. The "username" part is reserved for the Cobrand API key and can be blank.</aside>

##User Profile


> Update

```shell
curl \
--insecure \
--verbose \
--user ":01e4db4b-f6f3-43f5-91d1-e3818fc9d3e9" \
--header "Content-Type: application/json" \
--request "PUT" \
--data '{"name":{"first":"Thomas","last":"Davis"},"current":{"weight":{"amount":184,"unit":"pounds"},"height":{"amount":72,"unit":"inches"},"gender":"f","birth_date":19740705},"goal":{"weight":{"amount":null,"unit":"pounds"},"start_date":null,"end_date":null},"email":"ted.davis@nutrio.com","integrate_plan_and_log":null}' \
"https://api.nutrio.com/api/v2/user_profiles/447293.json"
```



Set general user information and retrieve with calculated values for the current date (e.g. calorie bank balance).




##User Meal Ratings
##User Meal Favorites
##User Weight Loss Goal Cycles
##User Weights (Batch)

#Calculators
##BMI Calculator
##Calorie Burn Calculator
##Daily Calorie Target Calculator

#Weight Log
##Weight Tracker Entries

#Activity Log
##Activity Log Entries
##Activity Search Autocomplete

#Food Log
##Food Log Entries
##Food Log Nutrients for Day
##Food Log Recipe Search Autocomplete
##Food Log Natural Language Parsing

#Meals, Recipes, Foods
##Foods (Ingredients)
##Recipe Search by Keywords
##Recipe Search by Categories
##Food Analyzer
##Meal ID Translator

