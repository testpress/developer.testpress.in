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
curl -X POST -H "Content-Type: application/json" -H "Cache-Control: no-cache" -d '{
    "username": "testpress",
    "password": "demo"
}' 'https://demo.testpress.in/api/v2.1/auth-token/'
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

# Exams

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
curl -X GET -H "Authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw" -H "Cache-Control: no-cache" 'http://demo.testpress.in/api/v2.1/exams/'
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
    'cache-control': "no-cache",
    'postman-token': "56c3dd46-4ff2-c2dc-f886-a32f3c91d933"
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```shell
curl -X GET -H "Authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw" -H "Cache-Control: no-cache" 'http://demo.testpress.in/api/v2.1/exams/aptitude-analytical-maths-nbe-template-15/'
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

