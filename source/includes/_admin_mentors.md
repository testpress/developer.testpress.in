# Mentors
Admin Mentors API gives you access to create/view mentors and add/remove students to mentors.

## Create mentor

```shell
curl --request POST \
  --url http://demo.testpress.in/api/v2.2/admin/mentors/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6InN0ZWVwaGFuc2VsdmFyYWpAdGVzdHByZXNzLmluIiwiZXhwIjoxNDc1MDYyMTkwfQ.iwVg_UM4HBB6qs21fe2b6FlNz_JjRfqcs2VTML4Te3k' \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json' \
  --header 'postman-token: 9624f4b4-d495-aaaa-df27-b99f0cef13b4' \
  --data '{\n    "username": "Georgebobby", \n    "password":"password",\n    "first_name": "George", \n    "last_name": "Bobby", \n    "email": "george@hotmail.com", \n    "birth_date": "03/07/1990", \n    "gender_code": "1", \n    "address1": "21 New Street", \n    "address2": "Chrompet", \n    "city": "Chennai", \n    "zip": "641003", \n    "state_code": "IN-TN", \n    "phone": "9876543210"\n}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.2/admin/mentors/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6InN0ZWVwaGFuc2VsdmFyYWpAdGVzdHByZXNzLmluIiwiZXhwIjoxNDc1MDYyMTkwfQ.iwVg_UM4HBB6qs21fe2b6FlNz_JjRfqcs2VTML4Te3k'
request["content-type"] = 'application/json'
request["cache-control"] = 'no-cache'
request["postman-token"] = '02729f65-07a8-b865-41cd-09fd9281a489'
request.body = "{\n    \"username\": \"Georgebobby\", \n    \"password\":\"password\",\n    \"first_name\": \"George\", \n    \"last_name\": \"Bobby\", \n    \"email\": \"george@hotmail.com\", \n    \"birth_date\": \"03/07/1990\", \n    \"gender_code\": \"1\", \n    \"address1\": \"21 New Street\", \n    \"address2\": \"Chrompet\", \n    \"city\": \"Chennai\", \n    \"zip\": \"641003\", \n    \"state_code\": \"IN-TN\", \n    \"phone\": \"9876543210\"\n}"

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://demo.testpress.in/api/v2.2/admin/mentors/"

payload = "{\n    \"username\": \"Georgebobby\", \n    \"password\":\"password\",\n    \"first_name\": \"George\", \n    \"last_name\": \"Bobby\", \n    \"email\": \"george@hotmail.com\", \n    \"birth_date\": \"03/07/1990\", \n    \"gender_code\": \"1\", \n    \"address1\": \"21 New Street\", \n    \"address2\": \"Chrompet\", \n    \"city\": \"Chennai\", \n    \"zip\": \"641003\", \n    \"state_code\": \"IN-TN\", \n    \"phone\": \"9876543210\"\n}"
headers = {
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6InN0ZWVwaGFuc2VsdmFyYWpAdGVzdHByZXNzLmluIiwiZXhwIjoxNDc1MDYyMTkwfQ.iwVg_UM4HBB6qs21fe2b6FlNz_JjRfqcs2VTML4Te3k",
    'content-type': "application/json",
    'cache-control': "no-cache",
    'postman-token': "59e716f0-4dd8-c677-fbfe-89e8672a1b27"
    }

response = requests.request("POST", url, data=payload, headers=headers)

print(response.text)
```

```csharp
var client = new RestClient("http://demo.testpress.in/api/v2.2/admin/mentors/");
var request = new RestRequest(Method.POST);
request.AddHeader("postman-token", "60b37cc0-352b-c122-a41f-31a27db2f08d");
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json");
request.AddHeader("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6InN0ZWVwaGFuc2VsdmFyYWpAdGVzdHByZXNzLmluIiwiZXhwIjoxNDc1MDYyMTkwfQ.iwVg_UM4HBB6qs21fe2b6FlNz_JjRfqcs2VTML4Te3k");
request.AddParameter("application/json", "{\n    \"username\": \"Georgebobby\", \n    \"password\":\"password\",\n    \"first_name\": \"George\", \n    \"last_name\": \"Bobby\", \n    \"email\": \"george@hotmail.com\", \n    \"birth_date\": \"03/07/1990\", \n    \"gender_code\": \"1\", \n    \"address1\": \"21 New Street\", \n    \"address2\": \"Chrompet\", \n    \"city\": \"Chennai\", \n    \"zip\": \"641003\", \n    \"state_code\": \"IN-TN\", \n    \"phone\": \"9876543210\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('http://demo.testpress.in/api/v2.2/admin/mentors/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'postman-token' => '0e6a81e9-0291-ad9a-5e25-a7ab77e950e4',
  'cache-control' => 'no-cache',
  'content-type' => 'application/json',
  'authorization' => 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6InN0ZWVwaGFuc2VsdmFyYWpAdGVzdHByZXNzLmluIiwiZXhwIjoxNDc1MDYyMTkwfQ.iwVg_UM4HBB6qs21fe2b6FlNz_JjRfqcs2VTML4Te3k'
));

$request->setBody('{
    "username": "Georgebobby", 
    "password":"password",
    "first_name": "George", 
    "last_name": "Bobby", 
    "email": "george@hotmail.com", 
    "birth_date": "03/07/1990", 
    "gender_code": "1", 
    "address1": "21 New Street", 
    "address2": "Chrompet", 
    "city": "Chennai", 
    "zip": "641003", 
    "state_code": "IN-TN", 
    "phone": "9876543210"
}');

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```java
OkHttpClient client = new OkHttpClient();

MediaType mediaType = MediaType.parse("application/json");
RequestBody body = RequestBody.create(mediaType, "{\n    \"username\": \"Georgebobby\", \n    \"password\":\"password\",\n    \"first_name\": \"George\", \n    \"last_name\": \"Bobby\", \n    \"email\": \"george@hotmail.com\", \n    \"birth_date\": \"03/07/1990\", \n    \"gender_code\": \"1\", \n    \"address1\": \"21 New Street\", \n    \"address2\": \"Chrompet\", \n    \"city\": \"Chennai\", \n    \"zip\": \"641003\", \n    \"state_code\": \"IN-TN\", \n    \"phone\": \"9876543210\"\n}");
Request request = new Request.Builder()
  .url("http://demo.testpress.in/api/v2.2/admin/mentors/")
  .post(body)
  .addHeader("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6InN0ZWVwaGFuc2VsdmFyYWpAdGVzdHByZXNzLmluIiwiZXhwIjoxNDc1MDYyMTkwfQ.iwVg_UM4HBB6qs21fe2b6FlNz_JjRfqcs2VTML4Te3k")
  .addHeader("content-type", "application/json")
  .addHeader("cache-control", "no-cache")
  .addHeader("postman-token", "cf247a42-9440-685e-dbd6-7ddbf2abc1ea")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var request = require("request");

var options = { method: 'POST',
  url: 'http://demo.testpress.in/api/v2.2/admin/mentors/',
  headers: 
   { 'postman-token': '0c99111c-c13f-eddf-a0bb-0e2eef469765',
     'cache-control': 'no-cache',
     'content-type': 'application/json',
     authorization: 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6InN0ZWVwaGFuc2VsdmFyYWpAdGVzdHByZXNzLmluIiwiZXhwIjoxNDc1MDYyMTkwfQ.iwVg_UM4HBB6qs21fe2b6FlNz_JjRfqcs2VTML4Te3k' },
  body: 
   { username: 'Georgebobby',
     password: 'password',
     first_name: 'George',
     last_name: 'Bobby',
     email: 'george@hotmail.com',
     birth_date: '03/07/1990',
     gender_code: '1',
     address1: '21 New Street',
     address2: 'Chrompet',
     city: 'Chennai',
     zip: '641003',
     state_code: 'IN-TN',
     phone: '9876543210' },
  json: true };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});

```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "http://demo.testpress.in/api/v2.2/admin/mentors/"

	payload := strings.NewReader("{\n    \"username\": \"Georgebobby\", \n    \"password\":\"password\",\n    \"first_name\": \"George\", \n    \"last_name\": \"Bobby\", \n    \"email\": \"george@hotmail.com\", \n    \"birth_date\": \"03/07/1990\", \n    \"gender_code\": \"1\", \n    \"address1\": \"21 New Street\", \n    \"address2\": \"Chrompet\", \n    \"city\": \"Chennai\", \n    \"zip\": \"641003\", \n    \"state_code\": \"IN-TN\", \n    \"phone\": \"9876543210\"\n}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6InN0ZWVwaGFuc2VsdmFyYWpAdGVzdHByZXNzLmluIiwiZXhwIjoxNDc1MDYyMTkwfQ.iwVg_UM4HBB6qs21fe2b6FlNz_JjRfqcs2VTML4Te3k")
	req.Header.Add("content-type", "application/json")
	req.Header.Add("cache-control", "no-cache")
	req.Header.Add("postman-token", "bc7f391f-c86e-08ed-49f0-0f6dcf281628")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

> The above command returns JSON structured like this:

```json
{
  "id": 45,
  "username": "Georgebobby",
  "email": "george@hotmail.com",
  "first_name": "George",
  "last_name": "Bobby",
  "display_name": "George Bobby",
  "gender": "Male",
  "state": "Tamil Nadu",
  "created": "2016-09-28T19:06:18.177Z",
  "students": {
    "url": "http://demo.testpress.in/api/v2.2/admin/mentors/45/students/",
    "students_count": 0
  }
}
```

This endpoint creates a mentor.

### HTTP Request

`POST /api/v2.2/admin/mentors/`

### Fields

Name | Type | Description
-----|------|-------------
username | string | Username of the mentor
password | string | password of the mentor
first_name | string | First name of the mentor
last_name | string | Last name of the mentor
email | string | Email of the mentor
birth_date | datestring | Birth date of mentor. Should be in DD/MM/YYYY format
gender_code | string | Gender of mentor. Can be "male", "female" or "trans"
address1 | string | Address of mentor
address2 | string | Address of mentor
city | string | City of mentor
zip | string | Pincode of mentor
state_code | string | State of mentor in ISO 3166-2:IN format (https://en.wikipedia.org/wiki/ISO_3166-2:IN)
phone | string | Phone of mentor

## View mentors

```shell
curl --request GET \
  --url http://demo.testpress.in/api/v2.2/admin/mentors/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6InN0ZWVwaGFuc2VsdmFyYWpAdGVzdHByZXNzLmluIiwiZXhwIjoxNDc1MDYyMTkwfQ.iwVg_UM4HBB6qs21fe2b6FlNz_JjRfqcs2VTML4Te3k' \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json' \
  --header 'postman-token: 7b270310-b1fe-2434-5f1d-d6a5d4c5db73'
```

```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.2/admin/mentors/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6InN0ZWVwaGFuc2VsdmFyYWpAdGVzdHByZXNzLmluIiwiZXhwIjoxNDc1MDYyMTkwfQ.iwVg_UM4HBB6qs21fe2b6FlNz_JjRfqcs2VTML4Te3k'
request["content-type"] = 'application/json'
request["cache-control"] = 'no-cache'
request["postman-token"] = '67539d2b-a84b-0fc5-93b0-edd440c52eac'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://demo.testpress.in/api/v2.2/admin/mentors/"

payload = ""
headers = {
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6InN0ZWVwaGFuc2VsdmFyYWpAdGVzdHByZXNzLmluIiwiZXhwIjoxNDc1MDYyMTkwfQ.iwVg_UM4HBB6qs21fe2b6FlNz_JjRfqcs2VTML4Te3k",
    'content-type': "application/json",
    'cache-control': "no-cache",
    'postman-token': "8c7a6a33-7a97-bc62-e0bf-bc20d70d5ca1"
    }

response = requests.request("GET", url, data=payload, headers=headers)

print(response.text)
```

```csharp
var client = new RestClient("http://demo.testpress.in/api/v2.2/admin/mentors/");
var request = new RestRequest(Method.GET);
request.AddHeader("postman-token", "b47a7b07-ea80-4e8d-103c-144d2dcf8224");
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json");
request.AddHeader("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6InN0ZWVwaGFuc2VsdmFyYWpAdGVzdHByZXNzLmluIiwiZXhwIjoxNDc1MDYyMTkwfQ.iwVg_UM4HBB6qs21fe2b6FlNz_JjRfqcs2VTML4Te3k");
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('http://demo.testpress.in/api/v2.2/admin/mentors/');
$request->setMethod(HTTP_METH_GET);

$request->setHeaders(array(
  'postman-token' => '4158e1f7-9216-65d7-618f-8c1e1becd02e',
  'cache-control' => 'no-cache',
  'content-type' => 'application/json',
  'authorization' => 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6InN0ZWVwaGFuc2VsdmFyYWpAdGVzdHByZXNzLmluIiwiZXhwIjoxNDc1MDYyMTkwfQ.iwVg_UM4HBB6qs21fe2b6FlNz_JjRfqcs2VTML4Te3k'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("http://demo.testpress.in/api/v2.2/admin/mentors/")
  .get()
  .addHeader("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6InN0ZWVwaGFuc2VsdmFyYWpAdGVzdHByZXNzLmluIiwiZXhwIjoxNDc1MDYyMTkwfQ.iwVg_UM4HBB6qs21fe2b6FlNz_JjRfqcs2VTML4Te3k")
  .addHeader("content-type", "application/json")
  .addHeader("cache-control", "no-cache")
  .addHeader("postman-token", "c28bed97-ec00-8378-ce56-8534eba3daa7")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var request = require("request");

var options = { method: 'GET',
  url: 'http://demo.testpress.in/api/v2.2/admin/mentors/',
  headers: 
   { 'postman-token': 'b236d859-b023-f064-0207-491f9ec1be11',
     'cache-control': 'no-cache',
     'content-type': 'application/json',
     authorization: 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6InN0ZWVwaGFuc2VsdmFyYWpAdGVzdHByZXNzLmluIiwiZXhwIjoxNDc1MDYyMTkwfQ.iwVg_UM4HBB6qs21fe2b6FlNz_JjRfqcs2VTML4Te3k' } };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});

```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "http://demo.testpress.in/api/v2.2/admin/mentors/"

	req, _ := http.NewRequest("GET", url, nil)

	req.Header.Add("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6InN0ZWVwaGFuc2VsdmFyYWpAdGVzdHByZXNzLmluIiwiZXhwIjoxNDc1MDYyMTkwfQ.iwVg_UM4HBB6qs21fe2b6FlNz_JjRfqcs2VTML4Te3k")
	req.Header.Add("content-type", "application/json")
	req.Header.Add("cache-control", "no-cache")
	req.Header.Add("postman-token", "1b0c4aeb-92af-f89a-a3d3-21dcedc3d55b")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

> The above command returns JSON structured like this:

```json
 [
    {
      "id": 44,
      "username": "Steevwilliam",
      "email": "steev@yahoomail.com",
      "first_name": "Steev",
      "last_name": "William",
      "display_name": "Steev William",
      "gender": "Male",
      "state": "Tamil Nadu",
      "created": "2016-09-28T18:44:54.081Z",
      "students": {
        "url": "http://demo.testpress.in/api/v2.2/admin/mentors/44/students/",
        "students_count": 150
      }
    },
    {
      "id": 45,
      "username": "Georgebobby",
      "email": "george@hotmail.com",
      "first_name": "George",
      "last_name": "Bobby",
      "display_name": "George Bobby",
      "gender": "Male",
      "state": "Tamil Nadu",
      "created": "2016-09-28T19:06:18.177Z",
      "students": {
        "url": "http://demo.testpress.in/api/v2.2/admin/mentors/45/students/",
        "students_count": 100
      }
    }
  ]
```

This endpoint allows you to view all the mentors.

### HTTP Request

`GET /api/v2.2/admin/mentors/`

### Response Fields

Name | Type | Description
-----|------|-------------
id   | int  | The mentor unique ID
username  | string | Username of the mentor
first_name  | string | First name of the mentor
last_name  | string | Last name of the mentor
display_name | string | Display name of the mentor
gender | string | Gender of the mentor
state | string | State of the mentor
created | datetimefield | Date and time when mentor created
students | array | Student details.


## View students

```shell
curl --request GET \
  --url http://demo.testpress.in/api/v2.2/admin/mentors/1/students \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6InN0ZWVwaGFuc2VsdmFyYWpAdGVzdHByZXNzLmluIiwiZXhwIjoxNDc1MDYyMTkwfQ.iwVg_UM4HBB6qs21fe2b6FlNz_JjRfqcs2VTML4Te3k' \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json' \
  --header 'postman-token: 14b92c4f-a0ad-fafb-67f4-5dc5d47ae832'
```

```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.2/admin/mentors/1/students")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6InN0ZWVwaGFuc2VsdmFyYWpAdGVzdHByZXNzLmluIiwiZXhwIjoxNDc1MDYyMTkwfQ.iwVg_UM4HBB6qs21fe2b6FlNz_JjRfqcs2VTML4Te3k'
request["content-type"] = 'application/json'
request["cache-control"] = 'no-cache'
request["postman-token"] = 'c7e923f3-3290-928a-29d3-d9f4ae589475'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://demo.testpress.in/api/v2.2/admin/mentors/1/students"

payload = ""
headers = {
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6InN0ZWVwaGFuc2VsdmFyYWpAdGVzdHByZXNzLmluIiwiZXhwIjoxNDc1MDYyMTkwfQ.iwVg_UM4HBB6qs21fe2b6FlNz_JjRfqcs2VTML4Te3k",
    'content-type': "application/json",
    'cache-control': "no-cache",
    'postman-token': "21520f53-8880-2ab4-90b9-c4534e11be8e"
    }

response = requests.request("GET", url, data=payload, headers=headers)

print(response.text)
```

```csharp
var client = new RestClient("http://demo.testpress.in/api/v2.2/admin/mentors/1/students");
var request = new RestRequest(Method.GET);
request.AddHeader("postman-token", "578c57d3-b414-1c0c-5ecc-27ec3809871c");
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json");
request.AddHeader("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6InN0ZWVwaGFuc2VsdmFyYWpAdGVzdHByZXNzLmluIiwiZXhwIjoxNDc1MDYyMTkwfQ.iwVg_UM4HBB6qs21fe2b6FlNz_JjRfqcs2VTML4Te3k");
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('http://demo.testpress.in/api/v2.2/admin/mentors/1/students');
$request->setMethod(HTTP_METH_GET);

$request->setHeaders(array(
  'postman-token' => '4ddf538f-c113-cf40-348e-ae627abc6137',
  'cache-control' => 'no-cache',
  'content-type' => 'application/json',
  'authorization' => 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6InN0ZWVwaGFuc2VsdmFyYWpAdGVzdHByZXNzLmluIiwiZXhwIjoxNDc1MDYyMTkwfQ.iwVg_UM4HBB6qs21fe2b6FlNz_JjRfqcs2VTML4Te3k'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("http://demo.testpress.in/api/v2.2/admin/mentors/1/students")
  .get()
  .addHeader("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6InN0ZWVwaGFuc2VsdmFyYWpAdGVzdHByZXNzLmluIiwiZXhwIjoxNDc1MDYyMTkwfQ.iwVg_UM4HBB6qs21fe2b6FlNz_JjRfqcs2VTML4Te3k")
  .addHeader("content-type", "application/json")
  .addHeader("cache-control", "no-cache")
  .addHeader("postman-token", "62de973a-a5ce-8753-ac75-274ac3e3976c")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var http = require("http");

var options = {
  "method": "GET",
  "hostname": "demo.testpress.in",
  "port": null,
  "path": "/api/v2.2/admin/mentors/1/students",
  "headers": {
    "authorization": "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6InN0ZWVwaGFuc2VsdmFyYWpAdGVzdHByZXNzLmluIiwiZXhwIjoxNDc1MDYyMTkwfQ.iwVg_UM4HBB6qs21fe2b6FlNz_JjRfqcs2VTML4Te3k",
    "content-type": "application/json",
    "cache-control": "no-cache",
    "postman-token": "d6e1e7fc-e06a-e141-5cc2-918fe49c6a71"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.end();
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "http://demo.testpress.in/api/v2.2/admin/mentors/1/students"

	req, _ := http.NewRequest("GET", url, nil)

	req.Header.Add("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6InN0ZWVwaGFuc2VsdmFyYWpAdGVzdHByZXNzLmluIiwiZXhwIjoxNDc1MDYyMTkwfQ.iwVg_UM4HBB6qs21fe2b6FlNz_JjRfqcs2VTML4Te3k")
	req.Header.Add("content-type", "application/json")
	req.Header.Add("cache-control", "no-cache")
	req.Header.Add("postman-token", "baabfe98-3c44-47df-4675-89b353f3b3e4")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

> The above command returns JSON structured like this:

```json
[
    {
      "id": 2,
      "url": "http://demo.testpress.in/api/v2.2/admin/users/2/",
      "username": "testpress",
      "first_name": "John",
      "last_name": "Appleseed",
      "display_name": "John Appleseed",
      "email": "selvasteephandfasdfasdf@gmail.com",
      "photo": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/d1b9192ef434443a963eced9b8747862.jpeg",
      "large_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/2e6f0eb3bc9d467ab4254c094b47611e.jpeg",
      "medium_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/7552ce50dff6479ba172f1102c56e72d.jpeg",
      "small_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/05764a619f09474d93caf0d49a43a4c0.jpeg",
      "x_small_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/5ae9976cc2224e08ab81510404dd8c93.jpeg",
      "mini_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/34d189e496f140b3aa772ee19df46e1b.jpeg",
      "birth_date": "27/08/1994",
      "gender_code": "male",
      "gender": "Male",
      "address1": "Chennai",
      "address2": "Chennai",
      "city": "Chennai",
      "zip": "600069",
      "state": "",
      "state_code": "",
      "phone": "9043570576",
      "batches": [
        {
          "id": 30,
          "name": "Testing Batch 1",
          "url": "http://demo.testpress.in/api/v2.2/admin/batches/30/"
        },
        {
          "id": 29,
          "name": "new sample batch",
          "url": "http://demo.testpress.in/api/v2.2/admin/batches/29/"
        }
      ],
      "batches_url": "http://demo.testpress.in/api/v2.2/admin/users/2/batches/"
    },
    {
      "id": 345,
      "url": "http://demo.testpress.in/api/v2.2/admin/users/345/",
      "username": "hellouser",
      "first_name": "hellouser",
      "last_name": "",
      "display_name": "hellouser",
      "email": "testingsocialauth@gmail.com",
      "photo": null,
      "large_image": "",
      "medium_image": "",
      "small_image": "",
      "x_small_image": "",
      "mini_image": "",
      "birth_date": null,
      "gender_code": null,
      "gender": null,
      "address1": "",
      "address2": "",
      "city": "",
      "zip": "",
      "state": "",
      "state_code": "",
      "phone": "9898989898",
      "batches": [
        {
          "id": 40,
          "name": "Payubatch",
          "url": "http://demo.testpress.in/api/v2.2/admin/batches/40/"
        },
        {
          "id": 29,
          "name": "new sample batch",
          "url": "http://demo.testpress.in/api/v2.2/admin/batches/29/"
        },
        {
          "id": 16,
          "name": "EEE",
          "url": "http://demo.testpress.in/api/v2.2/admin/batches/16/"
        }
      ],
      "batches_url": "http://demo.testpress.in/api/v2.2/admin/users/345/batches/"
    }
]
```

This endpoint allows you to view students of a particular mentor.

### HTTP Request

`GET /api/v2.2/admin/mentors/<:id>/students/`

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the mentor to retrieve

### Response Fields

Name | Type | Description
-----|------|-------------
id | int | Unique Id of the student
username | string | Username of the student
first_name | string | First name of the student
last_name | string | Last name of the student
display_name | string | Name of the student to be displayed
email | string | Email of the student
photo | string | Original image of the student as uploaded
large_image | string | Profile image with size 256x256
medium_image | string | Profile image with size 128x128
small_image | string | Profile image with size 48x48
xsmall_image | string | Profile image with size 32x32
mini_image | string | Profile image with size 24x24
birth_date | datestring | Birth date of student. Should be in DD/MM/YYYY format
gender_code | string | Gender of student. Can be "male", "female" or "trans"
gender | string | (Read only) Human readable gender of student. Can be "Male", "Female" or "Transgender"
address1 | string | Address of student
address2 | string | Address of student
city | string | City of student
zip | string | Pincode of student
state_code | string | State of student in ISO 3166-2:IN format (https://en.wikipedia.org/wiki/ISO_3166-2:IN)
phone | string | Phone of student
batches| array | Batches to which student has access

## Add students

```shell
curl --request POST \
  --url http://demo.testpress.in/api/v2.2/admin/mentors/1/students/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6InN0ZWVwaGFuc2VsdmFyYWpAdGVzdHByZXNzLmluIiwiZXhwIjoxNDc1MDYyMTkwfQ.iwVg_UM4HBB6qs21fe2b6FlNz_JjRfqcs2VTML4Te3k' \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json' \
  --header 'postman-token: 30305f4a-5150-4ff7-5781-30f4ab972452' \
  --data '{ \n    "students_username": [ "john", "ragav"]\n}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.2/admin/mentors/1/students/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6InN0ZWVwaGFuc2VsdmFyYWpAdGVzdHByZXNzLmluIiwiZXhwIjoxNDc1MDYyMTkwfQ.iwVg_UM4HBB6qs21fe2b6FlNz_JjRfqcs2VTML4Te3k'
request["content-type"] = 'application/json'
request["cache-control"] = 'no-cache'
request["postman-token"] = '1cca976b-d71f-613b-42f1-d7bf703edb35'
request.body = "{ \n    \"students_username\": [ \"john\", \"ragav\"]\n}"

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://demo.testpress.in/api/v2.2/admin/mentors/1/students/"

payload = "{ \n    \"students_username\": [ \"john\", \"ragav\"]\n}"
headers = {
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6InN0ZWVwaGFuc2VsdmFyYWpAdGVzdHByZXNzLmluIiwiZXhwIjoxNDc1MDYyMTkwfQ.iwVg_UM4HBB6qs21fe2b6FlNz_JjRfqcs2VTML4Te3k",
    'content-type': "application/json",
    'cache-control': "no-cache",
    'postman-token': "9c4eee2e-3472-3a2e-adc7-70bc448f4c04"
    }

response = requests.request("POST", url, data=payload, headers=headers)

print(response.text)
```

```csharp
var client = new RestClient("http://demo.testpress.in/api/v2.2/admin/mentors/1/students/");
var request = new RestRequest(Method.POST);
request.AddHeader("postman-token", "6c43c51e-a280-50cd-78ba-5685f9db8730");
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json");
request.AddHeader("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6InN0ZWVwaGFuc2VsdmFyYWpAdGVzdHByZXNzLmluIiwiZXhwIjoxNDc1MDYyMTkwfQ.iwVg_UM4HBB6qs21fe2b6FlNz_JjRfqcs2VTML4Te3k");
request.AddParameter("application/json", "{ \n    \"students_username\": [ \"john\", \"ragav\"]\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('http://demo.testpress.in/api/v2.2/admin/mentors/1/students/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'postman-token' => '0ff6afca-b158-a349-172b-f9b4c3f02cec',
  'cache-control' => 'no-cache',
  'content-type' => 'application/json',
  'authorization' => 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6InN0ZWVwaGFuc2VsdmFyYWpAdGVzdHByZXNzLmluIiwiZXhwIjoxNDc1MDYyMTkwfQ.iwVg_UM4HBB6qs21fe2b6FlNz_JjRfqcs2VTML4Te3k'
));

$request->setBody('{ 
    "students_username": [ "john", "ragav"]
}');

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```java
OkHttpClient client = new OkHttpClient();

MediaType mediaType = MediaType.parse("application/json");
RequestBody body = RequestBody.create(mediaType, "{ \n    \"students_username\": [ \"john\", \"ragav\"]\n}");
Request request = new Request.Builder()
  .url("http://demo.testpress.in/api/v2.2/admin/mentors/1/students/")
  .post(body)
  .addHeader("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6InN0ZWVwaGFuc2VsdmFyYWpAdGVzdHByZXNzLmluIiwiZXhwIjoxNDc1MDYyMTkwfQ.iwVg_UM4HBB6qs21fe2b6FlNz_JjRfqcs2VTML4Te3k")
  .addHeader("content-type", "application/json")
  .addHeader("cache-control", "no-cache")
  .addHeader("postman-token", "38897bdf-4b68-bd5c-47a0-688b558d3012")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var http = require("http");

var options = {
  "method": "POST",
  "hostname": "demo.testpress.in",
  "port": null,
  "path": "/api/v2.2/admin/mentors/1/students/",
  "headers": {
    "authorization": "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6InN0ZWVwaGFuc2VsdmFyYWpAdGVzdHByZXNzLmluIiwiZXhwIjoxNDc1MDYyMTkwfQ.iwVg_UM4HBB6qs21fe2b6FlNz_JjRfqcs2VTML4Te3k",
    "content-type": "application/json",
    "cache-control": "no-cache",
    "postman-token": "d8350bb5-db23-fbe7-bd3a-6e5daa8d9ed6"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.write(JSON.stringify({ students_username: [ 'john', 'ragav' ] }));
req.end();
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "http://demo.testpress.in/api/v2.2/admin/mentors/1/students/"

	payload := strings.NewReader("{ \n    \"students_username\": [ \"john\", \"ragav\"]\n}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6InN0ZWVwaGFuc2VsdmFyYWpAdGVzdHByZXNzLmluIiwiZXhwIjoxNDc1MDYyMTkwfQ.iwVg_UM4HBB6qs21fe2b6FlNz_JjRfqcs2VTML4Te3k")
	req.Header.Add("content-type", "application/json")
	req.Header.Add("cache-control", "no-cache")
	req.Header.Add("postman-token", "39860c6a-72fc-ce61-ab91-aa7746a041ff")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 2,
    "url": "http://demo.testpress.in/api/v2.2/admin/users/2/",
    "username": "john",
    "first_name": "John",
    "last_name": "Appleseed",
    "display_name": "John Appleseed",
    "email": "selvasteephandfasdfasdf@gmail.com",
    "photo": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/d1b9192ef434443a963eced9b8747862.jpeg",
    "large_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/2e6f0eb3bc9d467ab4254c094b47611e.jpeg",
    "medium_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/7552ce50dff6479ba172f1102c56e72d.jpeg",
    "small_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/05764a619f09474d93caf0d49a43a4c0.jpeg",
    "x_small_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/5ae9976cc2224e08ab81510404dd8c93.jpeg",
    "mini_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/34d189e496f140b3aa772ee19df46e1b.jpeg",
    "birth_date": "27/08/1994",
    "gender_code": "male",
    "gender": "Male",
    "address1": "Chennai",
    "address2": "Chennai",
    "city": "Chennai",
    "zip": "600069",
    "state": "",
    "state_code": "",
    "phone": "9043570576",
    "batches": [
      {
        "id": 30,
        "name": "Testing Batch 1",
        "url": "http://demo.testpress.in/api/v2.2/admin/batches/30/"
      },
      {
        "id": 29,
        "name": "new sample batch",
        "url": "http://demo.testpress.in/api/v2.2/admin/batches/29/"
      }
    ],
    "batches_url": "http://demo.testpress.in/api/v2.2/admin/users/2/batches/"
  },
  {
    "id": 345,
    "url": "http://demo.testpress.in/api/v2.2/admin/users/345/",
    "username": "ragav",
    "first_name": "ragav",
    "last_name": "",
    "display_name": "ragav",
    "email": "ragav@gmail.com",
    "photo": null,
    "large_image": "",
    "medium_image": "",
    "small_image": "",
    "x_small_image": "",
    "mini_image": "",
    "birth_date": null,
    "gender_code": null,
    "gender": null,
    "address1": "",
    "address2": "",
    "city": "",
    "zip": "",
    "state": "",
    "state_code": "",
    "phone": "9898989898",
    "batches": [
      {
        "id": 40,
        "name": "Payubatch",
        "url": "http://demo.testpress.in/api/v2.2/admin/batches/40/"
      },
      {
        "id": 29,
        "name": "new sample batch",
        "url": "http://demo.testpress.in/api/v2.2/admin/batches/29/"
      },
      {
        "id": 16,
        "name": "EEE",
        "url": "http://demo.testpress.in/api/v2.2/admin/batches/16/"
      }
    ],
    "batches_url": "http://demo.testpress.in/api/v2.2/admin/users/345/batches/"
  }
]
```
This endpoint allows you to add a students to a mentor.

### HTTP Request

`POST /api/v2.2/admin/mentors/<:id>/students`

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the mentor to retrieve

### POST data

Parameter | Description
--------- | ------- | -----------
students_username | Array of students username

### Response Fields

Name | Type | Description
-----|------|-------------
id | int | Unique Id of the student
username | string | Username of the student
first_name | string | First name of the student
last_name | string | Last name of the student
display_name | string | Name of the student to be displayed
email | string | Email of the student
photo | string | Original image of the student as uploaded
large_image | string | Profile image with size 256x256
medium_image | string | Profile image with size 128x128
small_image | string | Profile image with size 48x48
xsmall_image | string | Profile image with size 32x32
mini_image | string | Profile image with size 24x24
birth_date | datestring | Birth date of student. Should be in DD/MM/YYYY format
gender_code | string | Gender of student. Can be "male", "female" or "trans"
gender | string | (Read only) Human readable gender of student. Can be "Male", "Female" or "Transgender"
address1 | string | Address of student
address2 | string | Address of student
city | string | City of student
zip | string | Pincode of student
state_code | string | State of student in ISO 3166-2:IN format (https://en.wikipedia.org/wiki/ISO_3166-2:IN)
phone | string | Phone of student
batches| array | Batches to which student has access

## Remove students

```shell
curl --request DELETE \
  --url http://demo.testpress.in/api/v2.2/admin/mentors/1/students/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6InN0ZWVwaGFuc2VsdmFyYWpAdGVzdHByZXNzLmluIiwiZXhwIjoxNDc1MDYyMTkwfQ.iwVg_UM4HBB6qs21fe2b6FlNz_JjRfqcs2VTML4Te3k' \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json' \
  --header 'postman-token: 7cd40e60-ac91-ddc3-e493-b103a6b0c2e7' \
  --data '{ \n    "students_username": [ "john", "ragav"]\n}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.2/admin/mentors/1/students/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Delete.new(url)
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6InN0ZWVwaGFuc2VsdmFyYWpAdGVzdHByZXNzLmluIiwiZXhwIjoxNDc1MDYyMTkwfQ.iwVg_UM4HBB6qs21fe2b6FlNz_JjRfqcs2VTML4Te3k'
request["content-type"] = 'application/json'
request["cache-control"] = 'no-cache'
request["postman-token"] = '0228eca4-a3af-ed7f-4637-65d4392548c9'
request.body = "{ \n    \"students_username\": [ \"john\", \"ragav\"]\n}"

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://demo.testpress.in/api/v2.2/admin/mentors/1/students/"

payload = "{ \n    \"students_username\": [ \"john\", \"ragav\"]\n}"
headers = {
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6InN0ZWVwaGFuc2VsdmFyYWpAdGVzdHByZXNzLmluIiwiZXhwIjoxNDc1MDYyMTkwfQ.iwVg_UM4HBB6qs21fe2b6FlNz_JjRfqcs2VTML4Te3k",
    'content-type': "application/json",
    'cache-control': "no-cache",
    'postman-token': "a6cc65e9-35bd-d2ab-74c7-82a83bbc50e0"
    }

response = requests.request("DELETE", url, data=payload, headers=headers)

print(response.text)
```

```csharp
var client = new RestClient("http://demo.testpress.in/api/v2.2/admin/mentors/1/students/");
var request = new RestRequest(Method.DELETE);
request.AddHeader("postman-token", "ceeb1432-1778-4e7c-92f2-7ca1dde9b6a2");
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json");
request.AddHeader("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6InN0ZWVwaGFuc2VsdmFyYWpAdGVzdHByZXNzLmluIiwiZXhwIjoxNDc1MDYyMTkwfQ.iwVg_UM4HBB6qs21fe2b6FlNz_JjRfqcs2VTML4Te3k");
request.AddParameter("application/json", "{ \n    \"students_username\": [ \"john\", \"ragav\"]\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('http://demo.testpress.in/api/v2.2/admin/mentors/1/students/');
$request->setMethod(HTTP_METH_DELETE);

$request->setHeaders(array(
  'postman-token' => 'fcd88f65-8d4a-5a0b-20ee-36ffa49a753f',
  'cache-control' => 'no-cache',
  'content-type' => 'application/json',
  'authorization' => 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6InN0ZWVwaGFuc2VsdmFyYWpAdGVzdHByZXNzLmluIiwiZXhwIjoxNDc1MDYyMTkwfQ.iwVg_UM4HBB6qs21fe2b6FlNz_JjRfqcs2VTML4Te3k'
));

$request->setBody('{ 
    "students_username": [ "john", "ragav"]
}');

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```java
OkHttpClient client = new OkHttpClient();

MediaType mediaType = MediaType.parse("application/json");
RequestBody body = RequestBody.create(mediaType, "{ \n    \"students_username\": [ \"john\", \"ragav\"]\n}");
Request request = new Request.Builder()
  .url("http://demo.testpress.in/api/v2.2/admin/mentors/1/students/")
  .delete(body)
  .addHeader("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6InN0ZWVwaGFuc2VsdmFyYWpAdGVzdHByZXNzLmluIiwiZXhwIjoxNDc1MDYyMTkwfQ.iwVg_UM4HBB6qs21fe2b6FlNz_JjRfqcs2VTML4Te3k")
  .addHeader("content-type", "application/json")
  .addHeader("cache-control", "no-cache")
  .addHeader("postman-token", "5c4514c1-b20f-867d-4daa-bf10708dc01e")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var http = require("http");

var options = {
  "method": "DELETE",
  "hostname": "demo.testpress.in",
  "port": null,
  "path": "/api/v2.2/admin/mentors/1/students/",
  "headers": {
    "authorization": "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6InN0ZWVwaGFuc2VsdmFyYWpAdGVzdHByZXNzLmluIiwiZXhwIjoxNDc1MDYyMTkwfQ.iwVg_UM4HBB6qs21fe2b6FlNz_JjRfqcs2VTML4Te3k",
    "content-type": "application/json",
    "cache-control": "no-cache",
    "postman-token": "55152e63-d460-2456-ed63-bf5c716365a8"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.write(JSON.stringify({ students_username: [ 'john', 'ragav' ] }));
req.end();
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "http://demo.testpress.in/api/v2.2/admin/mentors/1/students/"

	payload := strings.NewReader("{ \n    \"students_username\": [ \"john\", \"ragav\"]\n}")

	req, _ := http.NewRequest("DELETE", url, payload)

	req.Header.Add("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6InN0ZWVwaGFuc2VsdmFyYWpAdGVzdHByZXNzLmluIiwiZXhwIjoxNDc1MDYyMTkwfQ.iwVg_UM4HBB6qs21fe2b6FlNz_JjRfqcs2VTML4Te3k")
	req.Header.Add("content-type", "application/json")
	req.Header.Add("cache-control", "no-cache")
	req.Header.Add("postman-token", "056ddd52-a1bb-2934-09df-82c5f03a1c96")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
> The above command on success will return 204 NO CONTENT

This endpoint allows you to remove students from mentor.

### HTTP Request

`DELETE /api/v2.2/admin/mentors/<:id>/students`

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the mentor to retrieve

### POST data

Parameter | Description
--------- | ------- | -----------
students_username | Array of students username

