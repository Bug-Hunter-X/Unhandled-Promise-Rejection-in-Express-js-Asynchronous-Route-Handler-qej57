# Unhandled Promise Rejection in Express.js Asynchronous Route Handler

This repository demonstrates a common error in Express.js applications:  unhandled promise rejections within asynchronous route handlers.  The `bug.js` file shows an example where an asynchronous operation (`someAsyncOperation`) might fail, but the error is not caught, potentially causing the server to crash silently or return an incomplete/incorrect response.

The solution, shown in `bugSolution.js`, demonstrates how to properly handle these rejections using `.catch()` to gracefully manage errors and respond appropriately to the client.

## How to Reproduce

1. Clone this repository.
2. Run `npm install express` to install the required dependency.
3. Run `node bug.js`.  Observe that the server might start, but if an error occurs during the asynchronous operation, it will likely crash without a clear error message in the console.
4. Run `node bugSolution.js`.  Observe that the server handles the error gracefully and logs it to the console.