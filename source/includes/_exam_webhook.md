# Exam webhook

## How to create hash

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
* Calculate the HMAC using HMAC-SHA512 with the private key
* Private key can be received from the admin dashboard

hmac.new(secret, message, hashlib.sha512).hexdigest()

## Response Parameters for Attempt after completion
Below are the response parameters posted by Testpress to Institute when an attempt is completed.

Name | Type | Description
-----|------|-------------
email | string | Email Address of the user
username | string | Username of the user
attempt_id | integer | Unique Testpress Id for the Attempt. This id will be used to review the attempt
total_count | integer | Total number of questions in the Exam
correct_answers_count | integer | Total number of correct answers in the attempt
incorrect_answers_count | integer | Total number of incorrect answers in the attempt
unanswered_answers_count | integer | Total number of unattemptted questions in the attempt
score | integer | Total score obtained by the user for the attempt
percentage | integer | Score percentage
key | string | Public institute key provided by Testpress to identify the Institute
hash | string | Hash generated using above algorithm.
