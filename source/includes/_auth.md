# Authentication

> To authorize, use this code:

```csharp
var client = new RestClient("https://demo.testpress.in/api/v2.2/auth-token/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\n    \"username\": \"admin\",\n    \"password\": \"demo\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```ruby
re 'uri'
require 'net/http'

url = URI("https://demo.testpress.in/api/v2.2/auth-token/")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"username\": \"testpress\",\n    \"password\": \"demo\"\n}"

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "https://demo.testpress.in/api/v2.2/auth-token/"

payload = "{\n    \"username\": \"testpress\",\n    \"password\": \"demo\"\n}"
headers = {
    'content-type': "application/json",
    'cache-control': "no-cache",
    }

response = requests.request("POST", url, data=payload, headers=headers)

print(response.text)
```

```shell
# With shell, you can just pass the user credentials to get the auth token
curl --request POST \
  --url https://demo.testpress.in/api/v2.2/auth-token/ \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json' \
  --data '{"username": "testpress", "password": "demo"}'
```

> Make sure to replace `testpress` and `demo` with your credentials.
> The above command returns JSON structured like this:

```php
<?php

$request = new HttpRequest();
$request->setUrl('http://demo.testpress.in/api/v2.2/auth-token/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'postman-token' => '6501b66f-d9ec-4a94-0a94-ef81a66a41f3',
  'cache-control' => 'no-cache',
  'authorization' => 'JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MTM5NTYsInVzZXJfaWQiOjEzOTU2LCJlbWFpbCI6ImRlcy5wcm8ubWFkaGFuQGhvdG1haWwuY29tIiwiZXhwIjoxNDY0MzQwMzg1fQ.TElNLpQE8KERVe7Q-vjNk9aU-9prOfzBb43srB9WmC0',
  'content-type' => 'multipart/form-data; boundary=---011000010111000001101001'
));

$request->setBody('-----011000010111000001101001
Content-Disposition: form-data; name="username"

admin
-----011000010111000001101001
Content-Disposition: form-data; name="password"

demo
-----011000010111000001101001--');

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```
```java
OkHttpClient client = new OkHttpClient();

MediaType mediaType = MediaType.parse("multipart/form-data; boundary=---011000010111000001101001");
RequestBody body = RequestBody.create(mediaType, "-----011000010111000001101001\r\nContent-Disposition: form-data; name=\"username\"\r\n\r\nadmin\r\n-----011000010111000001101001\r\nContent-Disposition: form-data; name=\"password\"\r\n\r\ndemo\r\n-----011000010111000001101001--");
Request request = new Request.Builder()
  .url("http://demo.testpress.in/api/v2.2/auth-token/")
  .post(body)
  .addHeader("content-type", "multipart/form-data; boundary=---011000010111000001101001")
  .addHeader("authorization", "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6MTM5NTYsInVzZXJfaWQiOjEzOTU2LCJlbWFpbCI6ImRlcy5wcm8ubWFkaGFuQGhvdG1haWwuY29tIiwiZXhwIjoxNDY0MzQwMzg1fQ.TElNLpQE8KERVe7Q-vjNk9aU-9prOfzBb43srB9WmC0")
  .addHeader("cache-control", "no-cache")
  .addHeader("postman-token", "987488b1-1b5f-dd8b-95fc-fea8d276b2ae")
  .build();

Response response = client.newCall(request).execute();

```

```json
{"token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw"}
```

This endpoint provides an authentication token to get access to private resources in Testpress.

### HTTP Request

`POST http://demo.testpress.in/api/v2.2/auth-token/`

Name | Type | Description
-----|------|-------------
username | string | Username of the user
password | string | Password of the user

<aside class="info">
Replace <code>demo</code> with your institute subdomain hereafter everywhere.
</aside>


### Response
The response will return an token which should be prefixed with <code>JWT</code> and included in all API requests to the server in a header that looks like the following:

`Authorization: JWT auth-token-string`

<aside class="info">
You must replace <code>auth-token-string</code> with the token you got from the response.
</aside>


