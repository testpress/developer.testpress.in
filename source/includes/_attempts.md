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

## Start an attempt

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
id | The unique id of the attempt to retrieve

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

## Modify attempt questions

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

`GET /api/v2.2/attempts/<id>/questions/`

### URL Parameters

Parameter | Description
--------- | -----------
id | The unique id of the attempt to retrieve


