# Users
Users API gives you access to get basic information about other users present in the institute.

<aside class="info">This endpoint protects the privacy of users. It is <strong>NOT</strong> possible to extract personal details of all the users from this endpoint. An admin however can extract the personal details using the Admin APIs.</aside>

## Get current authenticated user

```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.2/me/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw'
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://demo.testpress.in/api/v2.2/me/"

headers = {
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw",
    'cache-control': "no-cache"
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```shell
curl --request GET \
  --url http://demo.testpress.in/api/v2.2/me/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw' \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("http://demo.testpress.in/api/v2.2/me/");
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
    "OHC 2.23",
    "st std A",
    "IBPS Morning Batch",
    "UPSC Morning  Batch",
    "NEET Morning Batch",
    "IBPS Online Batch",
    "UPSC Evening Batch"
  ],
  "url": "http://demo.testpress.in/api/v2.2/users/17/",
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

`GET /api/v2.2/me/`

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

url = URI("http://demo.testpress.in/api/v2.2/users/18/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw'
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://demo.testpress.in/api/v2.2/users/18/"

headers = {
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw",
    'cache-control': "no-cache"
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```shell
curl --request GET \
  --url http://demo.testpress.in/api/v2.2/users/18/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw' \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("http://demo.testpress.in/api/v2.2/users/18/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "id": 18,
  "url": "http://demo.testpress.in/api/v2.2/users/18/",
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

<aside class="info">This endpoint protects the privacy of users. If the requested user is same as authenticated user, then the response will be same as <code>/api/v2.2/me/</code>. Otherwise, personal contact details will not be available.</aside>

### HTTP Request

`GET /api/v2.2/users/<id>`

### URL Parameters

Parameter | Description
--------- | -----------
id | The unique id of the user to retrieve

## Update current user

```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.2/users/17/")

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

url = "http://demo.testpress.in/api/v2.2/users/17/"

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
  --url http://demo.testpress.in/api/v2.2/users/17/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw' \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json' \
  --data '{\n    "first_name": "John",\n    "last_name": "Appleseed"\n}'
```

```csharp
var client = new RestClient("http://demo.testpress.in/api/v2.2/users/17/");
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

`PUT /api/v2.2/users/<id>`

### URL Parameters

Parameter | Description
--------- | -----------
id | The unique id of the user to retrieve


