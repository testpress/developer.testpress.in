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

```json
{"token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3RwcmVzcyIsInVzZXJfaWQiOjE3LCJlbWFpbCI6InRlc3RwcmVzcy5pbkBnbWFpbC5jb20iLCJleHAiOjE0NDc4MzMyMjl9.Ik_yi4lHbNbrRGhqmRpsW82Nls_O9lgXakk_syV-vSw"}
```

This endpoint provides an authentication token to get access to private resources in Testpress.

### HTTP Request

`POST http://demo.testpress.in/api/v2.2/auth-token/`

<aside class="info">
Replace <code>demo</code> with your institute subdomain hereafter everywhere.
</aside>


### Response
The response will return an token which should be prefixed with <code>JWT</code> and included in all API requests to the server in a header that looks like the following:

`Authorization: JWT auth-token-string`

<aside class="info">
You must replace <code>auth-token-string</code> with the token you got from the response.
</aside>


