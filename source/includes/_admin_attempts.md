# Attempt 
Allows a user to take an exam. User would be redirected to testpress page where users can attempt an exam. Once user completes the exam, Testpress would invoke the surl given in Post Parameter

## Create an attempt by checksum

Allows a user to take an exam. User would be redirected to testpress page where users can attempt an exam. Once user completes the exam, Testpress would invoke the surl given in Post Parameter

### HTTP Request

`POST <exam_url>`

exam_url can be taken from Testpress dashboard. Once an exam is created, URL can be copied from Exam's List Page

### Fields

Name | Type | Description
-----|------|-------------
key | string | Public Institute key provided by Testpress to identify the Institute
email | string | Email Address of the user
first_name | string | First name of the user
institute_attempt_id | string | It is the reference number generated at your End (Institute's End). It is an identifier used to track a particular attempt. If an attempt using a particular attempt id has already successfully completed, the usage of same attempt Id would fail 
checksum | string | checksum generated using the below algorithm
success_url | url | Url to be invoked by Testpress after successfull completion of the exam
failure_url | url | Url to be invoked in case of any any errors

<aside class="info">
<strong> How to create Checksum </strong>
<br>
Hash is a crucial parameter -- used specifically to avoid any tampering during the request

<br>

For hash calculation, you need to generate a string using certain parameters and apply the sha512 algorithm on this string. Please note that you have to use pipe (|) character in between these parameters as mentioned below. The parameter order is mentioned below:

 sha512(key|email|firstname|exam_title|institute_attempt_id|SALT)
 exam_title: Can be retrieved from Testpress dashboard

</aside>


##Response Parameters for Attempt Creation

Below are the response parameters posted by Testpress to Institute when an exam is completed / cancelled

Name | Type | Description
-----|------|-------------
key | string | Public Institute key provided by Testpress to identify the Institute
email | string | Email Address of the user
first_name | string | First name of the user
status | string | completed / cancelled / pending
attempt_id | string | Unique Testpress Id for the Attempt. This will be None if the user has cancelled the attempt and chose "Take Later". This id will be used to review the attempt
institute_attempt_id | string | It is the reference number generated at your End (Institute's End). It is an identifier used to track a particular attempt. If an attempt using a particular attempt id has already successfully completed, the usage of same attempt Id would fail 
checksum | string | checksum generated using the below algorithm

<aside class="info">
<strong> How checksum is created </strong>
<br>
This parameter is absolutely crucial and is similar to the hash parameter used in the attempt create request send by the Institute to Testpress. Testpress calculates the hash using a string of other parameters and returns to the Institute. Institute must verify the hash and then only mark a transaction as success/failure. This is to make sure that the transaction hasn't been tampered with. The calculation is as below:

<br>

 sha512(key|email|firstname|exam_title|institute_attempt_id|attempt_id|SALT)
</aside>

Response also returns json data about the Attempt. Check the right side pane for json data structure

> The above command returns JSON structured like this:

```json
{
  "url": "http://demo.testpress.in/api/v2.2/attempts/125894/",
  "id": 125894,
  "exam": {
    "url": "http://demo.testpress.in/api/v2.2/exams/forum-ias-rbi-demo/",
    "id": 3720,
    "title": "FORUM IAS RBI DEMO",
    "description": "",
    "course": "TNPSC",
    "start_date": "2.25-11-07T12:37:11+05:30",
    "end_date": "2.25-11-15T12:37:11+05:30",
    "duration": "3:00:00",
    "number_of_questions": 200,
    "negative_marks": "0.00",
    "mark_per_question": "1.00",
    "template_type": 2,
    "allow_retake": true,
    "max_retakes": null,
    "enable_ranks": false,
    "rank_publishing_date": null,
    "allow_pdf": false,
    "created": "2.25-11-07T07:07:41.597Z",
    "slug": "forum-ias-rbi-demo",
    "variable_mark_per_question": false,
    "show_answers": true
  },
  "user": "testpress",
  "date": "2.25-11-07T07:12:49.873Z",
  "total_questions": 200,
  "score": "0.00",
  "review_url": "http://demo.testpress.in/api/v2.2/attempts/125894/review/",
  "questions_url": "http://demo.testpress.in/api/v2.2/attempts/125894/questions/",
  "percentile": 0,
  "correct_count": 0,
  "incorrect_count": 0,
  "last_started_time": "2.25-11-07T08:02:46.845Z",
  "remaining_time": "2.20:03",
  "time_taken": "0:49:57",
  "state": "Running",
  "rank": "NA",
  "max_rank": 0,
  "percentage": "0",
  "unanswered_count": 0,
  "commented_questions_count": 0,
  "comments_count": 0,
  "total_bonus": 0
}

```

## Review Exam attempt by checksum

Allows a user to review the exam he has attempted. User would be redirected to testpress page where users can review the exam. User can check the subject wise analytics / time analytics. User can check his correct and incorrect questions. User can post comment / doubts to questions. Also see the comments posted by peer students.

### HTTP Request

`GET /attempts/<id>/`


Name | Type | Description
-----|------|-------------
key | string | Public Institute key provided by Testpress to identify the Institute
email | string | Email Address of the user
first_name | string | First name of the user
checksum | string | checksum generated using the below algorithm
failure_url | url | Url to be invoked in case of any any errors

<aside class="info">
<strong> How checksum is created </strong>
Please note that algorithm is used is different from the previously used algorithms. Please note the usage of time_counter
<br>
sha512(key|email|firstname|institute_attempt_id|attempt_id|time_counter|SALT)

time_counter(Tc) = Tn / S ,

Tn - Number of seconds since epooch.
S - Time Step. Testpress use 3600s as Step time

time_counter is used to restrict the access to the 30 mins time frame. 

If SHA doesn't match, Testpress will check the time counter for Tc - 1 & Tc-2 to avoid any time errors. A link will be active for the maximum of 90 minutes.

</aside>


