# Errors

The Fabricut API uses the following error codes:

Error Code | Meaning
---------- | -------
400 | Bad Request -- Request could not be understood by the server due to malformed syntax
401 | Unauthorized -- Invalid API key
403 | Forbidden -- Access to specific object(s) denied
404 | Not Found -- Object not found
405 | Method Not Allowed -- You tried to access a object with an invalid method
406 | Not Acceptable -- You requested a format that isn't JSON
410 | Gone -- The object requested has been removed from our servers
422 | Unprocessable Entity -- Request understood but invalid
429 | Too Many Requests -- You're hitting the request rate limits
500 | Internal Server Error -- We had a problem with our server. Try again later.
503 | Service Unavailable -- We're temporarily offline for maintenance. Please try again later.
