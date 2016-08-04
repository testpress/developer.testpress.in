#Batches
Batches API lets you create a new batch in your institute or retreives the details of batches available in your institute.

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

> The above command returns JSON structured like this:

```json
{
    "count": 2, 
    "next": null, 
    "previous": null, 
    "per_page": 20, 
    "results": [
        {
            "id": 26, 
            "name": "UPSC Evening Batch", 
            "url": "http://demo.testbench.in:8000/api/v2.2/admin/batches/26/"
        }, 
        {
            "id": 1, 
            "name": "JIPMER Batch", 
            "url": "http://demo.testbench.in:8000/api/v2.2/admin/batches/1/"
        }
    ]
}
```
This endpoint retreives all the batches available in your institute

###HTTP Request

`GET api/v2_2/admin/batches/`

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


##Get a signle Batch

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

> The above command returns JSON structured like this:

```json
{
    "id": 26, 
    "name": "UPSC Evening Batch", 
    "url": "http://demo.testbench.in:8000/api/v2.2/admin/batches/26/"
} 

```
This endpoint retreives details of single batch

###HTTP Request

`GET api/v2_2/admin/batches/<id>`

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

`POST api/v2_2/admin/batches/`

### Response Fields
Name | Type | Description
-----|------|-------------
id   | int  | Unique ID for the created Batch
name | string  | Batch's Name
url  | string | URL to get details of the batch
