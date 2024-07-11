# lendsqrAdjutorAPI
Task 1,3 & 4 
https://docs.google.com/document/d/15fH2I0viuSxs51047R1rgg-W64JEmEiKD2vwIUQUKlU/edit 

Task 2
Summary of Test Results for Lendsqr Adjutor APIs

Overview
The tests were conducted on the Login and Retrieving API key functionalities of the Lendsqr Adjutor APIs. The main objective was to assess the response times, validate the HTTP status codes, and detect potential security vulnerabilities.

Test Scenarios
Login API:

  Login with valid details
  Login with unregistered email
  Login with wrong password
  Login with omitting email field
  Login with omitting password field

Retrieve API key API:

  Retrieve API key with authentication
  Retrieve API key without authentication
  Retrieve API key with unauthorized user token
  Retrieve API key with invalid token

Performance Inference
Response Time Analysis:

Login API:

  Login with valid details: 350ms
  Login with unregistered email: 150ms
  Login with wrong password: 120ms
  Login with omitting email field: 120ms
  Login with omitting password field: 150ms

Retrieve API key API:

  Retrieve API key with authentication: 220ms
  Retrieve API key without authentication: 120ms
  Retrieve API key with unauthorized user token: 190ms
  Retrieve API key with invalid token: 170ms

Inference:

  The response times for all tested endpoints were within an acceptable range, generally under 500ms.
  The response times were consistent, indicating no significant performance bottlenecks.

Security Vulnerabilities Identified

  The API exposed sensitive details like email, apiKey and userID in the response payload.
  The API had no rate limit, allowing for unlimited logging in to the app.
  Some sensitive data returned by the API endpoint was not encrypted; instead, it was written in plaintext.
  The API did not enforce multi-factor authentication for user logins.


Recommendations for Improvement

  Enforce multi-factor authentication (MFA).
  Ensure API responses only include necessary data.
  Encrypt sensitive information.
  Implement rate limiting.
  Use API gateways for managing rate limits.

Conclusion
The Lendsqr Adjutor APIs performed well in terms of response times and reliability. However, several security vulnerabilities were identified that need to be addressed to ensure the APIs are secure and resilient against potential attacks. Implementing the recommended improvements will enhance both the performance and security of the APIs.



#Automated Test Script 
Testing tool - Postman

Steps 

1. Download the collection and the environment attached to this project.
2. Setting Up Postman
Install Postman: If you haven’t already, download and install Postman using the link https://www.postman.com/downloads/.
3. Import the Collection:
  * Click the “Import” button on the top left.
  * Upload a collection file (Lendsqr_Adjutor_API.postman_collection.json).
4. Import an Environment:
  * Click the “Import” button on the top left.
  * Upload an environment file (Lendsqr_adjutor_API.postman_environment.json).
5. Run the Collection
  * Collection Runner:
    * Click on the “Runner” button (usually located in the bottom right corner).
    * Select the collection you want to run.
    * Choose the environment you want to use.
    * Configure other options like iteration count, delay, and data files if needed.
    * Click “Run”.
6. Analyze Test Results
  Review Results:
    After the collection run completes, review the results to see which tests passed or failed.
    Postman provides detailed logs for each request, including the request and response data.
