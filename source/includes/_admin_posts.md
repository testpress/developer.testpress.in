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


