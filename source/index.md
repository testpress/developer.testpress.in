---
title: API Reference

language_tabs:
  - shell
  - ruby
  - python
  - csharp

includes:
  - errors

search: true
---

# Introduction

Welcome to Testpress API. You can use our API to access Testpress API endpoints, which can get information on various resources in our database.

You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

# Authentication

> To authorize, use this code:

```csharp
var client = new RestClient("https://demo.testpress.in/api/v2.1/auth-token/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\n    \"username\": \"admin\",\n    \"password\": \"demo\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```ruby
re 'uri'
require 'net/http'

url = URI("https://demo.testpress.in/api/v2.1/auth-token/")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"username\": \"testpress\",\n    \"password\": \"demo\"\n}"

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://demo.testpress.in/api/v2.1/auth-token/"

payload = "{\n    \"username\": \"testpress\",\n    \"password\": \"demo\"\n}"
headers = {
    'content-type': "application/json",
    'cache-control': "no-cache",
    }

response = requests.request("POST", url, data=payload, headers=headers)

print(response.text)
```

```shell
# With shell, you can just pass the user credentials to get the auth token
curl --request POST \
  --url https://demo.testpress.in/api/v2.1/auth-token/ \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json' \
  --data '{\n    "username": "admin",\n    "password": "demo"\n}'
```

> Make sure to replace `testpress` and `demo` with your credentials.
> The above command returns JSON structured like this:

```json
{"token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw"}
```

This endpoint provides an authentication token to get access to private resources in Testpress.

### HTTP Request

`POST http://demo.testpress.in/api/v2.1/auth-token/`

<aside class="info">
Replace <code>demo</code> with your institute subdomain hereafter everywhere.
</aside>


### Response
The response will return an token which should be prefixed with <code>JWT</code> and included in all API requests to the server in a header that looks like the following:

`Authorization: JWT auth-token-string`

<aside class="info">
You must replace <code>auth-token-string</code> with the token you got from the response.
</aside>

# Users
Users API gives you access to get basic information about other users present in the institute.

<aside class="info">This endpoint protects the privacy of users. It is <strong>NOT</strong> possible to extract personal details of all the users from this endpoint. An admin however can extract the personal details using the Admin APIs.</aside>

## Get current authenticated user

```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.1/me/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw'
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://demo.testpress.in/api/v2.1/me/"

headers = {
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw",
    'cache-control': "no-cache"
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```shell
curl --request GET \
  --url http://demo.testpress.in/api/v2.1/me/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw' \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("http://demo.testpress.in/api/v2.1/me/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "id": 17,
  "batches": [
    "EEE",
    "ECE",
    "Unique UPSC Batch",
    "POZITIVE ONLINE TEST SERIES",
    "OHC 2013",
    "st std A",
    "IBPS Morning Batch",
    "UPSC Morning  Batch",
    "NEET Morning Batch",
    "IBPS Online Batch",
    "UPSC Evening Batch"
  ],
  "url": "http://demo.testpress.in/api/v2.1/users/17/",
  "username": "testpress",
  "display_name": "Divya",
  "first_name": "Divya",
  "last_name": "",
  "email": "testpress.in@gmail.com",
  "photo": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/9b69ab73fc924813871b2ef1e2ef00fa.jpeg",
  "large_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/493054067d1d4173a22d96b824d7f0c6.jpeg",
  "medium_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/8d96dab06a82487ab3149b771fe5d479.jpeg",
  "small_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/4023a394cd36472fa24db76e493192ce.jpeg",
  "x_small_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/796fa9a9727a42e4a7faa015b0388af3.jpeg",
  "mini_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/5f9215132af54acc8e72aed968582763.jpeg",
  "birth_date": "1994-08-27",
  "gender": "Female",
  "address1": "Chennai",
  "address2": "Chennai",
  "city": "Chennai",
  "zip": "600069",
  "state": "Tamil Nadu",
  "phone": "9043570576"
}
```
This endpoint retrieves details of the authenticated user.

### HTTP Request

`GET /api/v2.1/me/`

### Fields

Name | Type | Description
-----|------|-------------
id   | int  | The user unique ID
batches | array | List of batches to which this user belongs
url  | string | URL to get details of the user
username | string | Username of the user
first_name | string | First name of the user
last_name | string | Last name of the user
display_name | string | Display name of the user (Concatenates first_name & last_name if available. Falls back to username)
email | string | Email of the user
photo | string | Original photo uploaded by the user
large_image | string | Profile photo transformed to 256x256 px
medium_image | string | Profile photo transformed to 128x128 px
small_image | string | Profile photo transformed to 48x48 px
x_small_image | string | Profile photo transformed to 32x32 px
mini_image | string | Profile photo transformed to 24x24 px
birth_date | datestring | Birth date as provided by the user
gender | string | Gender as provided by the user. Can be "Male", "Female" or "Transgender"
address1 | string | Address provided by the user
address2 | string | Address provided by the user
city | string | City provided by the user
zip | string | Pincode provided by the user
state | string | State provided by the user
phone | string | Phone provided by the user

## Get a single user

```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.1/users/18/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw'
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://demo.testpress.in/api/v2.1/users/18/"

headers = {
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw",
    'cache-control': "no-cache"
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```shell
curl --request GET \
  --url http://demo.testpress.in/api/v2.1/users/18/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw' \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("http://demo.testpress.in/api/v2.1/users/18/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "id": 18,
  "url": "http://demo.testpress.in/api/v2.1/users/18/",
  "username": "Vinoth",
  "display_name": "Vinoth Kumar",
  "first_name": "Vinoth",
  "last_name": "Kumar",
  "photo": "",
  "large_image": "",
  "medium_image": "",
  "small_image": "",
  "x_small_image": "",
  "mini_image": ""
}
```

This endpoint retrieves publicly available details of a single user.

<aside class="info">This endpoint protects the privacy of users. If the requested user is same as authenticated user, then the response will be same as <code>/api/v2.1/me/</code>. Otherwise, personal contact details will not be available.</aside>

### HTTP Request

`GET /api/v2.1/users/<id>`

### URL Parameters

Parameter | Description
--------- | -----------
id | The unique id of the user to retrieve

## Update current user

```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.1/users/17/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw'
request["content-type"] = 'application/json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"first_name\": \"John\",\n    \"last_name\": \"Appleseed\"\n}"

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://demo.testpress.in/api/v2.1/users/17/"

payload = "{\n    \"first_name\": \"John\",\n    \"last_name\": \"Appleseed\"\n}"
headers = {
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw",
    'content-type': "application/json",
    'cache-control': "no-cache"
    }

response = requests.request("PUT", url, data=payload, headers=headers)

print(response.text)
```

```shell
curl --request PUT \
  --url http://demo.testpress.in/api/v2.1/users/17/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw' \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json' \
  --data '{\n    "first_name": "John",\n    "last_name": "Appleseed"\n}'
```

```csharp
var client = new RestClient("http://demo.testpress.in/api/v2.1/users/17/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json");
request.AddHeader("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw");
request.AddParameter("application/json", "{\n    \"first_name\": \"John\",\n    \"last_name\": \"Appleseed\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "first_name": "John",
  "last_name": "Appleseed",
  "email": "testpress.in@gmail.com",
  "photo": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/9b69ab73fc924813871b2ef1e2ef00fa.jpeg",
  "large_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/493054067d1d4173a22d96b824d7f0c6.jpeg",
  "medium_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/8d96dab06a82487ab3149b771fe5d479.jpeg",
  "small_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/4023a394cd36472fa24db76e493192ce.jpeg",
  "x_small_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/796fa9a9727a42e4a7faa015b0388af3.jpeg",
  "mini_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/5f9215132af54acc8e72aed968582763.jpeg",
  "x_offset": 37,
  "y_offset": 0,
  "crop_height": 540,
  "crop_width": 539,
  "birth_date": "1994-08-27",
  "gender": 2,
  "address1": "Chennai",
  "address2": "Chennai",
  "city": "Chennai",
  "zip": "600069",
  "state_choices": 31,
  "phone": "9043570576"
}
```
This endpoint will update a user profile details. The data to update should be posted in the request body in JSON format.

<aside class="warning">An authenticated user can update only his profile.</aside>

### HTTP Request

`PUT /api/v2.1/users/<id>`

### URL Parameters

Parameter | Description
--------- | -----------
id | The unique id of the user to retrieve

# Exams

Exams API gives you access to read all the exams which can be accessed by the authenticated user.

## Get All Exams

```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.1/exams/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw'
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://demo.testpress.in/api/v2.1/exams/"

headers = {
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw",
    'cache-control': "no-cache",
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```shell
curl --request GET \
  --url http://demo.testpress.in/api/v2.1/exams/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6ImFkbWluIiwidXNlcl9pZCI6MTAsImVtYWlsIjoiYmhhcmF0aEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NDc4Mjk5Nzl9.a_LVMuVyMcNQ7Qlu3w7icUYAQa9Mv2jhYikih4r-Wn8' \
  --header 'cache-control: no-cache'
```

> The above command returns JSON structured like this:

```json


{
  "count": 2,
  "next": null,
  "previous": null,
  "per_page": 20,
  "results": [
    {
      "url": "http://demo.testpress.in/api/v2.1/exams/aptitude-analytical-maths-nbe-template-15/",
      "id": 2394,
      "title": "Aptitude Analytical Maths (NBE Template)",
      "description": "",
      "course": "Uncategorized",
      "start_date": "2013-08-02T17:25:22+05:30",
      "end_date": "2019-08-01T17:25:22+05:30",
      "duration": "0:30:30",
      "number_of_questions": 20,
      "negative_marks": "0.00",
      "mark_per_question": "1.00",
      "template_type": 4,
      "allow_retake": true,
      "max_retakes": null,
      "enable_ranks": false,
      "rank_publishing_date": null,
      "attempts_url": "http://demo.testpress.in/api/v2.1/exams/aptitude-analytical-maths-nbe-template-15/attempts/",
      "allow_pdf": true,
      "created": "2015-04-09T00:00:00Z",
      "slug": "aptitude-analytical-maths-nbe-template-15",
      "variable_mark_per_question": false,
      "show_answers": true,
      "comments_count": 0
    },
    {
      "url": "http://demo.testpress.in/api/v2.1/exams/aptitude-analytical-maths-nbe-template-16/",
      "id": 2395,
      "title": "Aptitude Analytical Maths (NBE Template)",
      "description": "",
      "course": "Uncategorized",
      "start_date": "2013-08-02T17:25:22+05:30",
      "end_date": "2019-08-01T17:25:22+05:30",
      "duration": "0:30:30",
      "number_of_questions": 20,
      "negative_marks": "0.00",
      "mark_per_question": "1.00",
      "template_type": 4,
      "allow_retake": true,
      "max_retakes": null,
      "enable_ranks": false,
      "rank_publishing_date": null,
      "attempts_url": "http://demo.testpress.in/api/v2.1/exams/aptitude-analytical-maths-nbe-template-16/attempts/",
      "allow_pdf": true,
      "created": "2015-04-09T00:00:00Z",
      "slug": "aptitude-analytical-maths-nbe-template-16",
      "variable_mark_per_question": false,
      "show_answers": true,
      "comments_count": 0
    }
  ]
}

```

This endpoint retrieves all exams for the authenticated user.

### HTTP Request

`GET /api/v2.1/exams/`

### Query Parameters

Parameter | Type | Description
--------- | ------- | -----------
course | string | Filters by course name. Ex: IBPS
state | string | Indicates state of the exams to return. Can be one of: available, upcoming, history
q | string | Filters by exam title. Useful to search by exam title.

## Get a single exam

```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.1/exams/aptitude-analytical-maths-nbe-template-15/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw'
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body

```

```python
import requests

url = "http://demo.testpress.in/api/v2.1/exams/aptitude-analytical-maths-nbe-template-15/"

headers = {
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw",
    'cache-control': "no-cache"
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```shell
curl --request GET \
  --url http://demo.testpress.in/api/v2.1/exams/aptitude-analytical-maths-nbe-template-15/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw' \
  --header 'cache-control: no-cache'
```

> The above command returns JSON structured like this:

```json
{
  "url": "http://demo.testpress.in/api/v2.1/exams/aptitude-analytical-maths-nbe-template-15/",
  "id": 2394,
  "title": "Aptitude Analytical Maths (NBE Template)",
  "description": "",
  "course": "Uncategorized",
  "start_date": "2013-08-02T17:25:22+05:30",
  "end_date": "2019-08-01T17:25:22+05:30",
  "duration": "0:30:30",
  "number_of_questions": 20,
  "negative_marks": "0.00",
  "mark_per_question": "1.00",
  "template_type": 4,
  "allow_retake": true,
  "max_retakes": null,
  "enable_ranks": false,
  "rank_publishing_date": null,
  "attempts_url": "http://demo.testpress.in/api/v2.1/exams/aptitude-analytical-maths-nbe-template-15/attempts/",
  "attempts": [
    {
      "url": "http://demo.testpress.in/api/v2.1/attempts/59591/",
      "id": 59591,
      "user": "testpress",
      "date": "2015-07-14T05:16:12.086Z",
      "total_questions": 20,
      "score": "2.00",
      "review_url": "http://demo.testpress.in/api/v2.1/attempts/59591/review/",
      "questions_url": "http://demo.testpress.in/api/v2.1/attempts/59591/questions/",
      "percentile": 80,
      "correct_count": 2,
      "incorrect_count": 6,
      "last_started_time": "2015-07-14T05:20:36.851Z",
      "remaining_time": "0:29:52",
      "time_taken": "0:00:38",
      "state": "Completed",
      "rank": "NA",
      "max_rank": 0,
      "percentage": "10",
      "unanswered_count": 12
    },
    {
      "url": "http://demo.testpress.in/api/v2.1/attempts/59312/",
      "id": 59312,
      "user": "testpress",
      "date": "2015-07-13T05:07:54.639Z",
      "total_questions": 20,
      "score": "0.00",
      "review_url": "http://demo.testpress.in/api/v2.1/attempts/59312/review/",
      "questions_url": "http://demo.testpress.in/api/v2.1/attempts/59312/questions/",
      "percentile": 40,
      "correct_count": 0,
      "incorrect_count": 0,
      "last_started_time": "2015-07-13T05:07:54.666Z",
      "remaining_time": "0:30:29",
      "time_taken": "0:00:01",
      "state": "Completed",
      "rank": "NA",
      "max_rank": 0,
      "percentage": "0",
      "unanswered_count": 20
    },
    {
      "url": "http://demo.testpress.in/api/v2.1/attempts/33827/",
      "id": 33827,
      "user": "testpress",
      "date": "2015-05-13T13:03:53.339Z",
      "total_questions": 20,
      "score": "0.00",
      "review_url": "http://demo.testpress.in/api/v2.1/attempts/33827/review/",
      "questions_url": "http://demo.testpress.in/api/v2.1/attempts/33827/questions/",
      "percentile": 40,
      "correct_count": 0,
      "incorrect_count": 1,
      "last_started_time": "2015-05-14T05:24:47.437Z",
      "remaining_time": "0:30:29",
      "time_taken": "0:00:01",
      "state": "Completed",
      "rank": "NA",
      "max_rank": 0,
      "percentage": "0",
      "unanswered_count": 19
    },
    {
      "url": "http://demo.testpress.in/api/v2.1/attempts/31823/",
      "id": 31823,
      "user": "testpress",
      "date": "2015-04-21T04:47:26.454Z",
      "total_questions": 20,
      "score": "0.00",
      "review_url": "http://demo.testpress.in/api/v2.1/attempts/31823/review/",
      "questions_url": "http://demo.testpress.in/api/v2.1/attempts/31823/questions/",
      "percentile": 40,
      "correct_count": 0,
      "incorrect_count": 2,
      "last_started_time": "2015-05-05T05:34:40.640Z",
      "remaining_time": "0:30:23",
      "time_taken": "0:00:07",
      "state": "Completed",
      "rank": "NA",
      "max_rank": 0,
      "percentage": "0",
      "unanswered_count": 18
    }
  ],
  "allow_pdf": true,
  "created": "2015-04-09T00:00:00Z",
  "slug": "aptitude-analytical-maths-nbe-template-15",
  "variable_mark_per_question": false,
  "show_answers": true,
  "comments_count": 0
}

```

This endpoint retrieves a single exam.

<aside class="danger">Note that some exams will return 403 Forbidden if they are not available for the authenticated user.</aside>


### HTTP Request

`GET /api/v2.1/exams/<slug>`

### URL Parameters

Parameter | Description
--------- | -----------
slug | The unique slug of the exam to retrieve

## Get Available Exams

```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.1/exams/available/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw'
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://demo.testpress.in/api/v2.1/exams/available/"

headers = {
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw",
    'cache-control': "no-cache",
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```shell
curl --request GET \
  --url http://demo.testpress.in/api/v2.1/exams/available/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw' \
  --header 'cache-control: no-cache'
```

> The above command returns JSON structured like this:

```json


{
  "count": 2,
  "next": null,
  "previous": null,
  "per_page": 20,
  "results": [
    {
      "url": "http://demo.testpress.in/api/v2.1/exams/aptitude-analytical-maths-nbe-template-15/",
      "id": 2394,
      "title": "Aptitude Analytical Maths (NBE Template)",
      "description": "",
      "course": "Uncategorized",
      "start_date": "2013-08-02T17:25:22+05:30",
      "end_date": "2019-08-01T17:25:22+05:30",
      "duration": "0:30:30",
      "number_of_questions": 20,
      "negative_marks": "0.00",
      "mark_per_question": "1.00",
      "template_type": 4,
      "allow_retake": true,
      "max_retakes": null,
      "enable_ranks": false,
      "rank_publishing_date": null,
      "attempts_url": "http://demo.testpress.in/api/v2.1/exams/aptitude-analytical-maths-nbe-template-15/attempts/",
      "allow_pdf": true,
      "created": "2015-04-09T00:00:00Z",
      "slug": "aptitude-analytical-maths-nbe-template-15",
      "variable_mark_per_question": false,
      "show_answers": true,
      "comments_count": 0
    },
    {
      "url": "http://demo.testpress.in/api/v2.1/exams/aptitude-analytical-maths-nbe-template-16/",
      "id": 2395,
      "title": "Aptitude Analytical Maths (NBE Template)",
      "description": "",
      "course": "Uncategorized",
      "start_date": "2013-08-02T17:25:22+05:30",
      "end_date": "2019-08-01T17:25:22+05:30",
      "duration": "0:30:30",
      "number_of_questions": 20,
      "negative_marks": "0.00",
      "mark_per_question": "1.00",
      "template_type": 4,
      "allow_retake": true,
      "max_retakes": null,
      "enable_ranks": false,
      "rank_publishing_date": null,
      "attempts_url": "http://demo.testpress.in/api/v2.1/exams/aptitude-analytical-maths-nbe-template-16/attempts/",
      "allow_pdf": true,
      "created": "2015-04-09T00:00:00Z",
      "slug": "aptitude-analytical-maths-nbe-template-16",
      "variable_mark_per_question": false,
      "show_answers": true,
      "comments_count": 0
    }
  ]
}

```

This endpoint retrieves all available and unattempted exams for the authenticated user. This is same as getting all exams with <code>state</code> query parameter as <code>available</code>.


### HTTP Request

`GET /api/v2.1/exams/available/`

### Query Parameters

Parameter | Type | Description
--------- | ------- | -----------
course | string | Filters by course name. Ex: IBPS
q | string | Filters by exam title. Useful to search by exam title.

## Get Upcoming Exams

```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.1/exams/upcoming/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw'
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://demo.testpress.in/api/v2.1/exams/upcoming/"

headers = {
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw",
    'cache-control': "no-cache",
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```shell
curl --request GET \
  --url http://demo.testpress.in/api/v2.1/exams/upcoming/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw' \
  --header 'cache-control: no-cache'
```

> The above command returns JSON structured like this:

```json


{
  "count": 2,
  "next": null,
  "previous": null,
  "per_page": 20,
  "results": [
    {
      "url": "http://demo.testpress.in/api/v2.1/exams/aptitude-analytical-maths-nbe-template-15/",
      "id": 2394,
      "title": "Aptitude Analytical Maths (NBE Template)",
      "description": "",
      "course": "Uncategorized",
      "start_date": "2013-08-02T17:25:22+05:30",
      "end_date": "2019-08-01T17:25:22+05:30",
      "duration": "0:30:30",
      "number_of_questions": 20,
      "negative_marks": "0.00",
      "mark_per_question": "1.00",
      "template_type": 4,
      "allow_retake": true,
      "max_retakes": null,
      "enable_ranks": false,
      "rank_publishing_date": null,
      "attempts_url": "http://demo.testpress.in/api/v2.1/exams/aptitude-analytical-maths-nbe-template-15/attempts/",
      "allow_pdf": true,
      "created": "2015-04-09T00:00:00Z",
      "slug": "aptitude-analytical-maths-nbe-template-15",
      "variable_mark_per_question": false,
      "show_answers": true,
      "comments_count": 0
    },
    {
      "url": "http://demo.testpress.in/api/v2.1/exams/aptitude-analytical-maths-nbe-template-16/",
      "id": 2395,
      "title": "Aptitude Analytical Maths (NBE Template)",
      "description": "",
      "course": "Uncategorized",
      "start_date": "2013-08-02T17:25:22+05:30",
      "end_date": "2019-08-01T17:25:22+05:30",
      "duration": "0:30:30",
      "number_of_questions": 20,
      "negative_marks": "0.00",
      "mark_per_question": "1.00",
      "template_type": 4,
      "allow_retake": true,
      "max_retakes": null,
      "enable_ranks": false,
      "rank_publishing_date": null,
      "attempts_url": "http://demo.testpress.in/api/v2.1/exams/aptitude-analytical-maths-nbe-template-16/attempts/",
      "allow_pdf": true,
      "created": "2015-04-09T00:00:00Z",
      "slug": "aptitude-analytical-maths-nbe-template-16",
      "variable_mark_per_question": false,
      "show_answers": true,
      "comments_count": 0
    }
  ]
}

```

This endpoint retrieves all upcoming exams for the authenticated user. This is same as getting all exams with <code>state</code> query parameter as <code>upcoming</code>.

### HTTP Request

`GET /api/v2.1/exams/upcoming/`

### Query Parameters

Parameter | Type | Description
--------- | ------- | -----------
course | string | Filters by course name. Ex: IBPS
q | string | Filters by exam title. Useful to search by exam title.

## Get History Exams

```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.1/exams/history/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw'
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://demo.testpress.in/api/v2.1/exams/history/"

headers = {
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw",
    'cache-control': "no-cache",
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```shell
curl --request GET \
  --url http://demo.testpress.in/api/v2.1/exams/history/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw' \
  --header 'cache-control: no-cache'
```

> The above command returns JSON structured like this:

```json


{
  "count": 2,
  "next": null,
  "previous": null,
  "per_page": 20,
  "results": [
    {
      "url": "http://demo.testpress.in/api/v2.1/exams/aptitude-analytical-maths-nbe-template-15/",
      "id": 2394,
      "title": "Aptitude Analytical Maths (NBE Template)",
      "description": "",
      "course": "Uncategorized",
      "start_date": "2013-08-02T17:25:22+05:30",
      "end_date": "2019-08-01T17:25:22+05:30",
      "duration": "0:30:30",
      "number_of_questions": 20,
      "negative_marks": "0.00",
      "mark_per_question": "1.00",
      "template_type": 4,
      "allow_retake": true,
      "max_retakes": null,
      "enable_ranks": false,
      "rank_publishing_date": null,
      "attempts_url": "http://demo.testpress.in/api/v2.1/exams/aptitude-analytical-maths-nbe-template-15/attempts/",
      "allow_pdf": true,
      "created": "2015-04-09T00:00:00Z",
      "slug": "aptitude-analytical-maths-nbe-template-15",
      "variable_mark_per_question": false,
      "show_answers": true,
      "comments_count": 0
    },
    {
      "url": "http://demo.testpress.in/api/v2.1/exams/aptitude-analytical-maths-nbe-template-16/",
      "id": 2395,
      "title": "Aptitude Analytical Maths (NBE Template)",
      "description": "",
      "course": "Uncategorized",
      "start_date": "2013-08-02T17:25:22+05:30",
      "end_date": "2019-08-01T17:25:22+05:30",
      "duration": "0:30:30",
      "number_of_questions": 20,
      "negative_marks": "0.00",
      "mark_per_question": "1.00",
      "template_type": 4,
      "allow_retake": true,
      "max_retakes": null,
      "enable_ranks": false,
      "rank_publishing_date": null,
      "attempts_url": "http://demo.testpress.in/api/v2.1/exams/aptitude-analytical-maths-nbe-template-16/attempts/",
      "allow_pdf": true,
      "created": "2015-04-09T00:00:00Z",
      "slug": "aptitude-analytical-maths-nbe-template-16",
      "variable_mark_per_question": false,
      "show_answers": true,
      "comments_count": 0
    }
  ]
}

```

This endpoint retrieves all history exams for the authenticated user. This is same as getting all exams with <code>state</code> query parameter as <code>history</code>.

### HTTP Request

`GET /api/v2.1/exams/history/`

### Query Parameters

Parameter | Type | Description
--------- | ------- | -----------
course | string | Filters by course name. Ex: IBPS
q | string | Filters by exam title. Useful to search by exam title.

# Attempts

Attempts API gives you access to read all the attempts which can be accessed by the authenticated user.

## Get All Attempts

```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.1/attempts/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw'
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://demo.testpress.in/api/v2.1/attempts/"

headers = {
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw",
    'cache-control': "no-cache",
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```shell
curl --request GET \
  --url http://demo.testpress.in/api/v2.1/attempts/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw' \
  --header 'cache-control: no-cache'
```

> The above command returns JSON structured like this:

```json
{
  "count": 2,
  "next": null,
  "previous": null,
  "per_page": 20,
  "results": [
    {
      "url": "http://demo.testpress.in/api/v2.1/attempts/125894/",
      "id": 125894,
      "exam": {
        "url": "http://demo.testpress.in/api/v2.1/exams/forum-ias-rbi-demo/",
        "id": 3720,
        "title": "FORUM IAS RBI DEMO",
        "description": "",
        "course": "TNPSC",
        "start_date": "2015-11-07T12:37:11+05:30",
        "end_date": "2015-11-15T12:37:11+05:30",
        "duration": "3:00:00",
        "number_of_questions": 200,
        "negative_marks": "0.00",
        "mark_per_question": "1.00",
        "template_type": 2,
        "allow_retake": true,
        "max_retakes": null,
        "enable_ranks": false,
        "rank_publishing_date": null,
        "allow_pdf": false,
        "created": "2015-11-07T07:07:41.597Z",
        "slug": "forum-ias-rbi-demo",
        "variable_mark_per_question": false,
        "show_answers": true
      },
      "user": "testpress",
      "date": "2015-11-07T07:12:49.873Z",
      "total_questions": 200,
      "score": "0.00",
      "review_url": "http://demo.testpress.in/api/v2.1/attempts/125894/review/",
      "questions_url": "http://demo.testpress.in/api/v2.1/attempts/125894/questions/",
      "percentile": 0,
      "correct_count": 0,
      "incorrect_count": 0,
      "last_started_time": "2015-11-07T08:02:46.845Z",
      "remaining_time": "2:10:03",
      "time_taken": "0:49:57",
      "state": "Running",
      "rank": "NA",
      "max_rank": 0,
      "percentage": "0",
      "unanswered_count": 0,
      "commented_questions_count": 0,
      "comments_count": 0,
      "allow_retake": true,
      "remaining_attempts": null,
      "total_bonus": 0
    },
    {
      "url": "http://demo.testpress.in/api/v2.1/attempts/125872/",
      "id": 125872,
      "exam": {
        "url": "http://demo.testpress.in/api/v2.1/exams/aiims-exam/",
        "id": 3625,
        "title": "AIIMS Exam",
        "description": "",
        "course": "TNPSC",
        "start_date": "2015-10-20T18:12:26+05:30",
        "end_date": null,
        "duration": "3:12:27",
        "number_of_questions": 200,
        "negative_marks": "0.00",
        "mark_per_question": "1.00",
        "template_type": 3,
        "allow_retake": true,
        "max_retakes": null,
        "enable_ranks": true,
        "rank_publishing_date": "2015-10-20T12:42:44Z",
        "allow_pdf": false,
        "created": "2015-10-20T12:43:01.684Z",
        "slug": "aiims-exam",
        "variable_mark_per_question": false,
        "show_answers": true
      },
      "user": "testpress",
      "date": "2015-11-07T06:17:42.313Z",
      "total_questions": 200,
      "score": "0.00",
      "review_url": "http://demo.testpress.in/api/v2.1/attempts/125872/review/",
      "questions_url": "http://demo.testpress.in/api/v2.1/attempts/125872/questions/",
      "percentile": 60,
      "correct_count": 0,
      "incorrect_count": 0,
      "last_started_time": "2015-11-07T06:17:42.375Z",
      "remaining_time": "3:12:26",
      "time_taken": "0:00:01",
      "state": "Completed",
      "rank": 4,
      "max_rank": 5,
      "percentage": "0",
      "unanswered_count": 200,
      "commented_questions_count": 0,
      "comments_count": 0,
      "allow_retake": true,
      "remaining_attempts": null,
      "total_bonus": 0
    }
  ]
}

```

This endpoint retrieves all attempts for the authenticated user.

### HTTP Request

`GET /api/v2.1/attempts/`

### Query Parameters

Parameter | Type | Description
--------- | ------- | -----------
course | string | Filters by course name. Ex: IBPS
q | string | Filters by exam title. Useful to search by exam title.

## Get a single attempt

```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.1/attempts/125894/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw'
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://demo.testpress.in/api/v2.1/attempts/125894/"

headers = {
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw",
    'cache-control': "no-cache"
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```shell
curl --request GET \
  --url http://demo.testpress.in/api/v2.1/attempts/125894/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw' \
  --header 'cache-control: no-cache'
```

> The above command returns JSON structured like this:

```json
{
  "url": "http://demo.testpress.in/api/v2.1/attempts/125894/",
  "id": 125894,
  "exam": {
    "url": "http://demo.testpress.in/api/v2.1/exams/forum-ias-rbi-demo/",
    "id": 3720,
    "title": "FORUM IAS RBI DEMO",
    "description": "",
    "course": "TNPSC",
    "start_date": "2015-11-07T12:37:11+05:30",
    "end_date": "2015-11-15T12:37:11+05:30",
    "duration": "3:00:00",
    "number_of_questions": 200,
    "negative_marks": "0.00",
    "mark_per_question": "1.00",
    "template_type": 2,
    "allow_retake": true,
    "max_retakes": null,
    "enable_ranks": false,
    "rank_publishing_date": null,
    "allow_pdf": false,
    "created": "2015-11-07T07:07:41.597Z",
    "slug": "forum-ias-rbi-demo",
    "variable_mark_per_question": false,
    "show_answers": true
  },
  "user": "testpress",
  "date": "2015-11-07T07:12:49.873Z",
  "total_questions": 200,
  "score": "0.00",
  "review_url": "http://demo.testpress.in/api/v2.1/attempts/125894/review/",
  "questions_url": "http://demo.testpress.in/api/v2.1/attempts/125894/questions/",
  "percentile": 0,
  "correct_count": 0,
  "incorrect_count": 0,
  "last_started_time": "2015-11-07T08:02:46.845Z",
  "remaining_time": "2:10:03",
  "time_taken": "0:49:57",
  "state": "Running",
  "rank": "NA",
  "max_rank": 0,
  "percentage": "0",
  "unanswered_count": 0,
  "commented_questions_count": 0,
  "comments_count": 0,
  "total_bonus": 0
}

```

This endpoint retrieves a single attempt.

<aside class="danger">Note that some attempts will return 403 Forbidden if they do not belong to the authenticated user.</aside>

### HTTP Request

`GET /api/v2.1/attempts/<id>`

### URL Parameters

Parameter | Description
--------- | -----------
id | The unique id of the attempt to retrieve

## Start an attempt

```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.1/attempts/125894/start/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw'
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://demo.testpress.in/api/v2.1/attempts/125894/start/"

headers = {
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw",
    'cache-control': "no-cache"
    }

response = requests.request("PUT", url, headers=headers)

print(response.text)
```

```shell
curl --request PUT \
  --url http://demo.testpress.in/api/v2.1/attempts/125894/start/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw' \
  --header 'cache-control: no-cache'
```

> The above command returns JSON structured like this:

```json
{
  "url": "http://demo.testpress.in/api/v2.1/attempts/125894/",
  "id": 125894,
  "exam": {
    "url": "http://demo.testpress.in/api/v2.1/exams/forum-ias-rbi-demo/",
    "id": 3720,
    "title": "FORUM IAS RBI DEMO",
    "description": "",
    "course": "TNPSC",
    "start_date": "2015-11-07T12:37:11+05:30",
    "end_date": "2015-11-15T12:37:11+05:30",
    "duration": "3:00:00",
    "number_of_questions": 200,
    "negative_marks": "0.00",
    "mark_per_question": "1.00",
    "template_type": 2,
    "allow_retake": true,
    "max_retakes": null,
    "enable_ranks": false,
    "rank_publishing_date": null,
    "allow_pdf": false,
    "created": "2015-11-07T07:07:41.597Z",
    "slug": "forum-ias-rbi-demo",
    "variable_mark_per_question": false,
    "show_answers": true
  },
  "user": "testpress",
  "date": "2015-11-07T07:12:49.873Z",
  "total_questions": 200,
  "score": "0.00",
  "review_url": "http://demo.testpress.in/api/v2.1/attempts/125894/review/",
  "questions_url": "http://demo.testpress.in/api/v2.1/attempts/125894/questions/",
  "percentile": 0,
  "correct_count": 0,
  "incorrect_count": 0,
  "last_started_time": "2015-11-18T09:50:20.287Z",
  "remaining_time": "2:10:03",
  "time_taken": "0:49:57",
  "state": "Running",
  "rank": "NA",
  "max_rank": 0,
  "percentage": "0",
  "unanswered_count": 0,
  "commented_questions_count": 0,
  "comments_count": 0,
  "total_bonus": 0
}

```

This endpoint starts a paused attempt. This is for restarting the timer calculation incase of a paused attempt. 

<aside class="info">It is best practice to always call this API when trying to resume a paused exam. If not done, the server might end the exam as time over if the time elapsed exceeds the assigned time for the exam.</aside>

### HTTP Request

`PUT /api/v2.1/attempts/<id>/start/`

### URL Parameters

Parameter | Description
--------- | -----------
id | The unique id of the attempt to retrieve

## End an attempt

```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.1/attempts/125894/end/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw'
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://demo.testpress.in/api/v2.1/attempts/125894/end/"

headers = {
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw",
    'cache-control': "no-cache"
    }

response = requests.request("PUT", url, headers=headers)

print(response.text)
```

```shell
curl --request PUT \
  --url http://demo.testpress.in/api/v2.1/attempts/125894/end/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw' \
  --header 'cache-control: no-cache'
```

> The above command returns JSON structured like this:

```json
{
  "url": "http://demo.testpress.in/api/v2.1/attempts/125894/",
  "id": 125894,
  "exam": {
    "url": "http://demo.testpress.in/api/v2.1/exams/forum-ias-rbi-demo/",
    "id": 3720,
    "title": "FORUM IAS RBI DEMO",
    "description": "",
    "course": "TNPSC",
    "start_date": "2015-11-07T12:37:11+05:30",
    "end_date": "2015-11-15T12:37:11+05:30",
    "duration": "3:00:00",
    "number_of_questions": 200,
    "negative_marks": "0.00",
    "mark_per_question": "1.00",
    "template_type": 2,
    "allow_retake": true,
    "max_retakes": null,
    "enable_ranks": false,
    "rank_publishing_date": null,
    "allow_pdf": false,
    "created": "2015-11-07T07:07:41.597Z",
    "slug": "forum-ias-rbi-demo",
    "variable_mark_per_question": false,
    "show_answers": true
  },
  "user": "testpress",
  "date": "2015-11-07T07:12:49.873Z",
  "total_questions": 200,
  "score": "2.00",
  "review_url": "http://demo.testpress.in/api/v2.1/attempts/125894/review/",
  "questions_url": "http://demo.testpress.in/api/v2.1/attempts/125894/questions/",
  "percentile": 100,
  "correct_count": 2,
  "incorrect_count": 6,
  "last_started_time": "2015-11-18T09:50:20.287Z",
  "remaining_time": "2:10:03",
  "time_taken": "0:49:57",
  "state": "Completed",
  "rank": "NA",
  "max_rank": 0,
  "percentage": "1",
  "unanswered_count": 192,
  "commented_questions_count": 0,
  "comments_count": 0,
  "total_bonus": 0
}

```

This endpoint ends an attempt. The <code>state</code> of the attempt will return as <code>Completed</code>. An attempt which has been ended cannot be started again using the <code>/start/</code> end point.

<aside class="warning">One cannot review an attempt if this API is not called.</aside>

### HTTP Request

`PUT /api/v2.1/attempts/<id>/end/`

### URL Parameters

Parameter | Description
--------- | -----------
id | The unique id of the attempt to retrieve

## Get attempt questions

```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.1/attempts/122046/questions/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw'
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://demo.testpress.in/api/v2.1/attempts/122046/questions/"

headers = {
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw",
    'cache-control': "no-cache"
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```shell
curl --request GET \
  --url http://demo.testpress.in/api/v2.1/attempts/122046/questions/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw' \
  --header 'cache-control: no-cache'
```

> The above command returns JSON structured like this:

```json
{
  "count": 100,
  "next": "http://demo.testpress.in/api/v2.1/attempts/122046/questions/?page=2",
  "previous": null,
  "per_page": 20,
  "results": [
    {
      "id": 12705318,
      "url": "http://demo.testpress.in/api/v2.1/attempts/122046/questions/12705318/",
      "question": {
        "question_html": "<p>Which of the following is/are the principal feature (s) of the Government of India Act, 1919? <br>\n1. Introduction of dyarchy in the executive government of the provinces<br>\n2. Introduction of separate communal electorates for Muslims<br>\n3. Devolution of legislative authority by the centre to the provinces</p><p>Select the correct answer using the codes given below:</p><p><img src=\"https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/ebd87eb5c09b445d879610586fca072e.png\"></p>",
        "direction": null,
        "answers": [
          {
            "text_html": "<p>1 only</p>",
            "id": 129
          },
          {
            "text_html": "<p>2 and 3 only</p>",
            "id": 130
          },
          {
            "text_html": "<p>1 and 3 only</p>",
            "id": 131
          },
          {
            "text_html": "<p>1, 2 and 3</p>",
            "id": 132
          }
        ],
        "essay_topics": [],
        "subject": "khecha subject",
        "type": "C"
      },
      "duration": null,
      "selected_answers": [],
      "essay_text": null,
      "essay_topic": null,
      "review": null
    },
    {
      "id": 12705296,
      "url": "http://demo.testpress.in/api/v2.1/attempts/122046/questions/12705296/",
      "question": {
        "question_html": "<p>With reference to National Rural Health Mission, which of the following are the jobs of ASHA, a trained community health worker?</p>\n<p>1.Accompanying women to the health facility for antenatal care checkup</p>\n<p>2.Using pregnancy test kits for early detection of pregnancy </p>\n<p>3.Providing information on nutrition and immunization</p>\n<p>4.Conducting the delivery of baby</p>\n<p>Select the correct answer using the codes given below:</p>",
        "direction": null,
        "answers": [
          {
            "text_html": "<p>1, 2 and 3 Only</p>",
            "id": 413
          },
          {
            "text_html": "<p>2 and 4 Only</p>",
            "id": 414
          },
          {
            "text_html": "<p>1 and 3 Only</p>",
            "id": 415
          },
          {
            "text_html": "<p>1, 2, 3 and 4</p>",
            "id": 416
          }
        ],
        "essay_topics": [],
        "subject": "Sin Questions",
        "type": "R"
      },
      "duration": null,
      "selected_answers": [],
      "essay_text": null,
      "essay_topic": null,
      "review": null
    }
  ]
}

```

This endpoint returns all questions for an attempt.

<aside class="danger">This will fail if the attempt is in <code>Completed</code> state.</aside>

### HTTP Request

`PUT /api/v2.1/attempts/<id>/questions/`

### URL Parameters

Parameter | Description
--------- | -----------
id | The unique id of the attempt to retrieve

## Modify attempt questions

```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.1/attempts/122046/questions/12705318/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw'
request["content-type"] = 'application/json'
request["cache-control"] = 'no-cache'
request.body = "{\n\"selected_answers\": [129, 130],\n\"review\": true\n}"

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://demo.testpress.in/api/v2.1/attempts/122046/questions/12705318/"

payload = "{\n\"selected_answers\": [129, 130],\n\"review\": true\n}"
headers = {
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw",
    'content-type': "application/json",
    'cache-control': "no-cache"
    }

response = requests.request("PUT", url, data=payload, headers=headers)

print(response.text)
```

```shell
curl --request PUT \
  --url http://demo.testpress.in/api/v2.1/attempts/122046/questions/12705318/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw' \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json' \
  --data '{\n"selected_answers": [129, 130],\n"review": true\n}'
```

> The above command returns JSON structured like this:

```json
{
  "id": 12705318,
  "url": "http://demo.testpress.in/api/v2.1/attempts/122046/questions/12705318/",
  "question": {
    "question_html": "<p>Which of the following is/are the principal feature (s) of the Government of India Act, 1919? <br>\n1. Introduction of dyarchy in the executive government of the provinces<br>\n2. Introduction of separate communal electorates for Muslims<br>\n3. Devolution of legislative authority by the centre to the provinces</p><p>Select the correct answer using the codes given below:</p><p><img src=\"https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/ebd87eb5c09b445d879610586fca072e.png\"></p>",
    "direction": null,
    "answers": [
      {
        "text_html": "<p>1 only</p>",
        "id": 129
      },
      {
        "text_html": "<p>2 and 3 only</p>",
        "id": 130
      },
      {
        "text_html": "<p>1 and 3 only</p>",
        "id": 131
      },
      {
        "text_html": "<p>1, 2 and 3</p>",
        "id": 132
      }
    ],
    "essay_topics": [],
    "subject": "khecha subject",
    "type": "C"
  },
  "duration": "20 days, 3:58:48.044696",
  "selected_answers": [
    129,
    130
  ],
  "essay_text": null,
  "essay_topic": null,
  "review": true
}

```

This endpoint will update a question with the <code>selected_answers</code> and <code>review</code>.

<aside class="danger">This will fail if the attempt is in <code>Completed</code> state.</aside>

### HTTP Request

`PUT /api/v2.1/attempts/<id>/questions/<question_id>`

### URL Parameters

Parameter | Description
--------- | -----------
id | The unique id of the attempt
question_id | The unique id of the attempt question

## Review attempt questions

```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.1/attempts/122046/review/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw'
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://demo.testpress.in/api/v2.1/attempts/122046/review/"

headers = {
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw",
    'cache-control': "no-cache"
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```shell
curl --request GET \
  --url http://demo.testpress.in/api/v2.1/attempts/122046/review/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw' \
  --header 'cache-control: no-cache'
```

> The above command returns JSON structured like this:

```json
{
  "count": 100,
  "next": "http://demo.testpress.in/api/v2.1/attempts/122046/questions/?page=2",
  "previous": null,
  "per_page": 20,
  "results": [
    {
      "id": 12705318,
      "url": "http://demo.testpress.in/api/v2.1/attempts/122046/questions/12705318/",
      "question": {
        "question_html": "<p>Which of the following is/are the principal feature (s) of the Government of India Act, 1919? <br>\n1. Introduction of dyarchy in the executive government of the provinces<br>\n2. Introduction of separate communal electorates for Muslims<br>\n3. Devolution of legislative authority by the centre to the provinces</p><p>Select the correct answer using the codes given below:</p><p><img src=\"https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/ebd87eb5c09b445d879610586fca072e.png\"></p>",
        "direction": null,
        "answers": [
          {
            "text_html": "<p>1 only</p>",
            "id": 129
          },
          {
            "text_html": "<p>2 and 3 only</p>",
            "id": 130
          },
          {
            "text_html": "<p>1 and 3 only</p>",
            "id": 131
          },
          {
            "text_html": "<p>1, 2 and 3</p>",
            "id": 132
          }
        ],
        "essay_topics": [],
        "subject": "khecha subject",
        "type": "C"
      },
      "duration": null,
      "selected_answers": [],
      "essay_text": null,
      "essay_topic": null,
      "review": null
    },
    {
      "id": 12705296,
      "url": "http://demo.testpress.in/api/v2.1/attempts/122046/questions/12705296/",
      "question": {
        "question_html": "<p>With reference to National Rural Health Mission, which of the following are the jobs of ASHA, a trained community health worker?</p>\n<p>1.Accompanying women to the health facility for antenatal care checkup</p>\n<p>2.Using pregnancy test kits for early detection of pregnancy </p>\n<p>3.Providing information on nutrition and immunization</p>\n<p>4.Conducting the delivery of baby</p>\n<p>Select the correct answer using the codes given below:</p>",
        "direction": null,
        "answers": [
          {
            "text_html": "<p>1, 2 and 3 Only</p>",
            "id": 413
          },
          {
            "text_html": "<p>2 and 4 Only</p>",
            "id": 414
          },
          {
            "text_html": "<p>1 and 3 Only</p>",
            "id": 415
          },
          {
            "text_html": "<p>1, 2, 3 and 4</p>",
            "id": 416
          }
        ],
        "essay_topics": [],
        "subject": "Sin Questions",
        "type": "R"
      },
      "duration": null,
      "selected_answers": [],
      "essay_text": null,
      "essay_topic": null,
      "review": null
    }
  ]
}

```

This endpoint returns all questions for an attempt.

<aside class="danger">This will fail if the attempt is in <code>Completed</code> state.</aside>

### HTTP Request

`GET /api/v2.1/attempts/<id>/questions/`

### URL Parameters

Parameter | Description
--------- | -----------
id | The unique id of the attempt to retrieve

# Products

Products API gives you access to read all the products which are active and can be purchased.

## Get All Products

```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.1/products/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw'
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://demo.testpress.in/api/v2.1/products/"

headers = {
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw",
    'cache-control': "no-cache"
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```shell
curl --request GET \
  --url http://demo.testpress.in/api/v2.1/products/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw' \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("http://demo.testpress.in/api/v2.1/products/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "count": 1,
  "next": null,
  "previous": null,
  "per_page": 20,
  "results": [
    {
      "id": 243,
      "url": "http://demo.testpress.in/api/v2.1/products/free-ias-prelims-power-pack/",
      "title": "Free IAS Prelims Power Pack",
      "slug": "free-ias-prelims-power-pack",
      "image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/770056a05ab2433191eeeef8de75210f.png",
      "images": [
        {
          "original": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/770056a05ab2433191eeeef8de75210f.png",
          "medium": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/bfbfcf2f31f84c5aada30eba2ae6bd2e.png",
          "small": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/63b181a83d8c4e198309cacb110bac35.png"
        }
      ],
      "start_date": "2015-01-01T00:00:00+05:30",
      "end_date": "2021-12-31T00:00:00+05:30",
      "categories": [
        "TNPSC"
      ],
      "types": [
        "E-books",
        "Exams"
      ],
      "exams_count": 1,
      "notes_count": 0,
      "price": "1.00"
    }
  ]
}
```

This endpoint retrieves all products available for purchase in an institute.

### HTTP Request

`GET /api/v2.1/products/`

### Query Parameters

Parameter | Type | Description
--------- | ------- | -----------
category | string | Filters by category name. Ex: IBPS

### Fields

Name | Type | Description
-----|------|-------------
id   | int  | The product unique ID
url  | string | URL to get details of the product
title | string | Title of the product
slug | string | Human readable keyword string of the product
images | array | An array of image urls for the product <ul><li>original - User uploaded size</li><li>medium - 300x250px</li><li>small - 100x83px</li></ul>
start_date | datestring | Start date of product
end_date | datestring | End date of product
categories | array | Categories to which this product belongs
types | array | Type of goods included in this package. Can be E-books, Exams, Classroom Program, Books
price | string | Price of the product in INR
exams_count | int | Number of exams present in this product
notes_count | int | Number of documents present in this product

## Get a single product

```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.1/products/free-ias-prelims-power-pack/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw'
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://demo.testpress.in/api/v2.1/products/free-ias-prelims-power-pack/"

headers = {
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw",
    'cache-control': "no-cache"
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```shell
curl --request GET \
  --url http://demo.testpress.in/api/v2.1/products/free-ias-prelims-power-pack/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw' \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("http://demo.testpress.in/api/v2.1/products/free-ias-prelims-power-pack/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "count": 1,
  "next": null,
  "previous": null,
  "per_page": 20,
  "results": [
    {
      "id": 243,
      "url": "http://demo.testpress.in/api/v2.1/products/free-ias-prelims-power-pack/",
      "title": "Free IAS Prelims Power Pack",
      "slug": "free-ias-prelims-power-pack",
      "image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/770056a05ab2433191eeeef8de75210f.png",
      "images": [
        {
          "original": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/770056a05ab2433191eeeef8de75210f.png",
          "medium": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/bfbfcf2f31f84c5aada30eba2ae6bd2e.png",
          "small": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/63b181a83d8c4e198309cacb110bac35.png"
        }
      ],
      "start_date": "2015-01-01T00:00:00+05:30",
      "end_date": "2021-12-31T00:00:00+05:30",
      "categories": [
        "TNPSC"
      ],
      "types": [
        "E-books",
        "Exams"
      ],
      "exams_count": 1,
      "notes_count": 0,
      "price": "1.00"
    }
  ]
}
```

This endpoint retrieves all products available for purchase in an institute.

### HTTP Request

`GET /api/v2.1/products/<slug>`

### URL Parameters

Parameter | Description
--------- | -----------
slug | The unique slug of the product to retrieve

### Fields

Name | Type | Description
-----|------|-------------
description | string | Brief description of the product
exams | array | [Exams](#get-a-single-exam) present in this product
notes | array | Documents present in this product
requires_shipping | boolean | Whether the product has shippable goods

# Posts

Posts are broadcast data which the institutes want to share to their users. This endpoint can be used to retrieve the posts which are accessible to a particular user.

## Get all posts
```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.1/posts/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw'
request["content-type"] = 'application/json'
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://demo.testpress.in/api/v2.1/posts/"

headers = {
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw",
    'content-type': "application/json",
    'cache-control': "no-cache"
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```shell
curl --request GET \
  --url http://demo.testpress.in/api/v2.1/posts/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw' \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json'
```

```csharp
var client = new RestClient("http://demo.testpress.in/api/v2.1/posts/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json");
request.AddHeader("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "count": 2,
  "next": "http://demo.testpress.in/api/v2.1/posts/?page=2",
  "previous": null,
  "per_page": 20,
  "results": [
    {
      "url": "http://demo.testpress.in/api/v2.1/posts/post-title2/",
      "created_by": {
        "id": 10,
        "url": "http://demo.testpress.in/api/v2.1/users/10/",
        "username": "admin",
        "display_name": "admin",
        "first_name": "",
        "last_name": "",
        "photo": "",
        "large_image": "",
        "medium_image": "",
        "small_image": "",
        "x_small_image": "",
        "mini_image": ""
      },
      "category": {
        "id": 2,
        "name": "Daliy News",
        "color": "33CC33",
        "slug": "daliy-news"
      },
      "created": "2015-10-15T15:24:34Z",
      "modified": "2015-10-15T15:24:34Z",
      "id": 33,
      "active": true,
      "title": "Post Title2",
      "summary": "summary goes here",
      "institute": 1
    },
    {
      "url": "http://demo.testpress.in/api/v2.1/posts/working-great/",
      "created_by": {
        "id": 10,
        "url": "http://demo.testpress.in/api/v2.1/users/10/",
        "username": "admin",
        "display_name": "admin",
        "first_name": "",
        "last_name": "",
        "photo": "",
        "large_image": "",
        "medium_image": "",
        "small_image": "",
        "x_small_image": "",
        "mini_image": ""
      },
      "category": {
        "id": 2,
        "name": "Daliy News",
        "color": "33CC33",
        "slug": "daliy-news"
      },
      "created": "2015-10-07T06:00:07Z",
      "modified": "2015-10-07T06:00:07Z",
      "id": 26,
      "active": true,
      "title": "Working Great",
      "summary": "All is Well",
      "institute": 1
    }
  ]
}
```

This endpoint retrieves all posts for the authenticated user.

### HTTP Request

`GET /api/v2.1/posts/`

### Query Parameters

Parameter | Type | Description
--------- | ------- | -----------
gt | datestring | Filter posts created greater than the date
lt | datestring | Filter posts created lesser than the date
order | string | Order posts based on the field queried. For descending order, prefix with '-'
category | string | Filter posts based on category

## Get single post

```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.1/posts/working-great/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw'
request["content-type"] = 'application/json'
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://demo.testpress.in/api/v2.1/posts/working-great/"

headers = {
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw",
    'content-type': "application/json",
    'cache-control': "no-cache"
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```shell
curl --request GET \
  --url http://demo.testpress.in/api/v2.1/posts/working-great/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw' \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json'
```

```csharp
var client = new RestClient("http://demo.testpress.in/api/v2.1/posts/working-great/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json");
request.AddHeader("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "url": "http://demo.testpress.in/api/v2.1/posts/working-great/",
  "created_by": {
    "id": 10,
    "url": "http://demo.testpress.in/api/v2.1/users/10/",
    "username": "admin",
    "display_name": "admin",
    "first_name": "",
    "last_name": "",
    "photo": "",
    "large_image": "",
    "medium_image": "",
    "small_image": "",
    "x_small_image": "",
    "mini_image": ""
  },
  "category": {
    "id": 2,
    "name": "Daliy News",
    "color": "33CC33",
    "slug": "daliy-news"
  },
  "created": "2015-10-07T06:00:07Z",
  "modified": "2015-10-07T06:00:07Z",
  "id": 26,
  "active": true,
  "title": "Working Great",
  "summary": "All is Well",
  "content_html": "<p>Good Better Best</p>",
  "institute": 1
}
```

This endpoint retrieves a single post.

<aside class="danger">Note that some posts will return 403 Forbidden if they are not available for the authenticated user.</aside>


### HTTP Request

`GET /api/v2.1/posts/<slug>`

### URL Parameters

Parameter | Description
--------- | -----------
slug | The unique slug of the post to retrieve

