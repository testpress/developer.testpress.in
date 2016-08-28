# Attempts
All operations related to user attempt can be done using the following end points.

## Create an attempt by HMAC
* Allows a user to take an exam in a seamless manner from your own website. 
* The flow will be similar to that of making a purchase using a payment gateway. 
* Users would be redirected to testpress page where users can attempt an exam. 
* Once user completes the exam, Testpress would redirect to the success url (`surl`) given in `POST` Parameter

### HTTP Request

`POST <exam_url>`

`exam_url` can be taken from Testpress Admin dashboard. Once an exam is created, URL can be copied from Exam's List Page

### Fields

Name | Type | Description
-----|------|-------------
email | string | Email Address of the user
first_name | string | First name of the user
institute_attempt_id | string | Unique reference string generated at your end (Institute's end). This can be used to track a particular attempt.
key | string | Public institute key provided by Testpress to identify the Institute
time | string | Time since epoch used during the HMAC creation
hmac | string | HMAC generated using the below algorithm
surl | url | Percentage encoded URL to be called by Testpress after successful completion of the exam

### How to create HMAC

HMAC (Hash-based message authentication code) is used to avoid tampering during the request flow. We use a time based HMAC algorithm to limit the lifetime of the HMAC.

The HMAC is calculated using the following algorithm:

* Get the values of 'email', 'first_name', 'institute_attempt_id', 'key', 'time'
* Percentage encode the values
* `time` will be time since epoch in *seconds*
* Create a string by appending the above percentage encoded values using `|` pipe character. *Maintain the same order while appending (uses alphabetical order of the keys)*
* Calculate the HMAC using HMAC-SHA256 with the secret
* Secret can be received from the admin dashboard

message = email|first_name|institute_attempt_id|key|time
hmac.new(secret, message, hashlib.sha256).hexdigest()

```python
import hashlib, hmac, time
epoch_time = int(time.time())
message = '|'.join([email, exam_title, first_name, institute_attempt_id, key, epoch_time ])
return hmac.new(secret, message, hashlib.sha256).hexdigest()
```

<aside class="info">
<strong> Usage of time </strong><br>

The epoch time limits the validity of the HMAC. We have a *30 minute* delta to ensure the validity of the HMAC. 
For ex: if the HMAC was generated at 10.30 AM, it will be valid only for the next 30 minutes and can be used to start an attempt only till 11.00 AM.

</aside>


##Response Parameters for Attempt Creation

Below are the response parameters posted by Testpress to Institute when an exam is completed / cancelled

Name | Type | Description
-----|------|-------------
email | string | Email Address of the user
first_name | string | First name of the user
attempt_id | string | Unique Testpress Id for the Attempt. This id will be used to review the attempt
institute_attempt_id | string | Unique reference string generated and passed during attempt creation
total_count | string | Total number of questions in the Exam
correct_count | string | Total number of correct attempts by the user
incorrect_count | string | Total number of incorrect attempts
unanswered_count | string | Total number of unattemptted questions
score | string | Score gained by the student
max_score | string | Maximum grade for the test
rank | string | Student's rank. Rank will be set only if the ranks are enabled for the exam
max_rank | string | Total number of students attemptted the exam
percentage | string | Score percentage
status | string | completed / cancelled / pending
hmac | string | HMAC generated using above algorithm


## Review Exam attempt by HMAC

* Allows a user to review the exam he has attempted. 
* User would be redirected to testpress page where users can review the exam.
* User can check the subject wise analytics / time analytics, correct and incorrect questions. 
* Comments/doubts can be posted by user to questions and can also see comments posted by peer students.

### HTTP Request

`GET /attempts/?id=<id>&hmac=<hmac>&time=<time>`


Name | Type | Description
-----|------|-------------
id | string | Attempt ID provided by testpress
hmac | string | HMAC generated using the above algorithm
time | string | Time since epoch used during the HMAC creation
