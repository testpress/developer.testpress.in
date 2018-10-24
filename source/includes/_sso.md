# Single Sign On (SSO)

This endpoint is used to authenticate the user to get access to private resources in Testpress.

### HTTP Request

`GET /sso/?sig=<hmac-signature>&sso=<payload>`

### Payload

```python
import base64, time
epoch_time = int(time.time())
query_string = 'email=demo@testpress.in&time='+str(epoch_time)
payload = base64.encodestring(query_string)
return payload 
```

Payload is basically the query string encoded in base64.

Below are the accepted query strings 

Name | Type | Description
-----|------|-------------
email | string | Email Address of the user
username | string | username of the user
time | string | Time since epoch used during the HMAC creation


### HMAC signature

```python
import hashlib, hmac, time
epoch_time = int(time.time())
query_string = 'username=student1&time='+str(epoch_time)
payload = base64.encodestring(query_string)
return hmac.new(secret, payload, hashlib.sha256).hexdigest()
```

HMAC (Hash-based message authentication code) is used to avoid tampering during the request flow. We use a time based HMAC algorithm to limit the lifetime of the HMAC.

The HMAC is calculated using the following algorithm:

* Get the values of 'secret', 'payload'  encode the values.
* Calculate the HMAC using HMAC-SHA256 with the secret
* Secret can be received from the admin dashboard

hmac.new(secret, payload, hashlib.sha256).hexdigest()

<aside class="info">
<strong> Usage of time </strong><br>

The epoch time limits the validity of the HMAC. We have a *30 minute* delta to ensure the validity of the HMAC. 
For ex: if the HMAC was generated at 10.30 AM, it will be valid only for the next 30 minutes and can be used to start an attempt only till 11.00 AM.

</aside>
