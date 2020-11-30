<h1 id="admin_users">Users</h1>
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

## Update User

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "http://demo.testpress.in/api/v2.3/admin/users/2120/"

	payload := strings.NewReader("{\n\t\"password\": \"welcome\"\n}")

	req, _ := http.NewRequest("PUT", url, payload)

	req.Header.Add("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzNDI4NTB9.Dsc2NZ_q0e3GRaBTArgwkPs81RbQEt-FnH0u_TBs2hc")
	req.Header.Add("content-type", "application/json")
	req.Header.Add("cache-control", "no-cache")
	req.Header.Add("postman-token", "9c29d96f-7ea6-35c9-1d30-8ccb20389d39")

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

url = URI("http://demo.testpress.in/api/v2.3/admin/users/2120/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzNDI4NTB9.Dsc2NZ_q0e3GRaBTArgwkPs81RbQEt-FnH0u_TBs2hc'
request["content-type"] = 'application/json'
request["cache-control"] = 'no-cache'
request["postman-token"] = 'e395af73-374f-75e4-4ca2-3751f84b0598'
request.body = "{\n\t\"password\": \"welcome\"\n}"

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://demo.testpress.in/api/v2.3/admin/users/2120/"

payload = "{\n\t\"password\": \"welcome\"\n}"
headers = {
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzNDI4NTB9.Dsc2NZ_q0e3GRaBTArgwkPs81RbQEt-FnH0u_TBs2hc",
    'content-type': "application/json",
    'cache-control': "no-cache",
    'postman-token': "25ef8298-0a61-7404-3a97-db9d0250ef78"
    }

response = requests.request("PUT", url, data=payload, headers=headers)

print(response.text)
```

```shell
curl --request PUT \
  --url http://demo.testpress.in/api/v2.3/admin/users/2120/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzNDI4NTB9.Dsc2NZ_q0e3GRaBTArgwkPs81RbQEt-FnH0u_TBs2hc' \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json' \
  --header 'postman-token: 5bdb17f6-db4d-c72e-a30f-c1776f0d8384' \
  --data '{\n	"password": "welcome"\n}'
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('http://demo.testpress.in/api/v2.3/admin/users/2120/');
$request->setMethod(HTTP_METH_PUT);

$request->setHeaders(array(
  'postman-token' => '652f45cc-e181-b3e2-706c-47459bb5363e',
  'cache-control' => 'no-cache',
  'content-type' => 'application/json',
  'authorization' => 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzNDI4NTB9.Dsc2NZ_q0e3GRaBTArgwkPs81RbQEt-FnH0u_TBs2hc'
));

$request->setBody('{
	"password": "welcome"
}');

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```csharp
var client = new RestClient("http://demo.testpress.in/api/v2.3/admin/users/2120/");
var request = new RestRequest(Method.PUT);
request.AddHeader("postman-token", "0ce5b8e5-0793-457c-32e7-f5c96be55aa9");
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json");
request.AddHeader("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzNDI4NTB9.Dsc2NZ_q0e3GRaBTArgwkPs81RbQEt-FnH0u_TBs2hc");
request.AddParameter("application/json", "{\n\t\"password\": \"welcome\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```javascript
var http = require("http");

var options = {
  "method": "PUT",
  "hostname": "demo.testpress.in",
  "port": null,
  "path": "/api/v2.3/admin/users/2120/",
  "headers": {
    "authorization": "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzNDI4NTB9.Dsc2NZ_q0e3GRaBTArgwkPs81RbQEt-FnH0u_TBs2hc",
    "content-type": "application/json",
    "cache-control": "no-cache",
    "postman-token": "a4f44159-0b97-e199-ecca-7c5646324c84"
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

req.write(JSON.stringify({ password: 'welcome' }));
req.end();
```

```java
OkHttpClient client = new OkHttpClient();

MediaType mediaType = MediaType.parse("application/json");
RequestBody body = RequestBody.create(mediaType, "{\n\t\"password\": \"welcome\"\n}");
Request request = new Request.Builder()
  .url("http://demo.testpress.in/api/v2.3/admin/users/2120/")
  .put(body)
  .addHeader("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzNDI4NTB9.Dsc2NZ_q0e3GRaBTArgwkPs81RbQEt-FnH0u_TBs2hc")
  .addHeader("content-type", "application/json")
  .addHeader("cache-control", "no-cache")
  .addHeader("postman-token", "2d5c843c-b6ee-d38e-7a3b-7a71c0353bc8")
  .build();

Response response = client.newCall(request).execute();
```

> The above command returns JSON structured like this:

```json
{
    "id": 2120,
    "username": "goodboy",
    "password_hash": "pbkdf2_sha256$12000$zaz1v370q51a$ipNrjQCWNOAmdFsHWPHHZ1i1+5hxF5LxHZ+VfFZ9mrM=",
    "email": "",
    "first_name": "",
    "last_name": "",
    "display_name": "goodboy",
    "photo": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/png/3a6be029faea4c41915291da8778c36d.png",
    "large_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/png/3a6be029faea4c41915291da8778c36d.png",
    "medium_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/png/82b59e4b2d29426ab74b25457384961b.png",
    "medium_small_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/png/b8d2e490f8414d8485a1261fcba80d11.png",
    "small_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/png/2aa6f66820dd4fe9acdd2b63da148f8c.png",
    "x_small_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/png/64818b7216f340b3be636e32effc57fd.png",
    "mini_image": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/png/9746d9747c184aa98273fbb9c5222adc.png",
    "birth_date": null,
    "gender_code": null,
    "gender": null,
    "address1": "",
    "address2": "",
    "city": "",
    "zip": "",
    "state": "",
    "state_code": "",
    "phone": "",
    "batches": [],
    "created": "2017-08-03T18:25:45.949568Z",
    "modified": "2017-08-03T18:29:24.712464Z"
}
```
This endpoint allows you to update details of a particular user.

### HTTP Request

`PUT /api/v2.2/admin/users/<:id>`

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the user to update

### Fields

Name | Type | Description
-----|------|-------------
username | string | Username of the user
password | string | Password to update the user
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
state | string | State (Read Only)
phone | string | Phone of user

### Read Only Fields
password_hash, gender, state, large_image, medium_image, medium_small_image, small_image, xsmall_image, mini_image, created, modified

### Write Only Fields
password

## Delete User 

This endpoint allows you to delete particular user. Please be aware this will delete all the data related to the user. The operation is ir reversible

### HTTP Request

`DELETE /api/v2.2/admin/users/<:id>`

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the user to retrieve

## View User by email

```go 
package main

import (
    "fmt"
    "net/http"
    "io/ioutil"
)

func main() {

    url := "http://demo.testpress.in//api/v2.2/admin/users/?email=bharathwaaj.s%40gmail.com"

    req, _ := http.NewRequest("GET", url, nil)

    req.Header.Add("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzODY4NTV9.5w4InsvTPtQGgj4L1myQGc1qxw7IvNEpa3BtVfQOtxE")
    req.Header.Add("cache-control", "no-cache")
    req.Header.Add("postman-token", "80159c50-160a-991a-f513-a5fafa286a1b")

    res, _ := http.DefaultClient.Do(req)

    defer res.Body.Close()
    body, _ := ioutil.ReadAll(res.Body)

    fmt.Println(res)
    fmt.Println(string(body))

}

```ruby

require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in//api/v2.2/admin/users/?email=bharathwaaj.s%40gmail.com")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzODY4NTV9.5w4InsvTPtQGgj4L1myQGc1qxw7IvNEpa3BtVfQOtxE'
request["cache-control"] = 'no-cache'
request["postman-token"] = 'b21426e3-c795-8d2f-eb0b-db5d81ac2ec0'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://demo.testpress.in//api/v2.2/admin/users/"

querystring = {"email":"bharathwaaj.s@gmail.com"}

headers = {
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzODY4NTV9.5w4InsvTPtQGgj4L1myQGc1qxw7IvNEpa3BtVfQOtxE",
    'cache-control': "no-cache",
    'postman-token': "d46170d5-b684-79ad-2ce8-b2c5d8cb5988"
    }

response = requests.request("GET", url, headers=headers, params=querystring)

print(response.text)
```

```shell
curl -X GET -H "Authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzODY4NTV9.5w4InsvTPtQGgj4L1myQGc1qxw7IvNEpa3BtVfQOtxE" -H "Cache-Control: no-cache" -H "Postman-Token: c8cbe2a1-76d0-da3a-1bbb-38cd3f61f215" "http://demo.testpress.in//api/v2.2/admin/users/?email=bharathwaaj.s@gmail.com"
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('http://demo.testpress.in//api/v2.2/admin/users/');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'email' => 'bharathwaaj.s@gmail.com'
));

$request->setHeaders(array(
  'postman-token' => 'f09b000b-ac7c-da00-2532-85010b519a60',
  'cache-control' => 'no-cache',
  'authorization' => 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzODY4NTV9.5w4InsvTPtQGgj4L1myQGc1qxw7IvNEpa3BtVfQOtxE'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```csharp
var client = new RestClient("http://demo.testpress.in//api/v2.2/admin/users/?email=bharathwaaj.s%40gmail.com");
var request = new RestRequest(Method.GET);
request.AddHeader("postman-token", "30c7ab26-66ed-0558-dd6f-8cc4b66d5644");
request.AddHeader("cache-control", "no-cache");
request.AddHeader("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzODY4NTV9.5w4InsvTPtQGgj4L1myQGc1qxw7IvNEpa3BtVfQOtxE");
IRestResponse response = client.Execute(request);
```

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("http://demo.testpress.in//api/v2.2/admin/users/?email=bharathwaaj.s%40gmail.com")
  .get()
  .addHeader("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzODY4NTV9.5w4InsvTPtQGgj4L1myQGc1qxw7IvNEpa3BtVfQOtxE")
  .addHeader("cache-control", "no-cache")
  .addHeader("postman-token", "05ef17ed-3a9c-3745-ee1b-10ae5963bbcc")
  .build();

Response response = client.newCall(request).execute();
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
      "id": 36,
      "url": "http://demo.testpress.in/api/v2.2/admin/users/36/",
      "username": "bharath",
      "first_name": "Bharath Kumar",
      "last_name": "S",
      "display_name": "Bharath Kumar S",
      "email": "bharathwaaj.s@gmail.com",
      "photo": "https://s3-ap-southeast-1.amazonaws.com/media.testpress.in/i/cb88287098924bd6ae615ca4aa71eab5.png",
      "large_image": "",
      "medium_image": "",
      "small_image": "",
      "x_small_image": "",
      "mini_image": "",
      "birth_date": "17/08/1987",
      "gender_code": "male",
      "gender": "Male",
      "address1": "257 A Timber Mill Road",
      "address2": "4th Cross, New Thippasandra",
      "city": "Bangalore",
      "zip": "560075",
      "state": "",
      "state_code": "",
      "phone": "9787231006",
      "batches": [
        {
          "id": 26,
          "name": "UPSC Evening Batch",
          "url": "http://demo.testpress.in/api/v2.2/admin/batches/26/"
        },
        {
          "id": 25,
          "name": "IBPS Online Batch",
          "url": "http://demo.testpress.in/api/v2.2/admin/batches/25/"
        },
        {
          "id": 24,
          "name": "NEET Morning Batch",
          "url": "http://demo.testpress.in/api/v2.2/admin/batches/24/"
        },
        {
          "id": 23,
          "name": "UPSC Morning Batch",
          "url": "http://demo.testpress.in/api/v2.2/admin/batches/23/"
        },
        {
          "id": 22,
          "name": "IBPS Morning Batch",
          "url": "http://demo.testpress.in/api/v2.2/admin/batches/22/"
        },
        {
          "id": 21,
          "name": "st std A",
          "url": "http://demo.testpress.in/api/v2.2/admin/batches/21/"
        },
        {
          "id": 20,
          "name": "OHC 2013",
          "url": "http://demo.testpress.in/api/v2.2/admin/batches/20/"
        },
        {
          "id": 19,
          "name": "POZITIVE ONLINE TEST SERIES",
          "url": "http://demo.testpress.in/api/v2.2/admin/batches/19/"
        },
        {
          "id": 18,
          "name": "Unique UPSC Batch",
          "url": "http://demo.testpress.in/api/v2.2/admin/batches/18/"
        }
      ],
      "batches_url": "http://demo.testpress.in/api/v2.2/admin/users/36/batches/"
    }
  ]
}

```
This endpoint allows you to view details of a particular user by email address

### HTTP Request

`GET /api/v2.2/admin/users/?email=<:email_id>`

### URL Parameters

Parameter | Description
--------- | ------- | -----------
email | Email Address of the user

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
batches| array | Batches to which user has access


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
> The above command returns JSON structured like this:

```json
[
  {
    "id": 29,
    "name": "Test Batch",
    "url": "http://demo.testpress.in/api/v2.2/admin/batches/29/"
  },
  {
    "id": 24,
    "name": "NEET Morning Batch",
    "url": "http://demo.testpress.in/api/v2.2/admin/batches/24/"
  },
  {
    "id": 23,
    "name": "UPSC Morning Batch",
    "url": "http://demo.testpress.in/api/v2.2/admin/batches/23/"
  },
  {
    "id": 22,
    "name": "IBPS Morning Batch",
    "url": "http://demo.testpress.in/api/v2.2/admin/batches/22/"
  }
]
```

This endpoint allows you to add users to batches

### HTTP Request

`POST /api/v2.2/admin/users/<id>/batches/`

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the user to retrieve

### POST data

Parameter | Description
--------- | ------- | -----------
batches | Array of string of batches names to add the user to 

### Response Fields

Name | Type | Description
-----|------|-------------
id | string | Id of the batch
url | string | Unique endpoint of that batch
name | string | Name of the batch

## Remove batches

```shell
curl --request DELETE \
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

request = Net::HTTP::Delete.new(url)
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

response = requests.request("DELETE", url, data=payload, headers=headers)

print(response.text)
```

```csharp
var client = new RestClient("http://demo.testpress.in/api/v2.2/admin/users/1892/batches/");
var request = new RestRequest(Method.DELETE);
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
$request->setMethod(HTTP_METH_DELETE);

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
  .delete(body)
  .addHeader("content-type", "application/json")
  .addHeader("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAyMjk2MDd9.ynLE30wWup2CXMqgpNjT4ZBAUAtttqebzat-stuVB84")
  .addHeader("cache-control", "no-cache")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var http = require("http");

var options = {
  "method": "DELETE",
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

    req, _ := http.NewRequest("DELETE", url, payload)

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

> The above command on success will return 204 NO CONTENT

This endpoint allows you to remove users from batches

### HTTP Request

`DELETE /api/v2.2/admin/users/<id>/batches/`

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the user to retrieve

### POST data

Parameter | Description
--------- | ------- | -----------
batches | Array of string of batches names to add the user to 

