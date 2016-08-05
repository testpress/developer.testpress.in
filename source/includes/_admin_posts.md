# Posts

Posts are broadcast data which the institutes want to share to their users. This endpoint can be used to retrieve the posts created in your institute

## Get all posts
```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.2/admin/posts/")

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

url = "http://demo.testpress.in/api/v2.2/admin/posts/"

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
  --url http://demo.testpress.in/api/v2.2/admin/posts/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw' \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json'
```

```csharp
var client = new RestClient("http://demo.testpress.in/api/v2.2/admin/posts/");
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
    "next": null, 
    "previous": null, 
    "per_page": 20, 
    "results": [
        {
            "url": "http://demo.testpress.in/api/v2.2/admin/posts/sbbj-recruitment-20152016-sbbjbankcom-various-jobs-advt-apply-online/", 
            "created_by": {
                "id": 16, 
                "url": "http://demo.testpress.in/api/v2.2/users/16/", 
                "username": "bharath", 
                "display_name": "Bharath Kumar S", 
                "first_name": "Bharath Kumar", 
                "last_name": "S", 
                "photo": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/cb88287098924bd6ae615ca4aa71eab5.png", 
                "large_image": "", 
                "medium_image": "", 
                "small_image": "", 
                "x_small_image": "", 
                "mini_image": "", 
                "state": "", 
                "state_code": "", 
                "gender": "Male", 
                "gender_code": "male"
            }, 
            "category": {
                "id": 1, 
                "name": "Alerts", 
                "color": "FF0000", 
                "slug": "alerts", 
                "is_starred": false
            }, 
            "created": "2015-09-24T10:00:16.609Z", 
            "modified": "2016-06-04T16:09:59.446Z", 
            "id": 1, 
            "is_active": true, 
            "title": "SBBJ Recruitment 2015\u20132016 sbbjbank.com Various Jobs Advt Apply Online", 
            "summary": "SBBJ Recruitment 2015\u20132016 sbbjbank.com Various Jobs Advt Apply Online\r\n", 
            "batches": [
                {
                    "id": 17, 
                    "name": "ECE", 
                    "url": "http://demo.testpress.in/api/v2.2/admin/batches/17/"
                }, 
                {
                    "id": 16, 
                    "name": "EEE", 
                    "url": "http://demo.testpress.in/api/v2.2/admin/batches/16/"
                }
            ], 
            "products": [], 
            "is_public": false, 
            "published_date": "2016-06-04T16:09:59.431Z"
        }, 
        {
            "url": "http://demo.testpress.in/api/v2.2/admin/posts/sbi-recruitment-2015-2016-wwwsbicoin-manager-job-notification-online/", 
            "created_by": {
                "id": 16, 
                "url": "http://demo.testpress.in/api/v2.2/users/16/", 
                "username": "bharath", 
                "display_name": "Bharath Kumar S", 
                "first_name": "Bharath Kumar", 
                "last_name": "S", 
                "photo": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/cb88287098924bd6ae615ca4aa71eab5.png", 
                "large_image": "", 
                "medium_image": "", 
                "small_image": "", 
                "x_small_image": "", 
                "mini_image": "", 
                "state": "", 
                "state_code": "", 
                "gender": "Male", 
                "gender_code": "male"
            }, 
            "category": {
                "id": 1, 
                "name": "Alerts", 
                "color": "FF0000", 
                "slug": "alerts", 
                "is_starred": false
            }, 
            "created": "2015-09-24T13:45:38.374Z", 
            "modified": "2016-06-04T16:09:59.664Z", 
            "id": 2, 
            "is_active": true, 
            "title": "SBI Recruitment 2015-2016 www.sbi.co.in Manager Job Notification Online", 
            "summary": "State Bank of India has unfolded a job notification of SBI Recruitment. Organization requires confident and responsible contenders for filling up the vacancies of Deputy General Manager (Law) Post....", 
            "batches": [
                {
                    "id": 17, 
                    "name": "ECE", 
                    "url": "http://demo.testpress.in/api/v2.2/admin/batches/17/"
                }, 
                {
                    "id": 16, 
                    "name": "EEE", 
                    "url": "http://demo.testpress.in/api/v2.2/admin/batches/16/"
                }
            ], 
            "products": [], 
            "is_public": false, 
            "published_date": "2016-06-04T16:09:59.656Z"
        }
    ]
}

```
This endpoint retrieves all posts created by your institute admins

### HTTP Request

`GET /api/v2.2/admin/posts/`

## Get single post

```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.2/admin/posts/working-great/")

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

url = "http://demo.testpress.in/api/v2.2/admin/posts/working-great/"

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
  --url http://demo.testpress.in/api/v2.2/admin/posts/working-great/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw' \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json'
```

```csharp
var client = new RestClient("http://demo.testpress.in/api/v2.2/admin/posts/working-great/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json");
request.AddHeader("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "url": "http://demo.testpress.in/api/v2.2/posts/working-great/",
  "created_by": {
    "id": 10,
    "url": "http://demo.testpress.in/api/v2.2/users/10/",
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
  "created": "2.25-10-07T06:00:07Z",
  "modified": "2.25-10-07T06:00:07Z",
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

`GET /api/v2.2/posts/<slug>`

### URL Parameters

Parameter | Description
--------- | -----------
slug | The unique slug of the post to retrieve

##Create a post 
```ruby
re 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.2/admin/posts/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzODY4NTV9.5w4InsvTPtQGgj4L1myQGc1qxw7IvNEpa3BtVfQOtxE'
request["content-type"] = 'application/json'
request["cache-control"] = 'no-cache'
request["postman-token"] = '653bbc93-696f-e194-caa5-21b5e2a736b7'
request.body = "{\n    \"title\": \"NCRA Recruitment 2015 www.ncra.tifr.res.in JRF Vacancies Apply Online\", \n    \"summary\": \"Test Summary\", \n    \"content_html\": \"<h2><strong>NCRA Recruitment</strong></h2> <p>National Centre for Radio Astrophysics, Pune has emitted an advertisement related to <strong>NCRA Recruitment</strong>. The organization is willing to hire self-motivated and expert candidates against vacancies of Junior Research Fellow (JRF) Post. Job Seekers who fulfill the eligibility criteria can apply against NCRA Recruitment 2015 by following online process. Job seekers who are eagerly waiting for jobs in this organization may apply against these Openings as soon as possible. Aspirants need to submit application form in proper manner on or prior to end date that is represented below.</p>\", \n    \"batches\": [\n        \"Online Test Batch\"\n    ], \n    \"products\": [\n        \"IAS Prelims Power Pack\"\n    ], \n    \"is_public\": false, \n    \"category\": \"Alerts\", \n    \"published_date\": \"2016-08-05T09:17:56.883Z\"\n}"

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://demo.testpress.in/api/v2.2/admin/posts/"

payload = "{\n    \"title\": \"NCRA Recruitment 2015 www.ncra.tifr.res.in JRF Vacancies Apply Online\", \n    \"summary\": \"Test Summary\", \n    \"content_html\": \"<h2><strong>NCRA Recruitment</strong></h2> <p>National Centre for Radio Astrophysics, Pune has emitted an advertisement related to <strong>NCRA Recruitment</strong>. The organization is willing to hire self-motivated and expert candidates against vacancies of Junior Research Fellow (JRF) Post. Job Seekers who fulfill the eligibility criteria can apply against NCRA Recruitment 2015 by following online process. Job seekers who are eagerly waiting for jobs in this organization may apply against these Openings as soon as possible. Aspirants need to submit application form in proper manner on or prior to end date that is represented below.</p>\", \n    \"batches\": [\n        \"Online Test Batch\"\n    ], \n    \"products\": [\n        \"IAS Prelims Power Pack\"\n    ], \n    \"is_public\": false, \n    \"category\": \"Alerts\", \n    \"published_date\": \"2016-08-05T09:17:56.883Z\"\n}"
headers = {
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzODY4NTV9.5w4InsvTPtQGgj4L1myQGc1qxw7IvNEpa3BtVfQOtxE",
    'content-type': "application/json",
    'cache-control': "no-cache",
    'postman-token': "8a880552-d0f7-f2f8-be8f-dab095c4f24c"
    }

response = requests.request("POST", url, data=payload, headers=headers)

print(response.text)
```

```shell
curl -X POST -H "Authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzODY4NTV9.5w4InsvTPtQGgj4L1myQGc1qxw7IvNEpa3BtVfQOtxE" -H "Content-Type: application/json" -H "Cache-Control: no-cache" -H "Postman-Token: ababd89e-d515-7bca-b2a5-2a99a5a15d6d" -d '{
    "title": "NCRA Recruitment 2015 www.ncra.tifr.res.in JRF Vacancies Apply Online", 
    "summary": "Test Summary", 
    "content_html": "<h2><strong>NCRA Recruitment</strong></h2> <p>National Centre for Radio Astrophysics, Pune has emitted an advertisement related to <strong>NCRA Recruitment</strong>. The organization is willing to hire self-motivated and expert candidates against vacancies of Junior Research Fellow (JRF) Post. Job Seekers who fulfill the eligibility criteria can apply against NCRA Recruitment 2015 by following online process. Job seekers who are eagerly waiting for jobs in this organization may apply against these Openings as soon as possible. Aspirants need to submit application form in proper manner on or prior to end date that is represented below.</p>", 
    "batches": [
        "Online Test Batch"
    ], 
    "products": [
        "IAS Prelims Power Pack"
    ], 
    "is_public": false, 
    "category": "Alerts", 
    "published_date": "2016-08-05T09:17:56.883Z"
}' "http://demo.testpress.in/api/v2.2/admin/posts/"
```

```csharp
var client = new RestClient("http://demo.testpress.in/api/v2.2/admin/posts/");
var request = new RestRequest(Method.POST);
request.AddHeader("postman-token", "e837fb2b-c7c2-c3de-f9ba-d05fc084da77");
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json");
request.AddHeader("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzODY4NTV9.5w4InsvTPtQGgj4L1myQGc1qxw7IvNEpa3BtVfQOtxE");
request.AddParameter("application/json", "{\n    \"title\": \"NCRA Recruitment 2015 www.ncra.tifr.res.in JRF Vacancies Apply Online\", \n    \"summary\": \"Test Summary\", \n    \"content_html\": \"<h2><strong>NCRA Recruitment</strong></h2> <p>National Centre for Radio Astrophysics, Pune has emitted an advertisement related to <strong>NCRA Recruitment</strong>. The organization is willing to hire self-motivated and expert candidates against vacancies of Junior Research Fellow (JRF) Post. Job Seekers who fulfill the eligibility criteria can apply against NCRA Recruitment 2015 by following online process. Job seekers who are eagerly waiting for jobs in this organization may apply against these Openings as soon as possible. Aspirants need to submit application form in proper manner on or prior to end date that is represented below.</p>\", \n    \"batches\": [\n        \"Online Test Batch\"\n    ], \n    \"products\": [\n        \"IAS Prelims Power Pack\"\n    ], \n    \"is_public\": false, \n    \"category\": \"Alerts\", \n    \"published_date\": \"2016-08-05T09:17:56.883Z\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);

```

> The above command returns JSON structured like this:

```json
{
  "url": "http://demo.testpress.in/api/v2.2/admin/posts/ncra-recruitment-2015-wwwncratifrresin-jrf-vacancies-apply-online-14/",
  "created_by": {
    "id": 38,
    "url": "http://demo.testpress.in/api/v2.2/users/38/",
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
    "id": 1,
    "name": "Alerts",
    "color": "FF0000",
    "slug": "alerts",
    "is_starred": false
  },
  "created": "2016-08-05T11:56:55.902Z",
  "modified": "2016-08-05T11:56:55.940Z",
  "id": 116,
  "is_active": true,
  "title": "NCRA Recruitment 2015 www.ncra.tifr.res.in JRF Vacancies Apply Online",
  "summary": "Test Summary",
  "batches": [
    {
      "id": 34,
      "name": "Online Test Batch",
      "url": "http://demo.testpress.in/api/v2.2/admin/batches/34/"
    }
  ],
  "products": [
    {
      "id": 5,
      "url": "http://demo.testpress.in/api/v2.2/products/ias-prelims-power-pack/",
      "title": "IAS Prelims Power Pack",
      "slug": "ias-prelims-power-pack",
      "image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/c098795970e64bbab0265e82c4a40f6a.png",
      "images": [
        {
          "original": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/c098795970e64bbab0265e82c4a40f6a.png",
          "medium": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/2c5648e2884e481aa4256554ad601d66.png",
          "small": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/a36d18c340c84e8eaa24d17697b1cb88.png"
        }
      ],
      "start_date": "2015-01-01T00:00:00+05:30",
      "end_date": "2019-01-01T00:00:00+05:30",
      "categories": [
        "TNPSC"
      ],
      "types": [
        "Exams",
        "Books"
      ],
      "exams_count": 1,
      "notes_count": 4,
      "price": "1.00"
    }
  ],
  "is_public": false,
  "published_date": "2016-08-05T09:17:56.883Z"
}
```
This endpoint creates a post for a batch / product in the given category

### HTTP Request

`POST /api/v2.2/admin/posts/`

### Fields

Name | Type | Description
-----|------|-------------
title | string | Post Title
summary | string | Summary of post
content_html | string | Content of the post
batches | array of strings | Pass as array of batch name strings.
products | array of strings | Pass as array of product name strings
is_public | Boolean | Is this a public post. True or False
category | string | Category of the post.

