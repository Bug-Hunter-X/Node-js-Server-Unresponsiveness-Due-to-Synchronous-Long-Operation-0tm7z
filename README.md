# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js where a long-running synchronous operation within a request handler can block the event loop, making the server unresponsive. The `server.js` file contains the buggy code, while `serverSolution.js` provides a corrected version using asynchronous operations.

## Problem

The original code includes a `while` loop that simulates a 5-second operation.  This operation blocks the event loop, preventing any other requests from being handled during this time.  The server will appear unresponsive for 5 seconds after the first request is received.

## Solution

The solution involves using asynchronous operations such as `setTimeout` or promises to avoid blocking the event loop.  The corrected code uses `setTimeout` to simulate a long operation without blocking the main thread.