# Attempts

Attempts API gives you access to read all the attempts which can be accessed by the authenticated user.

## Get All Attempts

```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.2/attempts/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw'
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://demo.testpress.in/api/v2.2/attempts/"

headers = {
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw",
    'cache-control': "no-cache",
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```shell
curl --request GET \
  --url http://demo.testpress.in/api/v2.2/attempts/ \
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
      "url": "http://demo.testpress.in/api/v2.2/attempts/125894/",
      "id": 125894,
      "exam": {
        "url": "http://demo.testpress.in/api/v2.2/exams/forum-ias-rbi-demo/",
        "id": 3720,
        "title": "FORUM IAS RBI DEMO",
        "description": "",
        "course": "TNPSC",
        "start_date": "2.25-11-07T12:37:11+05:30",
        "end_date": "2.25-11-15T12:37:11+05:30",
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
        "created": "2.25-11-07T07:07:41.597Z",
        "slug": "forum-ias-rbi-demo",
        "variable_mark_per_question": false,
        "show_answers": true
      },
      "user": "testpress",
      "date": "2.25-11-07T07:12:49.873Z",
      "total_questions": 200,
      "score": "0.00",
      "review_url": "http://demo.testpress.in/api/v2.2/attempts/125894/review/",
      "questions_url": "http://demo.testpress.in/api/v2.2/attempts/125894/questions/",
      "percentile": 0,
      "correct_count": 0,
      "incorrect_count": 0,
      "last_started_time": "2.25-11-07T08:02:46.845Z",
      "remaining_time": "2.20:03",
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
      "url": "http://demo.testpress.in/api/v2.2/attempts/125872/",
      "id": 125872,
      "exam": {
        "url": "http://demo.testpress.in/api/v2.2/exams/aiims-exam/",
        "id": 3625,
        "title": "AIIMS Exam",
        "description": "",
        "course": "TNPSC",
        "start_date": "2.25-10-20T18:12:26+05:30",
        "end_date": null,
        "duration": "3:12:27",
        "number_of_questions": 200,
        "negative_marks": "0.00",
        "mark_per_question": "1.00",
        "template_type": 3,
        "allow_retake": true,
        "max_retakes": null,
        "enable_ranks": true,
        "rank_publishing_date": "2.25-10-20T12:42:44Z",
        "allow_pdf": false,
        "created": "2.25-10-20T12:43:01.684Z",
        "slug": "aiims-exam",
        "variable_mark_per_question": false,
        "show_answers": true
      },
      "user": "testpress",
      "date": "2.25-11-07T06:17:42.313Z",
      "total_questions": 200,
      "score": "0.00",
      "review_url": "http://demo.testpress.in/api/v2.2/attempts/125872/review/",
      "questions_url": "http://demo.testpress.in/api/v2.2/attempts/125872/questions/",
      "percentile": 60,
      "correct_count": 0,
      "incorrect_count": 0,
      "last_started_time": "2.25-11-07T06:17:42.375Z",
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

`GET /api/v2.2/attempts/`

### Query Parameters

Parameter | Type | Description
--------- | ------- | -----------
course | string | Filters by course name. Ex: IBPS
q | string | Filters by exam title. Useful to search by exam title.

## Get all attempts of an exam

```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.2/exams/mathjax-sample-exam/attempts/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw'
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body

```

```python
import requests

url = "http://demo.testpress.in/api/v2.2/exams/mathjax-sample-exam/attempts/"

headers = {
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw",
    'cache-control': "no-cache"
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```shell
curl --request GET \
  --url http://demo.testpress.in/api/v2.2/exams/mathjax-sample-exam/attempts/ \
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
      "url": "http://demo.testpress.in/api/v2.2/attempts/369/",
      "id": 369,
      "user": {
        "id": 5,
        "url": "http://demo.testpress.in/api/v2.2/users/5/",
        "username": "demouser",
        "display_name": "DemoUser is my name eeeeee123456789012345678901234",
        "first_name": "DemoUser is my name eeeeee123456789012345678901234",
        "last_name": "",
        "photo": "https://media.testpress.in/i/bc194c3b0f3241ad9473edf949de3cec.jpeg",
        "large_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/459b2af2355549dc8d7f411553128903.jpeg",
        "medium_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/05c3efc7e4e3454ebad1c32c0c69297c.jpeg",
        "medium_small_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/ca7ae15e26cc4586ae5f98750c2acc62.jpeg",
        "small_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/33936fd431e14a9ab54d7e24e70bf301.jpeg",
        "x_small_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/673ceb6e18b343318fba39279ef07594.jpeg",
        "mini_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/3214f5359ad247d1b2e38609376af72b.jpeg"
      },
      "date": "2017-04-25T14:34:26.848Z",
      "total_questions": 25,
      "score": "0.00",
      "review_pdf_url": "",
      "review_url": "http://demo.testpress.in/api/v2.2/attempts/369/review/",
      "questions_url": "http://demo.testpress.in/api/v2.2/attempts/369/questions/",
      "percentile": 0,
      "correct_count": 0,
      "incorrect_count": 0,
      "last_started_time": "2017-05-11T12:26:08.889Z",
      "remaining_time": "1:09:31",
      "time_taken": "1:50:29",
      "state": "Running",
      "rank": 2,
      "max_rank": 165,
      "percentage": "0",
      "unanswered_count": 0,
      "rank_enabled": true,
      "sections": [],
      "speed": 0,
      "accuracy": 0
    },
    {
      "url": "http://demo.testpress.in/api/v2.2/attempts/12/",
      "id": 12,
      "user": {
        "id": 5,
        "url": "http://demo.testpress.in/api/v2.2/users/5/",
        "username": "demouser",
        "display_name": "DemoUser is my name eeeeee123456789012345678901234",
        "first_name": "DemoUser is my name eeeeee123456789012345678901234",
        "last_name": "",
        "photo": "https://media.testpress.in/i/bc194c3b0f3241ad9473edf949de3cec.jpeg",
        "large_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/459b2af2355549dc8d7f411553128903.jpeg",
        "medium_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/05c3efc7e4e3454ebad1c32c0c69297c.jpeg",
        "medium_small_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/ca7ae15e26cc4586ae5f98750c2acc62.jpeg",
        "small_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/33936fd431e14a9ab54d7e24e70bf301.jpeg",
        "x_small_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/673ceb6e18b343318fba39279ef07594.jpeg",
        "mini_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/3214f5359ad247d1b2e38609376af72b.jpeg"
      },
      "date": "2017-01-24T06:33:09.230Z",
      "total_questions": 16,
      "score": "3.00",
      "review_pdf_url": "",
      "review_url": "http://demo.testpress.in/api/v2.2/attempts/12/review/",
      "questions_url": "http://demo.testpress.in/api/v2.2/attempts/12/questions/",
      "percentile": 83.64,
      "correct_count": 0,
      "incorrect_count": 0,
      "last_started_time": "2017-01-24T06:33:51.754Z",
      "remaining_time": "2:59:17",
      "time_taken": "0:00:43",
      "state": "Completed",
      "rank": 2,
      "max_rank": 165,
      "percentage": "12",
      "unanswered_count": 0,
      "rank_enabled": true,
      "sections": [],
      "speed": 847,
      "accuracy": 30
    }
  ]
}
```

This endpoint retrieves attempts of a particular exam for the authenticated user.

### HTTP Request

`GET /api/v2.2/exams/<slug>/attempts/`

### URL Parameters

Parameter | Description
--------- | -----------
slug | The unique slug of the exam which attempts need to retrieve

## Get a single attempt

```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.2/attempts/125894/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw'
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://demo.testpress.in/api/v2.2/attempts/125894/"

headers = {
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw",
    'cache-control': "no-cache"
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```shell
curl --request GET \
  --url http://demo.testpress.in/api/v2.2/attempts/125894/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw' \
  --header 'cache-control: no-cache'
```

> The above command returns JSON structured like this:

```json
{
  "url": "http://demo.testpress.in/api/v2.2/attempts/125894/",
  "id": 125894,
  "exam": {
    "url": "http://demo.testpress.in/api/v2.2/exams/forum-ias-rbi-demo/",
    "id": 3720,
    "title": "FORUM IAS RBI DEMO",
    "description": "",
    "course": "TNPSC",
    "start_date": "2.25-11-07T12:37:11+05:30",
    "end_date": "2.25-11-15T12:37:11+05:30",
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
    "created": "2.25-11-07T07:07:41.597Z",
    "slug": "forum-ias-rbi-demo",
    "variable_mark_per_question": false,
    "show_answers": true
  },
  "user": "testpress",
  "date": "2.25-11-07T07:12:49.873Z",
  "total_questions": 200,
  "score": "0.00",
  "review_url": "http://demo.testpress.in/api/v2.2/attempts/125894/review/",
  "questions_url": "http://demo.testpress.in/api/v2.2/attempts/125894/questions/",
  "percentile": 0,
  "correct_count": 0,
  "incorrect_count": 0,
  "last_started_time": "2.25-11-07T08:02:46.845Z",
  "remaining_time": "2.20:03",
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

`GET /api/v2.2/attempts/<id>`

### URL Parameters

Parameter | Description
--------- | -----------
id | The unique id of the attempt to retrieve

## Create an attempt

```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.2/exams/dummy-test-7-8/attempts/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw'
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://demo.testpress.in/api/v2.2/exams/dummy-test-7-8/attempts/"

headers = {
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw",
    'cache-control': "no-cache"
    }

response = requests.request("POST", url, headers=headers)

print(response.text)
```

```shell
curl --request POST \
  --url http://demo.testpress.in/api/v2.2/exams/dummy-test-7-8/attempts/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw' \
  --header 'cache-control: no-cache'
```

> The above command returns JSON structured like this:

```json
{
  "url": "http://demo.testpress.in/api/v2.2/attempts/400/",
  "id": 400,
  "exam_url": "http://demo.testpress.in/api/v2.2/exams/dummy-test-7-8/",
  "user": {
    "id": 5,
    "url": "http://demo.testpress.in/api/v2.2/users/5/",
    "username": "demouser",
    "display_name": "DemoUser is my name eeeeee123456789012345678901234",
    "first_name": "DemoUser is my name eeeeee123456789012345678901234",
    "last_name": "",
    "photo": "https://media.testpress.in/i/bc194c3b0f3241ad9473edf949de3cec.jpeg",
    "large_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/459b2af2355549dc8d7f411553128903.jpeg",
    "medium_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/05c3efc7e4e3454ebad1c32c0c69297c.jpeg",
    "medium_small_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/ca7ae15e26cc4586ae5f98750c2acc62.jpeg",
    "small_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/33936fd431e14a9ab54d7e24e70bf301.jpeg",
    "x_small_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/673ceb6e18b343318fba39279ef07594.jpeg",
    "mini_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/3214f5359ad247d1b2e38609376af72b.jpeg"
  },
  "date": "2017-05-24T07:32:09.891Z",
  "total_questions": 50,
  "score": 0,
  "review_pdf_url": "",
  "review_url": "http://demo.testpress.in/api/v2.2/attempts/400/review/",
  "questions_url": "http://demo.testpress.in/api/v2.2/attempts/400/questions/",
  "percentile": 0,
  "correct_count": 0,
  "incorrect_count": 0,
  "last_started_time": "2017-05-24T07:32:09.921Z",
  "remaining_time": "1:59:59",
  "time_taken": "0:00:01",
  "state": "Running",
  "rank": "NA",
  "max_rank": "NA",
  "percentage": "0",
  "unanswered_count": 0,
  "commented_questions_count": 0,
  "comments_count": 0,
  "total_bonus": 0,
  "rank_enabled": false,
  "exam": {
    "url": "http://demo.testpress.in/api/v2.2/exams/dummy-test-7-8/",
    "id": 31,
    "title": "Dummy Test 7",
    "description": "",
    "start_date": "2017-03-30T18:58:53+07:00",
    "end_date": null,
    "duration": "2:00:00",
    "number_of_questions": 50,
    "negative_marks": "0.00",
    "mark_per_question": "1.00",
    "template_type": 1,
    "allow_retake": true,
    "max_retakes": -1,
    "enable_ranks": false,
    "rank_publishing_date": null,
    "allow_pdf": false,
    "allow_question_pdf": false,
    "created": "2017-03-30T13:29:05.007Z",
    "slug": "dummy-test-7-8",
    "variable_mark_per_question": false,
    "show_answers": true,
    "allow_preemptive_section_ending": false,
    "sections": [
      {
        "order": 0,
        "name": "",
        "duration": "2:00:00",
        "cut_off": 0
      }
    ],
    "immediate_feedback": false,
    "categories": []
  },
  "sections": [],
  "speed": 0,
  "accuracy": 0,
  "institute_attempt_id": null
}
```

This endpoint create new attempt of a exam.

### HTTP Request

`POST /api/v2.2/exams/<exam_slug>/attempts/`

### URL Parameters

Parameter | Description
--------- | -----------
exam_slug | The unique slug of the exam to which the attempt need to create

## Resume an attempt

```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.2/attempts/125894/start/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw'
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://demo.testpress.in/api/v2.2/attempts/125894/start/"

headers = {
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw",
    'cache-control': "no-cache"
    }

response = requests.request("PUT", url, headers=headers)

print(response.text)
```

```shell
curl --request PUT \
  --url http://demo.testpress.in/api/v2.2/attempts/125894/start/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw' \
  --header 'cache-control: no-cache'
```

> The above command returns JSON structured like this:

```json
{
  "url": "http://demo.testpress.in/api/v2.2/attempts/125894/",
  "id": 125894,
  "exam": {
    "url": "http://demo.testpress.in/api/v2.2/exams/forum-ias-rbi-demo/",
    "id": 3720,
    "title": "FORUM IAS RBI DEMO",
    "description": "",
    "course": "TNPSC",
    "start_date": "2.25-11-07T12:37:11+05:30",
    "end_date": "2.25-11-15T12:37:11+05:30",
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
    "created": "2.25-11-07T07:07:41.597Z",
    "slug": "forum-ias-rbi-demo",
    "variable_mark_per_question": false,
    "show_answers": true
  },
  "user": "testpress",
  "date": "2.25-11-07T07:12:49.873Z",
  "total_questions": 200,
  "score": "0.00",
  "review_url": "http://demo.testpress.in/api/v2.2/attempts/125894/review/",
  "questions_url": "http://demo.testpress.in/api/v2.2/attempts/125894/questions/",
  "percentile": 0,
  "correct_count": 0,
  "incorrect_count": 0,
  "last_started_time": "2.25-11-18T09:50:20.287Z",
  "remaining_time": "2.20:03",
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

`PUT /api/v2.2/attempts/<id>/start/`

### URL Parameters

Parameter | Description
--------- | -----------
id | The unique id of the attempt to retrieve

## Send heart beat

```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.2/attempts/400/heartbeat/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw'
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://demo.testpress.in/api/v2.2/attempts/400/heartbeat/"

headers = {
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw",
    'cache-control': "no-cache"
    }

response = requests.request("PUT", url, headers=headers)

print(response.text)
```

```shell
curl --request PUT \
  --url http://demo.testpress.in/api/v2.2/attempts/400/heartbeat/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw' \
  --header 'cache-control: no-cache'
```

> The above command returns JSON structured like this:

```json
{
  "url": "http://demo.testpress.in/api/v2.2/attempts/400/",
  "id": 400,
  "exam_url": "http://demo.testpress.in/api/v2.2/exams/dummy-test-7-8/",
  "user": {
    "id": 5,
    "url": "http://demo.testpress.in/api/v2.2/users/5/",
    "username": "demouser",
    "display_name": "DemoUser is my name eeeeee123456789012345678901234",
    "first_name": "DemoUser is my name eeeeee123456789012345678901234",
    "last_name": "",
    "photo": "https://media.testpress.in/i/bc194c3b0f3241ad9473edf949de3cec.jpeg",
    "large_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/459b2af2355549dc8d7f411553128903.jpeg",
    "medium_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/05c3efc7e4e3454ebad1c32c0c69297c.jpeg",
    "medium_small_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/ca7ae15e26cc4586ae5f98750c2acc62.jpeg",
    "small_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/33936fd431e14a9ab54d7e24e70bf301.jpeg",
    "x_small_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/673ceb6e18b343318fba39279ef07594.jpeg",
    "mini_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/3214f5359ad247d1b2e38609376af72b.jpeg"
  },
  "date": "2017-05-24T07:32:09.891Z",
  "total_questions": 50,
  "score": "0.00",
  "review_pdf_url": "",
  "review_url": "http://demo.testpress.in/api/v2.2/attempts/400/review/",
  "questions_url": "http://demo.testpress.in/api/v2.2/attempts/400/questions/",
  "percentile": 0,
  "correct_count": 0,
  "incorrect_count": 0,
  "last_started_time": "2017-05-24T07:37:10.655Z",
  "remaining_time": "1:54:59",
  "time_taken": "0:05:01",
  "state": "Running",
  "rank": "NA",
  "max_rank": "NA",
  "percentage": "0",
  "unanswered_count": 0,
  "commented_questions_count": 0,
  "comments_count": 0,
  "total_bonus": 0,
  "rank_enabled": false,
  "exam": {
    "url": "http://demo.testpress.in/api/v2.2/exams/dummy-test-7-8/",
    "id": 31,
    "title": "Dummy Test 7",
    "description": "",
    "start_date": "2017-03-30T18:58:53+07:00",
    "end_date": null,
    "duration": "2:00:00",
    "number_of_questions": 50,
    "negative_marks": "0.00",
    "mark_per_question": "1.00",
    "template_type": 1,
    "allow_retake": true,
    "max_retakes": -1,
    "enable_ranks": false,
    "rank_publishing_date": null,
    "allow_pdf": false,
    "allow_question_pdf": false,
    "created": "2017-03-30T13:29:05.007Z",
    "slug": "dummy-test-7-8",
    "variable_mark_per_question": false,
    "show_answers": true,
    "allow_preemptive_section_ending": false,
    "sections": [
      {
        "order": 0,
        "name": "",
        "duration": "2:00:00",
        "cut_off": 0
      }
    ],
    "immediate_feedback": false,
    "categories": []
  },
  "sections": [],
  "speed": 0,
  "accuracy": 0,
  "institute_attempt_id": null
}

```

For every 1 minute this API have to be called when the user attempting an exam to update the remaining time in server.

### HTTP Request

`PUT /api/v2.2/attempts/<id>/heartbeat/`

### URL Parameters

Parameter | Description
--------- | -----------
id | The unique id of the attempt to be update

## End an attempt

```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.2/attempts/125894/end/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw'
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://demo.testpress.in/api/v2.2/attempts/125894/end/"

headers = {
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw",
    'cache-control': "no-cache"
    }

response = requests.request("PUT", url, headers=headers)

print(response.text)
```

```shell
curl --request PUT \
  --url http://demo.testpress.in/api/v2.2/attempts/125894/end/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw' \
  --header 'cache-control: no-cache'
```

> The above command returns JSON structured like this:

```json
{
  "url": "http://demo.testpress.in/api/v2.2/attempts/125894/",
  "id": 125894,
  "exam": {
    "url": "http://demo.testpress.in/api/v2.2/exams/forum-ias-rbi-demo/",
    "id": 3720,
    "title": "FORUM IAS RBI DEMO",
    "description": "",
    "course": "TNPSC",
    "start_date": "2.25-11-07T12:37:11+05:30",
    "end_date": "2.25-11-15T12:37:11+05:30",
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
    "created": "2.25-11-07T07:07:41.597Z",
    "slug": "forum-ias-rbi-demo",
    "variable_mark_per_question": false,
    "show_answers": true
  },
  "user": "testpress",
  "date": "2.25-11-07T07:12:49.873Z",
  "total_questions": 200,
  "score": "2.00",
  "review_url": "http://demo.testpress.in/api/v2.2/attempts/125894/review/",
  "questions_url": "http://demo.testpress.in/api/v2.2/attempts/125894/questions/",
  "percentile": 100,
  "correct_count": 2,
  "incorrect_count": 6,
  "last_started_time": "2.25-11-18T09:50:20.287Z",
  "remaining_time": "2.20:03",
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

`PUT /api/v2.2/attempts/<id>/end/`

### URL Parameters

Parameter | Description
--------- | -----------
id | The unique id of the attempt to be end

## Get attempt questions

```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.2/attempts/122046/questions/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw'
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://demo.testpress.in/api/v2.2/attempts/122046/questions/"

headers = {
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw",
    'cache-control': "no-cache"
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```shell
curl --request GET \
  --url http://demo.testpress.in/api/v2.2/attempts/122046/questions/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw' \
  --header 'cache-control: no-cache'
```

> The above command returns JSON structured like this:

```json
{
  "count": 100,
  "next": "http://demo.testpress.in/api/v2.2/attempts/122046/questions/?page=2",
  "previous": null,
  "per_page": 20,
  "results": [
    {
      "id": 12705318,
      "url": "http://demo.testpress.in/api/v2.2/attempts/122046/questions/12705318/",
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
      "url": "http://demo.testpress.in/api/v2.2/attempts/122046/questions/12705296/",
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

`PUT /api/v2.2/attempts/<id>/questions/`

### URL Parameters

Parameter | Description
--------- | -----------
id | The unique id of the attempt to retrieve

## Update attempt questions

```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.2/attempts/122046/questions/12705318/")

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

url = "http://demo.testpress.in/api/v2.2/attempts/122046/questions/12705318/"

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
  --url http://demo.testpress.in/api/v2.2/attempts/122046/questions/12705318/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw' \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json' \
  --data '{\n"selected_answers": [129, 130],\n"review": true\n}'
```

> The above command returns JSON structured like this:

```json
{
  "id": 12705318,
  "url": "http://demo.testpress.in/api/v2.2/attempts/122046/questions/12705318/",
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

`PUT /api/v2.2/attempts/<id>/questions/<question_id>`

### URL Parameters

Parameter | Description
--------- | -----------
id | The unique id of the attempt
question_id | The unique id of the attempt question

## Review attempt questions

```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.2/attempts/122046/review/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw'
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://demo.testpress.in/api/v2.2/attempts/122046/review/"

headers = {
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw",
    'cache-control': "no-cache"
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```shell
curl --request GET \
  --url http://demo.testpress.in/api/v2.2/attempts/122046/review/ \
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
      "id": 52,
      "url": "http://demo.testpress.in/api/v2.2/attempts/12/review/52/",
      "order": 0,
      "question": {
        "id": 2,
        "url": "http://demo.testpress.in/api/v2.2/questions/2/",
        "question_html": "<p>Pick similar things</p>\n",
        "direction": null,
        "answers": [
          {
            "id": 3,
            "text_html": "<p>ComputerComputer</p>\n",
            "is_correct": true
          },
          {
            "id": 4,
            "text_html": "<p>Mouse Mouse Mouse</p>\n",
            "is_correct": true
          },
          {
            "id": 5,
            "text_html": "<p>Table</p>\n",
            "is_correct": false
          },
          {
            "id": 6,
            "text_html": "<p>CPU</p>\n",
            "is_correct": true
          }
        ],
        "essay_topics": [],
        "subject": "General Knowledge",
        "explanation_html": "",
        "type": "C",
        "comments_url": "http://demo.testpress.in/api/v2.2/questions/2/comments/",
        "marks": "1.00",
        "negative_marks": "0.00"
      },
      "duration": "NA",
      "best_duration": 0.61,
      "average_duration": 17.31,
      "selected_answers": [],
      "essay_text": null,
      "essay_topic": null,
      "review": null,
      "comments_count": 0,
      "correct_percentage": 25
    },
    {
      "id": 53,
      "url": "http://demo.testpress.in/api/v2.2/attempts/12/review/53/",
      "order": 0,
      "question": {
        "id": 3,
        "url": "http://demo.testpress.in/api/v2.2/questions/3/",
        "question_html": "<p>Odd one out</p>\n",
        "direction": null,
        "answers": [
          {
            "id": 7,
            "text_html": "<p>Table Table Table</p>\n",
            "is_correct": false
          },
          {
            "id": 8,
            "text_html": "<p>TreeTreeTree</p>\n",
            "is_correct": true
          },
          {
            "id": 9,
            "text_html": "<p>Book</p>\n",
            "is_correct": false
          },
          {
            "id": 10,
            "text_html": "<p>Water Bottle</p>\n",
            "is_correct": false
          }
        ],
        "essay_topics": [],
        "subject": "General Knowledge",
        "explanation_html": "",
        "type": "R",
        "comments_url": "http://demo.testpress.in/api/v2.2/questions/3/comments/",
        "marks": "1.00",
        "negative_marks": "0.00"
      },
      "duration": 1,
      "best_duration": 0.67,
      "average_duration": 11.3,
      "selected_answers": [
        8
      ],
      "essay_text": null,
      "essay_topic": null,
      "review": false,
      "comments_count": 0,
      "correct_percentage": 16
    }
  ]
}

```

This endpoint returns all questions for an attempt with correct answer & explanation.

<aside class="danger">This API will work only if the attempt is in <code>Completed</code> state.</aside>

### HTTP Request

`GET /api/v2.2/attempts/<id>/review/`

### URL Parameters

Parameter | Description
--------- | -----------
id | The unique id of the attempt which questions need to retrieve

## Attempt subject wise analytics

```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.2/attempts/377/review/subjects/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw'
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://demo.testpress.in/api/v2.2/attempts/377/review/subjects/"

headers = {
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw",
    'cache-control': "no-cache"
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```shell
curl --request GET \
  --url http://demo.testpress.in/api/v2.2/attempts/377/review/subjects/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw' \
  --header 'cache-control: no-cache'
```

> The above command returns JSON structured like this:

```json
{
  "count": 6,
  "next": null,
  "previous": null,
  "per_page": 200,
  "results": [
    {
      "id": 20,
      "name": "PSM",
      "total": 2,
      "correct": 0,
      "unanswered": 0,
      "incorrect": 2,
      "parent": null,
      "leaf": true,
      "score": "-2.00"
    },
    {
      "id": 17,
      "name": "Microbiology",
      "total": 1,
      "correct": 1,
      "unanswered": 0,
      "incorrect": 0,
      "parent": null,
      "leaf": true,
      "score": "4.00"
    }
  ]
}

```

This endpoint returns subject wise analytics of the attempt.

<aside class="danger">This API will work only if the attempt is in <code>Completed</code> state.</aside>

### HTTP Request

`GET /api/v2.2/attempts/<id>/review/subjects/`

### URL Parameters

Parameter | Description
--------- | -----------
id | The unique id of the attempt which analytics need to retrieve
