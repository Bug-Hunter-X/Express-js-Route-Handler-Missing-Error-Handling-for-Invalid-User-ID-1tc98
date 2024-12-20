# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: the lack of proper error handling for invalid input.  Specifically, the provided code attempts to parse a user ID as an integer without first validating that it's a number. This can lead to runtime errors if the ID is not a valid integer.

The `bug.js` file contains the erroneous code, and `bugSolution.js` provides the corrected version with appropriate error handling.

## How to Reproduce

1. Clone this repository.
2. Run `npm install express` to install the necessary dependencies.
3. Run `node bug.js`.
4. Make a request to `/users/abc` or `/users/123x`.  The server will likely crash or return an unexpected result. Then run `node bugSolution.js` and test with the same requests to see the improved error handling. 

## Solution

The solution involves adding input validation to ensure the user ID is a valid number before attempting to parse it.  The corrected code uses `isNaN()` to check for invalid input and returns a 400 Bad Request response if the ID is not a number.   This ensures a more robust and reliable server.