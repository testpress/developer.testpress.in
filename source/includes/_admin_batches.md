#Batches
Batches API lets you create and retrieve batches in your institute.

##Get All batches

```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.2/admin/batches/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MTgsInVzZXJfaWQiOjE4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzMTEyNzl9.fDF03EIOEoXTyVUA3sN9-biUGhWrzO_NIZo1KYCUkbU'
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://demo.testpress.in/api/v2.2/admin/batches/"

headers = {
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MTgsInVzZXJfaWQiOjE4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzMTEyNzl9.fDF03EIOEoXTyVUA3sN9-biUGhWrzO_NIZo1KYCUkbU",
    'cache-control': "no-cache"
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```shell
curl --request GET \
  --url http://demo.testpress.in/api/v2.2/admin/batches/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MTgsInVzZXJfaWQiOjE4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzMTEyNzl9.fDF03EIOEoXTyVUA3sN9-biUGhWrzO_NIZo1KYCUkbU' \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("http://demo.testpress.in/api/v2.2/admin/batches/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MTgsInVzZXJfaWQiOjE4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzMTEyNzl9.fDF03EIOEoXTyVUA3sN9-biUGhWrzO_NIZo1KYCUkbU");
IRestResponse response = client.Execute(request);
```

```javascript
var http = require("http");

var options = {
  "method": "GET",
  "hostname": "demo.testpress.in",
  "port": null,
  "path": "/api/v2.2/admin/batches/",
  "headers": {
    "content-type": "application/json",
    "authorization": "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzNDI4NTB9.Dsc2NZ_q0e3GRaBTArgwkPs81RbQEt-FnH0u_TBs2hc",
    "cache-control": "no-cache",
    "postman-token": "fcdc5d46-d477-3310-5221-d7e228714def"
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

```php
<?php

$request = new HttpRequest();
$request->setUrl('http://demo.testpress.in/api/v2.2/admin/batches/');
$request->setMethod(HTTP_METH_GET);

$request->setHeaders(array(
  'postman-token' => '4805a06e-813c-0357-dad6-d9c66de97a19',
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

```java
OkHttpClient client = new OkHttpClient();

MediaType mediaType = MediaType.parse("application/json");
RequestBody body = RequestBody.create(mediaType, "{\n    \"username\": \"admin15\",\n    \"password\": \"demouser\",\n    \"first_name\": \"Cool\",\n    \"last_name\": \"dude\",\n    \"email\": \"cool@dude.com\",\n    \"birth_date\": \"03/07/2016\",\n    \"gender_code\": \"trans\",\n    \"state_code\": \"IN-TN\"\n}");
Request request = new Request.Builder()
  .url("http://demo.testpress.in/api/v2.2/admin/batches/")
  .get()
  .addHeader("content-type", "application/json")
  .addHeader("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzNDI4NTB9.Dsc2NZ_q0e3GRaBTArgwkPs81RbQEt-FnH0u_TBs2hc")
  .addHeader("cache-control", "no-cache")
  .addHeader("postman-token", "8fd29aa5-9e74-0228-a86e-43c26a6cbb18")
  .build();

Response response = client.newCall(request).execute();
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

    url := "http://demo.testpress.in/api/v2.2/admin/batches/"

    payload := strings.NewReader("{\n    \"username\": \"admin15\",\n    \"password\": \"demouser\",\n    \"first_name\": \"Cool\",\n    \"last_name\": \"dude\",\n    \"email\": \"cool@dude.com\",\n    \"birth_date\": \"03/07/2016\",\n    \"gender_code\": \"trans\",\n    \"state_code\": \"IN-TN\"\n}")

    req, _ := http.NewRequest("GET", url, payload)

    req.Header.Add("content-type", "application/json")
    req.Header.Add("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzNDI4NTB9.Dsc2NZ_q0e3GRaBTArgwkPs81RbQEt-FnH0u_TBs2hc")
    req.Header.Add("cache-control", "no-cache")
    req.Header.Add("postman-token", "3155a52d-668f-5e94-6d39-d65d975d939a")

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
  "count": 21,
  "next": "http://demo.testpress.in/api/v2.2/admin/batches/?page=2",
  "previous": null,
  "per_page": 20,
  "results": [
    {
      "id": 33,
      "name": "TNPSC DEMO EXAM BATCH",
      "url": "http://demo.testpress.in/api/v2.2/admin/batches/33/"
    },
    {
      "id": 32,
      "name": "Orient Ias Test Batch",
      "url": "http://demo.testpress.in/api/v2.2/admin/batches/32/"
    },
    {
      "id": 31,
      "name": "Super Profs Test batch",
      "url": "http://demo.testpress.in/api/v2.2/admin/batches/31/"
    },
    {
      "id": 30,
      "name": "Sample new",
      "url": "http://demo.testpress.in/api/v2.2/admin/batches/30/"
    },
    {
      "id": 29,
      "name": "Test Batch",
      "url": "http://demo.testpress.in/api/v2.2/admin/batches/29/"
    },
    {
      "id": 28,
      "name": "9th Students Tambaram 2016",
      "url": "http://demo.testpress.in/api/v2.2/admin/batches/28/"
    },
    {
      "id": 27,
      "name": "8th Standard Tambaram 2016",
      "url": "http://demo.testpress.in/api/v2.2/admin/batches/27/"
    },
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
      "name": "UPSC Morning  Batch",
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
    },
    {
      "id": 17,
      "name": "ECE",
      "url": "http://demo.testpress.in/api/v2.2/admin/batches/17/"
    },
    {
      "id": 16,
      "name": "EEE",
      "url": "http://demo.testpress.in/api/v2.2/admin/batches/16/"
    },
    {
      "id": 15,
      "name": "DISHA BATCH 1",
      "url": "http://demo.testpress.in/api/v2.2/admin/batches/15/"
    },
    {
      "id": 2,
      "name": "Career Anna Test Batch",
      "url": "http://demo.testpress.in/api/v2.2/admin/batches/2/"
    }
  ]
}
```
This endpoint retreives all the batches available in your institute

###HTTP Request

`GET /api/v2.2/admin/batches/`

### Query Parameters

Parameter | Type | Description
--------- | ------- | -----------
q | string | Filters by batch name.

### Fields
Name | Type | Description
-----|------|-------------
id   | int  | The batch unique ID
name | string  | Batch's Name
url  | string | URL to get details of the batch


##Get a single Batch

```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.2/admin/batches/26/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MTgsInVzZXJfaWQiOjE4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzMTEyNzl9.fDF03EIOEoXTyVUA3sN9-biUGhWrzO_NIZo1KYCUkbU'
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://demo.testpress.in/api/v2.2/admin/batches/26/"

headers = {
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MTgsInVzZXJfaWQiOjE4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzMTEyNzl9.fDF03EIOEoXTyVUA3sN9-biUGhWrzO_NIZo1KYCUkbU",
    'cache-control': "no-cache"
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```shell
curl --request GET \
  --url http://demo.testpress.in/api/v2.2/admin/batches/26/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MTgsInVzZXJfaWQiOjE4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzMTEyNzl9.fDF03EIOEoXTyVUA3sN9-biUGhWrzO_NIZo1KYCUkbU' \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("http://demo.testpress.in/api/v2.2/admin/batches/26/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MTgsInVzZXJfaWQiOjE4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzMTEyNzl9.fDF03EIOEoXTyVUA3sN9-biUGhWrzO_NIZo1KYCUkbU");
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('http://demo.testpress.in/api/v2.2/admin/batches/26/');
$request->setMethod(HTTP_METH_GET);

$request->setHeaders(array(
  'postman-token' => 'f4169b65-54de-6ae9-cd88-aefbed547762',
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

```javascript
var http = require("http");

var options = {
  "method": "GET",
  "hostname": "demo.testpress.in",
  "port": null,
  "path": "/api/v2.2/admin/batches/26/",
  "headers": {
    "content-type": "application/json",
    "authorization": "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzNDI4NTB9.Dsc2NZ_q0e3GRaBTArgwkPs81RbQEt-FnH0u_TBs2hc",
    "cache-control": "no-cache",
    "postman-token": "1864d84e-3ca4-5ea6-e8a4-ae1255d4dfa4"
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
  .url("http://demo.testpress.in/api/v2.2/admin/batches/26/")
  .get()
  .addHeader("content-type", "application/json")
  .addHeader("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzNDI4NTB9.Dsc2NZ_q0e3GRaBTArgwkPs81RbQEt-FnH0u_TBs2hc")
  .addHeader("cache-control", "no-cache")
  .addHeader("postman-token", "46709ba6-3acc-5146-7ec9-3831296a9706")
  .build();

Response response = client.newCall(request).execute();
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

    url := "http://demo.testpress.in/api/v2.2/admin/batches/26/"

    payload := strings.NewReader("{\n    \"username\": \"admin15\",\n    \"password\": \"demouser\",\n    \"first_name\": \"Cool\",\n    \"last_name\": \"dude\",\n    \"email\": \"cool@dude.com\",\n    \"birth_date\": \"03/07/2016\",\n    \"gender_code\": \"trans\",\n    \"state_code\": \"IN-TN\"\n}")

    req, _ := http.NewRequest("GET", url, payload)

    req.Header.Add("content-type", "application/json")
    req.Header.Add("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzNDI4NTB9.Dsc2NZ_q0e3GRaBTArgwkPs81RbQEt-FnH0u_TBs2hc")
    req.Header.Add("cache-control", "no-cache")
    req.Header.Add("postman-token", "fa463bee-bff9-2c2e-3ff0-1828417d1b82")

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
  "id": 26,
  "name": "UPSC Evening Batch",
  "url": "http://demo.testpress.in/api/v2.2/admin/batches/26/"
} 
```
This endpoint retreives details of single batch

###HTTP Request

`GET /api/v2.2/admin/batches/<id>`

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the batch to retrieve


##Create a batch
```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.2/admin/batches/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MTgsInVzZXJfaWQiOjE4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzMTEyNzl9.fDF03EIOEoXTyVUA3sN9-biUGhWrzO_NIZo1KYCUkbU'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"name\": \"Online Test Batch\"\n}"

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://demo.testpress.in/api/v2.2/admin/batches/"
payload = "{\n    \"name\": \"Online Test Batch\"\n}"

headers = {
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MTgsInVzZXJfaWQiOjE4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzMTEyNzl9.fDF03EIOEoXTyVUA3sN9-biUGhWrzO_NIZo1KYCUkbU",
    'cache-control': "no-cache"
    }

response = requests.request("POST", url, headers=headers)

print(response.text)
```

```shell
curl --request POST \
  --url http://demo.testpress.in/api/v2.2/admin/batches/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MTgsInVzZXJfaWQiOjE4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzMTEyNzl9.fDF03EIOEoXTyVUA3sN9-biUGhWrzO_NIZo1KYCUkbU' \
  --header 'cache-control: no-cache' \
  --data '{\n    "name": "Online Test Batch"\n}'
```

```csharp
var client = new RestClient("http://demo.testpress.in/api/v2.2/admin/batches/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MTgsInVzZXJfaWQiOjE4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzMTEyNzl9.fDF03EIOEoXTyVUA3sN9-biUGhWrzO_NIZo1KYCUkbU");
request.AddParameter("application/json", "{\n    \"name\": \"Online Test Batch\"\n}", ParameterType.RequestBody);

IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('http://demo.testpress.in/api/v2.2/admin/batches/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'postman-token' => 'd6cf4ce2-eb4b-272f-8f8d-165080a65d41',
  'cache-control' => 'no-cache',
  'authorization' => 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzNDI4NTB9.Dsc2NZ_q0e3GRaBTArgwkPs81RbQEt-FnH0u_TBs2hc',
  'content-type' => 'application/json'
));

$request->setBody('{
    "name": "Online Test Batch"
}');

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```javascript
var http = require("http");

var options = {
  "method": "POST",
  "hostname": "demo.testpress.in",
  "port": null,
  "path": "/api/v2.2/admin/batches/",
  "headers": {
    "content-type": "application/json",
    "authorization": "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzNDI4NTB9.Dsc2NZ_q0e3GRaBTArgwkPs81RbQEt-FnH0u_TBs2hc",
    "cache-control": "no-cache",
    "postman-token": "4428c61c-5276-290f-164d-9d817c1428bf"
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

req.write(JSON.stringify({ name: 'Online Test Batch' }));
req.end();
```

```java
OkHttpClient client = new OkHttpClient();

MediaType mediaType = MediaType.parse("application/json");
RequestBody body = RequestBody.create(mediaType, "{\n    \"name\": \"Online Test Batch\"\n}");
Request request = new Request.Builder()
  .url("http://demo.testpress.in/api/v2.2/admin/batches/")
  .post(body)
  .addHeader("content-type", "application/json")
  .addHeader("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzNDI4NTB9.Dsc2NZ_q0e3GRaBTArgwkPs81RbQEt-FnH0u_TBs2hc")
  .addHeader("cache-control", "no-cache")
  .addHeader("postman-token", "9d0d627c-b0fc-833f-0c24-c15da1278f82")
  .build();

Response response = client.newCall(request).execute();
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

    url := "http://demo.testpress.in/api/v2.2/admin/batches/"

    payload := strings.NewReader("{\n    \"name\": \"Online Test Batch\"\n}")

    req, _ := http.NewRequest("POST", url, payload)

    req.Header.Add("content-type", "application/json")
    req.Header.Add("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAzNDI4NTB9.Dsc2NZ_q0e3GRaBTArgwkPs81RbQEt-FnH0u_TBs2hc")
    req.Header.Add("cache-control", "no-cache")
    req.Header.Add("postman-token", "447f5740-7bc0-1d00-5b14-7f5f9e75cb95")

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
    "id": 28, 
    "name": "Online Test Batch", 
    "url": "http://demo.testbench.in:8000/api/v2.2/admin/batches/28/"
} 
```
This endpoint creates a new batch in your institute

###HTTP Request

`POST /api/v2.2/admin/batches/`

### Response Fields
Name | Type | Description
-----|------|-------------
id   | int  | Unique ID for the created Batch
name | string  | Batch's Name
url  | string | URL to get details of the batch
