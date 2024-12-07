# Express.js Route Handler Missing Error Handling for Invalid User IDs

This repository demonstrates a common error in Express.js route handlers: missing error handling for invalid input.  The example shows a route that fetches a user by ID.  If the ID is not a valid integer, the code throws an error.  The solution demonstrates how to properly handle this situation.

## Bug

The `bug.js` file contains the buggy code.  The `parseInt()` function is used without error checking.  If the request parameter `id` is not an integer, `parseInt()` will return `NaN`, and the `find()` method will not work correctly, potentially causing a crash or unexpected behavior.

## Solution

The `bugSolution.js` file shows the corrected code.  It includes error handling to check if `parseInt(userId)` returns `NaN`, returning a 400 Bad Request response in this case. This prevents the server from crashing and provides a better user experience.