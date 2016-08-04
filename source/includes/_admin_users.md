# Users
Admin Users API gives you access to create/edit users in the institute.

## Create User

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

    payload := strings.NewReader("{\n    \"username\": \"lorem\",\n    \"password\": \"ipsum1$\",\n    \"first_name\": \"John\",\n    \"last_name\": \"Appleseed\",\n    \"email\": \"test@example.com\",\n    \"birth_date\": \"03/07/2016\",\n    \"gender_code\": \"male\",\n    \"state_code\": \"IN-TN\"\n}")

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

```ruby
require 'uri'
require 'net/http'

url = URI("http://demo.testpress.in/api/v2.2/admin/users/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request["authorization"] = 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAyMjk2MDd9.ynLE30wWup2CXMqgpNjT4ZBAUAtttqebzat-stuVB84'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"username\": \"lorem\",\n    \"password\": \"ipsum1$\",\n    \"first_name\": \"Lorem\",\n    \"last_name\": \"ipsum1$\",\n    \"email\": \"test@example.com\",\n    \"birth_date\": \"03/07/1987\",\n    \"gender_code\": \"male\",\n    \"state_code\": \"IN-TN\"\n}"

response = http.request(request)
puts response.read_body
```

```shell
curl --request POST \
  --url http://demo.testpress.in/api/v2.2/admin/users/ \
  --header 'authorization: JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAyMjk2MDd9.ynLE30wWup2CXMqgpNjT4ZBAUAtttqebzat-stuVB84' \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json' \
  --data '{"username": "lorem", "password": "ipsum1$", "first_name": "John", "last_name": "Appleseed", "email": "test@example.com", "birth_date": "03/07/2016", "gender_code": "male", "state_code": "IN-TN"}'
```

```python
import requests

url = "http://demo.testpress.in/api/v2.2/admin/users/"

payload = "{\n    \"username\": \"lorem\",\n    \"password\": \"ipsum1$\",\n    \"first_name\": \"John\",\n    \"last_name\": \"Appleseed\",\n    \"email\": \"test@example.com\",\n    \"birth_date\": \"03/07/2016\",\n    \"gender_code\": \"male\",\n    \"state_code\": \"IN-TN\"\n}"
headers = {
    'content-type': "application/json",
    'authorization': "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAyMjk2MDd9.ynLE30wWup2CXMqgpNjT4ZBAUAtttqebzat-stuVB84",
    'cache-control': "no-cache",
    }

response = requests.request("POST", url, data=payload, headers=headers)

print(response.text)
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
RequestBody body = RequestBody.create(mediaType, "{\n    \"username\": \"lorem\",\n    \"password\": \"ipsum1$\",\n    \"first_name\": \"John\",\n    \"last_name\": \"Appleseed\",\n    \"email\": \"test@example.com\",\n    \"birth_date\": \"03/07/2016\",\n    \"gender_code\": \"male\",\n    \"state_code\": \"IN-TN\"\n}");
Request request = new Request.Builder()
  .url("http://demo.testpress.in/api/v2.2/admin/users/")
  .post(body)
  .addHeader("content-type", "application/json")
  .addHeader("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAyMjk2MDd9.ynLE30wWup2CXMqgpNjT4ZBAUAtttqebzat-stuVB84")
  .addHeader("cache-control", "no-cache")
  .build();

Response response = client.newCall(request).execute();
```

```csharp
var client = new RestClient("http://demo.testpress.in/api/v2.2/admin/users/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MzgsInVzZXJfaWQiOjM4LCJlbWFpbCI6ImRpbmVzaEB0ZXN0cHJlc3MuaW4iLCJleHAiOjE0NzAyMjk2MDd9.ynLE30wWup2CXMqgpNjT4ZBAUAtttqebzat-stuVB84");
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\n    \"username\": \"lorem\",\n    \"password\": \"ipsum1$\",\n    \"first_name\": \"John\",\n    \"last_name\": \"Appleseed\",\n    \"email\": \"test@example.com\",\n    \"birth_date\": \"03/07/2016\",\n    \"gender_code\": \"male\",\n    \"state_code\": \"IN-TN\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
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
  state_code: 'IN-TN' }));
req.end();
```

> The above command returns JSON structured like this:

```json
{
  "id": 1889,
  "username": "lorem",
  "first_name": "John",
  "last_name": "Appleseed",
  "email": "test@example.com",
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

This endpoint creates a user.

### HTTP Request

`POST /api/v2.2/admin/users/`

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

