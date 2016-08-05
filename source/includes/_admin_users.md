# Users
Admin Users API gives you access to create/edit users in the institute.

## Create User

```shell
curl --request POST \
  --url http://demo.testpress.in/api/v2.2/admin/users/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAyMjk2MDd9.ynLE30wWup2CXMqgpNjT4ZBAUAtttqebzat-stuVB84' \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json' \
  --data '{"username": "lorem", "password": "ipsum1$", "first_name": "John", "last_name": "Appleseed", "email": "test@example.com", "birth_date": "03/07/2016", "gender_code": "male", "state_code": "IN-TN", "batches": ["Test Batch", "UPSC Morning Batch"]}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.2/admin/users/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAyMjk2MDd9.ynLE30wWup2CXMqgpNjT4ZBAUAtttqebzat-stuVB84'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"username\": \"lorem\",\n    \"password\": \"ipsum1$\",\n    \"first_name\": \"John\",\n    \"last_name\": \"Appleseed\",\n    \"email\": \"test@example.com\",\n    \"birth_date\": \"03/07/2016\",\n    \"gender_code\": \"male\",\n    \"state_code\": \"IN-TN\",\n    \"batches\": [\"Test Batch\", \"UPSC Morning Batch\"]\n}"

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://demo.testpress.in/api/v2.2/admin/users/"

payload = "{\n    \"username\": \"lorem\",\n    \"password\": \"ipsum1$\",\n    \"first_name\": \"John\",\n    \"last_name\": \"Appleseed\",\n    \"email\": \"test@example.com\",\n    \"birth_date\": \"03/07/2016\",\n    \"gender_code\": \"male\",\n    \"state_code\": \"IN-TN\",\n    \"batches\": [\"Test Batch\", \"UPSC Morning Batch\"]\n}"
headers = {
    'content-type': "application/json",
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAyMjk2MDd9.ynLE30wWup2CXMqgpNjT4ZBAUAtttqebzat-stuVB84",
    'cache-control': "no-cache"
    }

response = requests.request("POST", url, data=payload, headers=headers)

print(response.text)
```

```csharp
var client = new RestClient("http://demo.testpress.in/api/v2.2/admin/users/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAyMjk2MDd9.ynLE30wWup2CXMqgpNjT4ZBAUAtttqebzat-stuVB84");
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\n    \"username\": \"lorem\",\n    \"password\": \"ipsum1$\",\n    \"first_name\": \"John\",\n    \"last_name\": \"Appleseed\",\n    \"email\": \"test@example.com\",\n    \"birth_date\": \"03/07/2016\",\n    \"gender_code\": \"male\",\n    \"state_code\": \"IN-TN\",\n    \"batches\": [\"Test Batch\", \"UPSC Morning Batch\"]\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('http://demo.testpress.in/api/v2.2/admin/users/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'authorization' => 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAyMjk2MDd9.ynLE30wWup2CXMqgpNjT4ZBAUAtttqebzat-stuVB84',
  'content-type' => 'application/json'
));

$request->setBody('{
    "username": "lorem",
    "password": "ipsum1$",
    "first_name": "John",
    "last_name": "Appleseed",
    "email": "test@example.com",
    "birth_date": "03/07/2016",
    "gender_code": "male",
    "state_code": "IN-TN",
    "batches": ["Test Batch", "UPSC Morning Batch"]
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
RequestBody body = RequestBody.create(mediaType, "{\n    \"username\": \"lorem\",\n    \"password\": \"ipsum1$\",\n    \"first_name\": \"John\",\n    \"last_name\": \"Appleseed\",\n    \"email\": \"test@example.com\",\n    \"birth_date\": \"03/07/2016\",\n    \"gender_code\": \"male\",\n    \"state_code\": \"IN-TN\",\n    \"batches\": [\"Test Batch\", \"UPSC Morning Batch\"]\n}");
Request request = new Request.Builder()
  .url("http://demo.testpress.in/api/v2.2/admin/users/")
  .post(body)
  .addHeader("content-type", "application/json")
  .addHeader("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAyMjk2MDd9.ynLE30wWup2CXMqgpNjT4ZBAUAtttqebzat-stuVB84")
  .addHeader("cache-control", "no-cache")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var http = require("http");

var options = {
  "method": "POST",
  "hostname": "demo.testpress.in",
  "port": null,
  "path": "/api/v2.2/admin/users/",
  "headers": {
    "content-type": "application/json",
    "authorization": "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAyMjk2MDd9.ynLE30wWup2CXMqgpNjT4ZBAUAtttqebzat-stuVB84",
    "cache-control": "no-cache"
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

req.write(JSON.stringify({ username: 'lorem',
  password: 'ipsum1$',
  first_name: 'John',
  last_name: 'Appleseed',
  email: 'test@example.com',
  birth_date: '03/07/2016',
  gender_code: 'male',
  state_code: 'IN-TN',
  batches: [ 'Test Batch', 'UPSC Morning Batch' ] }));
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

    url := "http://demo.testpress.in/api/v2.2/admin/users/"

    payload := strings.NewReader("{\n    \"username\": \"lorem\",\n    \"password\": \"ipsum1$\",\n    \"first_name\": \"John\",\n    \"last_name\": \"Appleseed\",\n    \"email\": \"test@example.com\",\n    \"birth_date\": \"03/07/2016\",\n    \"gender_code\": \"male\",\n    \"state_code\": \"IN-TN\",\n    \"batches\": [\"Test Batch\", \"UPSC Morning Batch\"]\n}")

    req, _ := http.NewRequest("POST", url, payload)

    req.Header.Add("content-type", "application/json")
    req.Header.Add("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAyMjk2MDd9.ynLE30wWup2CXMqgpNjT4ZBAUAtttqebzat-stuVB84")
    req.Header.Add("cache-control", "no-cache")

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
  "id": 1892,
  "url": "http://demo.testpress.in/api/v2.2/admin/users/1892/",
  "username": "lorem",
  "first_name": "John",
  "last_name": "Appleseed",
  "display_name": "John Appleseed",
  "email": "test@example.com",
  "photo": null,
  "large_image": "",
  "medium_image": "",
  "small_image": "",
  "x_small_image": "",
  "mini_image": "",
  "birth_date": "03/07/2016",
  "gender_code": "male",
  "gender": "Male",
  "address1": "",
  "address2": "",
  "city": "",
  "zip": "",
  "state": "Tamil Nadu",
  "state_code": "IN-TN",
  "phone": "",
  "batches": [
    {
      "id": 29,
      "name": "Test Batch",
      "url": "http://demo.testpress.in/api/v2.2/admin/batches/29/"
    },
    {
      "id": 23,
      "name": "UPSC Morning Batch",
      "url": "http://demo.testpress.in/api/v2.2/admin/batches/23/"
    }
  ],
  "batches_url": "http://demo.testpress.in/api/v2.2/admin/users/1892/batches/"
}

```

This endpoint creates a user.

### HTTP Request

`POST /api/v2.2/admin/users/`

<aside class="info">You can optionally add a <i>batches</i> field in the <strong>POST</strong> data with an array of batch names. The user will automatically get added to those batches during creation.</aside>

Except username and password, all other fields are optional.

### Fields

Name | Type | Description
-----|------|-------------
username | string | Username of the user
first_name | string | First name of the user
last_name | string | Last name of the user
email | string | Email of the user
birth_date | datestring | Birth date of user. Should be in DD/MM/YYYY format
gender_code | string | Gender of user. Can be "male", "female" or "trans"
address1 | string | Address of user
address2 | string | Address of user
city | string | City of user
zip | string | Pincode of user
state_code | string | State of user in ISO 3166-2:IN format (https://en.wikipedia.org/wiki/ISO_3166-2:IN)
phone | string | Phone of user
batches | string | Pass as array of batch name strings.

## View User

```go
package main

import (
    "fmt"
    "strings"
    "net/http"
    "io/ioutil"
)

func main() {

    url := "http://demo.testpress.in/api/v2.2/admin/users/1889/"

    payload := strings.NewReader("{\n    \"username\": \"admin15\",\n    \"password\": \"demouser\",\n    \"first_name\": \"Cool\",\n    \"last_name\": \"dude\",\n    \"email\": \"cool@dude.com\",\n    \"birth_date\": \"03/07/2016\",\n    \"gender_code\": \"trans\",\n    \"state_code\": \"IN-TN\"\n}")

    req, _ := http.NewRequest("GET", url, payload)

    req.Header.Add("content-type", "application/json")
    req.Header.Add("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzNDI4NTB9.Dsc2NZ_q0e3GRaBTArgwkPs81RbQEt-FnH0u_TBs2hc")
    req.Header.Add("cache-control", "no-cache")

    res, _ := http.DefaultClient.Do(req)

    defer res.Body.Close()
    body, _ := ioutil.ReadAll(res.Body)

    fmt.Println(res)
    fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.2/admin/users/1889/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["content-type"] = 'application/json'
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzNDI4NTB9.Dsc2NZ_q0e3GRaBTArgwkPs81RbQEt-FnH0u_TBs2hc'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"username\": \"admin15\",\n    \"password\": \"demouser\",\n    \"first_name\": \"Cool\",\n    \"last_name\": \"dude\",\n    \"email\": \"cool@dude.com\",\n    \"birth_date\": \"03/07/2016\",\n    \"gender_code\": \"trans\",\n    \"state_code\": \"IN-TN\"\n}"

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://demo.testpress.in/api/v2.2/admin/users/1889/"

payload = "{\n    \"username\": \"admin15\",\n    \"password\": \"demouser\",\n    \"first_name\": \"Cool\",\n    \"last_name\": \"dude\",\n    \"email\": \"cool@dude.com\",\n    \"birth_date\": \"03/07/2016\",\n    \"gender_code\": \"trans\",\n    \"state_code\": \"IN-TN\"\n}"
headers = {
    'content-type': "application/json",
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzNDI4NTB9.Dsc2NZ_q0e3GRaBTArgwkPs81RbQEt-FnH0u_TBs2hc",
    'cache-control': "no-cache"
    }

response = requests.request("GET", url, data=payload, headers=headers)

print(response.text)
```

```shell
curl --request GET \
  --url http://demo.testpress.in/api/v2.2/admin/users/1889/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzNDI4NTB9.Dsc2NZ_q0e3GRaBTArgwkPs81RbQEt-FnH0u_TBs2hc' \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json' \
  --data '{"username": "admin15", "password": "demouser", "first_name": "Cool", "last_name": "dude", "email": "cool@dude.com", "birth_date": "03/07/2016", "gender_code": "trans", "state_code": "IN-TN"\n}'
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('http://demo.testpress.in/api/v2.2/admin/users/1889/');
$request->setMethod(HTTP_METH_GET);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'authorization' => 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzNDI4NTB9.Dsc2NZ_q0e3GRaBTArgwkPs81RbQEt-FnH0u_TBs2hc',
  'content-type' => 'application/json'
));

$request->setBody('{
    "username": "admin15",
    "password": "demouser",
    "first_name": "Cool",
    "last_name": "dude",
    "email": "cool@dude.com",
    "birth_date": "03/07/2016",
    "gender_code": "trans",
    "state_code": "IN-TN"
}');

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```csharp
var client = new RestClient("http://demo.testpress.in/api/v2.2/admin/users/1889/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzNDI4NTB9.Dsc2NZ_q0e3GRaBTArgwkPs81RbQEt-FnH0u_TBs2hc");
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\n    \"username\": \"admin15\",\n    \"password\": \"demouser\",\n    \"first_name\": \"Cool\",\n    \"last_name\": \"dude\",\n    \"email\": \"cool@dude.com\",\n    \"birth_date\": \"03/07/2016\",\n    \"gender_code\": \"trans\",\n    \"state_code\": \"IN-TN\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```javascript
var http = require("http");

var options = {
  "method": "GET",
  "hostname": "demo.testpress.in",
  "port": null,
  "path": "/api/v2.2/admin/users/1889/",
  "headers": {
    "content-type": "application/json",
    "authorization": "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzNDI4NTB9.Dsc2NZ_q0e3GRaBTArgwkPs81RbQEt-FnH0u_TBs2hc",
    "cache-control": "no-cache"
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

req.write(JSON.stringify({ username: 'admin15',
  password: 'demouser',
  first_name: 'Cool',
  last_name: 'dude',
  email: 'cool@dude.com',
  birth_date: '03/07/2016',
  gender_code: 'trans',
  state_code: 'IN-TN' }));
req.end();
```

```java
OkHttpClient client = new OkHttpClient();

MediaType mediaType = MediaType.parse("application/json");
RequestBody body = RequestBody.create(mediaType, "{\n    \"username\": \"admin15\",\n    \"password\": \"demouser\",\n    \"first_name\": \"Cool\",\n    \"last_name\": \"dude\",\n    \"email\": \"cool@dude.com\",\n    \"birth_date\": \"03/07/2016\",\n    \"gender_code\": \"trans\",\n    \"state_code\": \"IN-TN\"\n}");
Request request = new Request.Builder()
  .url("http://demo.testpress.in/api/v2.2/admin/users/1889/")
  .get()
  .addHeader("content-type", "application/json")
  .addHeader("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzNDI4NTB9.Dsc2NZ_q0e3GRaBTArgwkPs81RbQEt-FnH0u_TBs2hc")
  .addHeader("cache-control", "no-cache")
  .build();

Response response = client.newCall(request).execute();
```

> The above command returns JSON structured like this:

```json
{
  "id": 1889,
  "url": "http://demo.testpress.in/api/v2.2/admin/users/1889/",
  "username": "lorem",
  "first_name": "John",
  "last_name": "Appleseed",
  "display_name": "John Appleseed",
  "email": "test@example.com",
  "photo": null,
  "large_image": "",
  "medium_image": "",
  "small_image": "",
  "x_small_image": "",
  "mini_image": "",
  "birth_date": "03/07/2016",
  "gender_code": "male",
  "gender": "Male",
  "address1": "",
  "address2": "",
  "city": "",
  "zip": "",
  "state": "Tamil Nadu",
  "state_code": "IN-TN",
  "phone": ""
}
```
This endpoint allows you to view details of a particular user.

### HTTP Request

`GET /api/v2.2/admin/users/<:id>`

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the user to retrieve

### Fields

Name | Type | Description
-----|------|-------------
username | string | Username of the user
first_name | string | First name of the user
last_name | string | Last name of the user
display_name | string | Name of the user to be displayed
email | string | Email of the user
photo | string | Original image of the user as uploaded
large_image | string | Profile image with size 256x256
medium_image | string | Profile image with size 128x128
small_image | string | Profile image with size 48x48
xsmall_image | string | Profile image with size 32x32
mini_image | string | Profile image with size 24x24
birth_date | datestring | Birth date of user. Should be in DD/MM/YYYY format
gender_code | string | Gender of user. Can be "male", "female" or "trans"
gender | string | (Read only) Human readable gender of user. Can be "Male", "Female" or "Transgender"
address1 | string | Address of user
address2 | string | Address of user
city | string | City of user
zip | string | Pincode of user
state_code | string | State of user in ISO 3166-2:IN format (https://en.wikipedia.org/wiki/ISO_3166-2:IN)
phone | string | Phone of user

## View batches

```shell
curl --request GET \
  --url http://demo.testpress.in/api/v2.2/admin/users/1892/batches/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAyMjk2MDd9.ynLE30wWup2CXMqgpNjT4ZBAUAtttqebzat-stuVB84' \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json'
```

```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.2/admin/users/1892/batches/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["content-type"] = 'application/json'
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAyMjk2MDd9.ynLE30wWup2CXMqgpNjT4ZBAUAtttqebzat-stuVB84'
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://demo.testpress.in/api/v2.2/admin/users/1892/batches/"

payload = ""
headers = {
    'content-type': "application/json",
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAyMjk2MDd9.ynLE30wWup2CXMqgpNjT4ZBAUAtttqebzat-stuVB84",
    'cache-control': "no-cache"
    }

response = requests.request("GET", url, data=payload, headers=headers)

print(response.text)
```

```csharp
var client = new RestClient("http://demo.testpress.in/api/v2.2/admin/users/1892/batches/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAyMjk2MDd9.ynLE30wWup2CXMqgpNjT4ZBAUAtttqebzat-stuVB84");
request.AddHeader("content-type", "application/json");
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('http://demo.testpress.in/api/v2.2/admin/users/1892/batches/');
$request->setMethod(HTTP_METH_GET);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'authorization' => 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAyMjk2MDd9.ynLE30wWup2CXMqgpNjT4ZBAUAtttqebzat-stuVB84',
  'content-type' => 'application/json'
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
  .url("http://demo.testpress.in/api/v2.2/admin/users/1892/batches/")
  .get()
  .addHeader("content-type", "application/json")
  .addHeader("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAyMjk2MDd9.ynLE30wWup2CXMqgpNjT4ZBAUAtttqebzat-stuVB84")
  .addHeader("cache-control", "no-cache")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var http = require("http");

var options = {
  "method": "GET",
  "hostname": "demo.testpress.in",
  "port": null,
  "path": "/api/v2.2/admin/users/1892/batches/",
  "headers": {
    "content-type": "application/json",
    "authorization": "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAyMjk2MDd9.ynLE30wWup2CXMqgpNjT4ZBAUAtttqebzat-stuVB84",
    "cache-control": "no-cache"
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

    url := "http://demo.testpress.in/api/v2.2/admin/users/1892/batches/"

    req, _ := http.NewRequest("GET", url, nil)

    req.Header.Add("content-type", "application/json")
    req.Header.Add("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAyMjk2MDd9.ynLE30wWup2CXMqgpNjT4ZBAUAtttqebzat-stuVB84")
    req.Header.Add("cache-control", "no-cache")

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
  "count": 2,
  "next": null,
  "previous": null,
  "per_page": 20,
  "results": [
    {
      "id": 29,
      "name": "Test Batch",
      "url": "http://demo.testpress.in/api/v2.2/admin/batches/29/"
    },
    {
      "id": 23,
      "name": "UPSC Morning Batch",
      "url": "http://demo.testpress.in/api/v2.2/admin/batches/23/"
    }
  ]
}
```
This endpoint allows you to view batches of a particular user.

### HTTP Request

`GET /api/v2.2/admin/users/<id>/batches/`

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the user to retrieve

### Response Fields

Name | Type | Description
-----|------|-------------
id | string | Id of the batch
url | string | Unique endpoint of that batch
name | string | Name of the batch

## Add batches

```shell
curl --request POST \
  --url http://demo.testpress.in/api/v2.2/admin/users/1892/batches/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAyMjk2MDd9.ynLE30wWup2CXMqgpNjT4ZBAUAtttqebzat-stuVB84' \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json' \
  --data '{"batches": ["NEET Morning Batch", "IBPS Morning Batch"]}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.2/admin/users/1892/batches/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAyMjk2MDd9.ynLE30wWup2CXMqgpNjT4ZBAUAtttqebzat-stuVB84'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"batches\": [\"NEET Morning Batch\", \"IBPS Morning Batch\"]\n}"

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://demo.testpress.in/api/v2.2/admin/users/1892/batches/"

payload = "{\n    \"batches\": [\"NEET Morning Batch\", \"IBPS Morning Batch\"]\n}"
headers = {
    'content-type': "application/json",
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAyMjk2MDd9.ynLE30wWup2CXMqgpNjT4ZBAUAtttqebzat-stuVB84",
    'cache-control': "no-cache"
    }

response = requests.request("POST", url, data=payload, headers=headers)

print(response.text)
```

```csharp
var client = new RestClient("http://demo.testpress.in/api/v2.2/admin/users/1892/batches/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAyMjk2MDd9.ynLE30wWup2CXMqgpNjT4ZBAUAtttqebzat-stuVB84");
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\n    \"batches\": [\"NEET Morning Batch\", \"IBPS Morning Batch\"]\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('http://demo.testpress.in/api/v2.2/admin/users/1892/batches/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'authorization' => 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAyMjk2MDd9.ynLE30wWup2CXMqgpNjT4ZBAUAtttqebzat-stuVB84',
  'content-type' => 'application/json'
));

$request->setBody('{
    "batches": ["NEET Morning Batch", "IBPS Morning Batch"]
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
RequestBody body = RequestBody.create(mediaType, "{\n    \"batches\": [\"NEET Morning Batch\", \"IBPS Morning Batch\"]\n}");
Request request = new Request.Builder()
  .url("http://demo.testpress.in/api/v2.2/admin/users/1892/batches/")
  .post(body)
  .addHeader("content-type", "application/json")
  .addHeader("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAyMjk2MDd9.ynLE30wWup2CXMqgpNjT4ZBAUAtttqebzat-stuVB84")
  .addHeader("cache-control", "no-cache")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var http = require("http");

var options = {
  "method": "POST",
  "hostname": "demo.testpress.in",
  "port": null,
  "path": "/api/v2.2/admin/users/1892/batches/",
  "headers": {
    "content-type": "application/json",
    "authorization": "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAyMjk2MDd9.ynLE30wWup2CXMqgpNjT4ZBAUAtttqebzat-stuVB84",
    "cache-control": "no-cache"
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

req.write(JSON.stringify({ batches: [ 'NEET Morning Batch', 'IBPS Morning Batch' ] }));
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

    url := "http://demo.testpress.in/api/v2.2/admin/users/1892/batches/"

    payload := strings.NewReader("{\n    \"batches\": [\"NEET Morning Batch\", \"IBPS Morning Batch\"]\n}")

    req, _ := http.NewRequest("POST", url, payload)

    req.Header.Add("content-type", "application/json")
    req.Header.Add("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAyMjk2MDd9.ynLE30wWup2CXMqgpNjT4ZBAUAtttqebzat-stuVB84")
    req.Header.Add("cache-control", "no-cache")

    res, _ := http.DefaultClient.Do(req)

    defer res.Body.Close()
    body, _ := ioutil.ReadAll(res.Body)

    fmt.Println(res)
    fmt.Println(string(body))

}
```

