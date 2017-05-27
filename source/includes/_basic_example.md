# Basic Example
Following is a basic example of test taking flow

1. Get the Auth token to authenticate the user using the [Get Auth Token](#authentication) API.
2. Use the token as Authorization header in the following requests.
3. Now try to get list of exams using the [Get Available Exams](#get-available-exams) API.
4. Get exam details of an exam in the list of exams using the [Get Exam Details](#get-a-single-exam) API.
5. Start a new attempt for the exam using the [Create an attempt](#create-an-attempt) API.
6. Using the response of the new attempt, get the questions for that attempt using the [Get attempt questions](#get-attempt-questions) API.
7. Attend the questions by updating the selected answers or review later flag using [Update attempt questions](#update-attempt-questions) API.
8. Send heart beat every 1 minute using [Send Heart Beat](#send-heart-beat) API.
9. [End the attempt](#end-an-attempt) once all the required questions have been attempted.
10. Review the solutions of the completed attempt using [Get Review Questions](#review-attempt-questions) API.
11. Review the subject wise analytics of the completed attempt using [Get Attempt Subject Wise Analytics](#attempt-subject-wise-analytics) API.

## To retake the attempt

1. Get list of attempted exams using the [Get History Exams](#get-history-exams) API.
2. Get the attempts of an exam in the history exams list using [Get Attempts of an Exam](#get-all-attempts-of-an-exam) API.
3. Perform the above steps 4 to 11
