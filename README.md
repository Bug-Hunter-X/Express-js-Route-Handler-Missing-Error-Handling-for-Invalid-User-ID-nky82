# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: the lack of error handling for invalid input.  Specifically, the `/users/:id` route attempts to parse the `id` parameter as an integer without checking for potential errors (e.g., non-numeric input). This can lead to unexpected crashes or incorrect responses.

## Bug

The `bug.js` file contains the faulty code.  It attempts to access a user using the provided ID, but doesn't validate if the ID is a valid number.  If a non-numeric ID is provided, `parseInt(userId)` will return `NaN`, leading to an error (or potentially unexpected results).

## Solution

The `bugSolution.js` file provides a corrected version.  It includes explicit checks to ensure the ID is a number before attempting to parse it, adding robustness and preventing unexpected behavior.

## How to Run

1. Clone this repository.
2. Run `npm install express` to install dependencies.
3. Run `node bug.js` (or `node bugSolution.js`) to execute the code.
4. Try accessing `/users/1` and `/users/abc` to observe the difference.