# Exam webhook

## Data posted to the exam webhook URL 

> Below is the sample json data posted to the exam webhook URL:

```json
{
 "username": "test_user",
 "hash": "815aad5656f99ac131ab1ab57f1044c6c1c656b2a7f13b41feca74fd48a603f94a7024d6835204e463fbd79f6a4",
 "exam": {
  "duration": "0:30:00",
  "start_date": "2019-01-21T12:52:41.075Z",
  "id": 2,
  "end_date": "2019-03-21T12:52:41.075Z",
  "title": "test_exam"
 },
 "partial_correct_answers_count": "0",
 "attempt_id": "93",
 "key": "sxe7uKykEUT7WSnh",
 "speed": "960",
 "percentage": "100",
 "correct_answers_count": "50",
 "user_id": "3",
 "score": "50",
 "unanswered_answers_count": "0",
 "incorrect_answers_count": "0",
 "email": "test_user@gmail.com",
 "accuracy": "100"
}
```
Below are the response parameters posted by Testpress to Institute when an attempt is completed.

Name | Type | Description
-----|------|-------------
email | string | Email Address of the user
username | string | Username of the user
attempt_id | integer | Unique Testpress Id for the Attempt. This id will be used to review the attempt
exam | key/value pair | This key/value pair will contain exam details like "id", "title", "start_date", "end_date", "duration". 
total_count | integer | Total number of questions in the Exam
correct_answers_count | integer | Total number of correct answers in the attempt
incorrect_answers_count | integer | Total number of incorrect answers in the attempt
unanswered_answers_count | integer | Total number of unattemptted questions in the attempt
score | integer | Total score obtained by the user for the attempt
percentage | integer | Score percentage
key | string | Public institute key provided by Testpress to identify the Institute
hash | string | Hash generated using above algorithm.

In the above data `hash` value is used to identify that the data is indeed posted from testpress.

## How to generate the hash and verify the authenticity of the data

```python
import hashlib, hmac
message = '|'.join(
    [institute.public_key, str(user_exam.id),
     str(user_exam.correct_answers_count),
     str(institute.private_key),
     str(user_exam.incorrect_answers_count),
     str(user_exam.unanswered_count), str(user_exam.percentage),
     str(user_exam.score), str(user_exam.user_id)]
)
return hmac.new(secret, message, hashlib.sha256).hexdigest()
```

HMAC (Hash-based message authentication code) is used to avoid tampering during the request flow.

The hash is calculated using the following algorithm:

* Get the values of 'public_key', 'attempt_id', 'correct_answers_count', 'private_key', 'incorrct_answers_count', 'unanswered_count', 'percentage', 'score', 'user_id'
* Create a string by appending the above percentage encoded values using `|` pipe character. *Maintain the same order while appending*
* Calculate the HMAC using HMAC-SHA512 with the private key.
* Private key can be taken from the admin dashboard.

hmac.new(secret, message, hashlib.sha512).hexdigest()
