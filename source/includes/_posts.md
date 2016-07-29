# Posts

Posts are broadcast data which the institutes want to share to their users. This endpoint can be used to retrieve the posts which are accessible to a particular user.

## Get all posts
```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.2/posts/")

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

url = "http://demo.testpress.in/api/v2.2/posts/"

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
  --url http://demo.testpress.in/api/v2.2/posts/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw' \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json'
```

```csharp
var client = new RestClient("http://demo.testpress.in/api/v2.2/posts/");
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
  "next": "http://demo.testpress.in/api/v2.2/posts/?page=2",
  "previous": null,
  "per_page": 20,
  "results": [
    {
      "url": "http://demo.testpress.in/api/v2.2/posts/post-title2/",
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
      "created": "2.25-10-15T15:24:34Z",
      "modified": "2.25-10-15T15:24:34Z",
      "id": 33,
      "active": true,
      "title": "Post Title2",
      "summary": "summary goes here",
      "institute": 1
    },
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
      "institute": 1
    }
  ]
}
```

This endpoint retrieves all posts for the authenticated user.

### HTTP Request

`GET /api/v2.2/posts/`

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

url = URI("http://demo.testpress.in/api/v2.2/posts/working-great/")

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

url = "http://demo.testpress.in/api/v2.2/posts/working-great/"

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
  --url http://demo.testpress.in/api/v2.2/posts/working-great/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw' \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json'
```

```csharp
var client = new RestClient("http://demo.testpress.in/api/v2.2/posts/working-great/");
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


