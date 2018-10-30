# Single Sign On (SSO)

This endpoint is used to authenticate the user to get access to private resources in Testpress.

### HTTP Request

`GET /sso/?sig=<hmac-signature>&sso=<payload>`

### Payload
```java
import java.util.Base64;
import java.time.Instant;

public class Payload {
    public static void main(String[] args) {
        // Get the encoder
        Base64.Encoder encoder = Base64.getEncoder();
        Instant instant = Instant.now();
        // Epoch time the number of milliseconds since January 1, 1970, 00:00:00 GMT.
        int epoch_time = (int) instant.getEpochSecond();
        // Query string that needs to be encoded
        String query_string = "email=support@testpress.in&time=" + Integer.toString(epoch_time);
        // Constructing the payload by encoding the query string using Base64
        String payload = encoder.encodeToString(query_string.getBytes());
        System.out.println("Your payload is: " + payload);
}  
```

```python
import base64, time
epoch_time = int(time.time())
query_string = 'email=demo@testpress.in&time='+str(epoch_time)
payload = base64..b64encode(query_string)
print(payload)
```

Payload is basically the query string encoded in base64.

Below are the accepted query strings 

Name | Type | Description
-----|------|-------------
email | string | Email Address of the user
username | string | username of the user
time | string | Time since epoch used during the HMAC creation


### HMAC signature

```java
import java.util.Base64;
import java.time.Instant;
import javax.crypto.Mac;
import javax.crypto.spec.SecretKeySpec;
import java.security.NoSuchAlgorithmException;
import java.security.InvalidKeyException;
import javax.xml.bind.DatatypeConverter;

public class HmacSignature {
    public static void main(String[] args) {
        // Get the encoder
        Base64.Encoder encoder = Base64.getEncoder();
        Instant instant = Instant.now();
        // Epoch time the number of milliseconds since January 1, 1970, 00:00:00 GMT.
        int epoch_time = (int) instant.getEpochSecond();
        // Query string that needs to be encoded
        String query_string = "email=support@testpress.in&time=" + Integer.toString(epoch_time);
        // Constructing the payload by encoding the query string using Base64
        String payload = encoder.encodeToString(query_string.getBytes());
        System.out.println("Your payload is: " + payload);
        try {
            // Constructing HMAC Signature
            String secret_key = "the given scret key";
    	    
    	    Mac hasher = Mac.getInstance("HmacSHA256");
    	    hasher.init(new SecretKeySpec(secret_key.getBytes(), "HmacSHA256"));
    	    
    	    byte[] hmac = hasher.doFinal(payload.getBytes());
    	    String signature = DatatypeConverter.printHexBinary(hmac);
    	    String hmac_signature = signature.toLowerCase();
    	    System.out.println("Your HMAC Signature is: " + hmac_signature);
      	}
      	catch (NoSuchAlgorithmException e) {}
      	catch (InvalidKeyException e) {}
	    
    }  
}  
```

```python
import hashlib, hmac, time
epoch_time = int(time.time())
query_string = 'username=student1&time='+str(epoch_time)
payload = base64.b64encode(query_string)
hmac_signature = hmac.new(secret, payload, hashlib.sha256).hexdigest()
print(hmac_signature)
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
