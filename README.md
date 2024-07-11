# lendsqrAdjutorAPI

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
Steps to take
1. Setting Up Postman
Install Postman: If you haven’t already, download and install Postman using the link https://www.postman.com/downloads/.
2. Import the Collection
2. Import the collection and the environment into postman
3. Change the environment to the lendsqr_adjuto_api
4. Click on the collection folder to view its details
5. Click on the run button 
