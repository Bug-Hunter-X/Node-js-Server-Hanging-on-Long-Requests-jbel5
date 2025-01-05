# Node.js Server Hanging on Long Requests

This repository demonstrates a common issue in Node.js applications: server hangs due to blocking operations in request handlers.  The example shows a simple HTTP server that simulates a long-running task, causing the server to become unresponsive during that time.

The solution demonstrates how to use asynchronous operations (specifically `setTimeout`) to prevent blocking and keep the server responsive.

## Running the example

1. Clone this repository.
2. Navigate to the project directory.
3. Run `node bug.js` to start the server with the bug.
4. Run `node bugSolution.js` to start the server with the solution.

## Understanding the Issue

Node.js is single-threaded.  When a long-running operation is performed synchronously within a request handler, it blocks the event loop. This prevents other requests from being processed, leading to the server appearing unresponsive or hanging.

## Solution

The solution employs asynchronous programming to avoid blocking the event loop. The use of `setTimeout` ensures the response is sent after the simulated long task is finished without blocking the thread.