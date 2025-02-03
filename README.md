# Node.js Server Unresponsiveness

This repository demonstrates a common Node.js issue: server unresponsiveness caused by blocking the event loop with a long-running synchronous operation. The `server.js` file contains the buggy code, while `serverSolution.js` provides a corrected version using asynchronous operations.

## Bug Description

The server hangs because the `while` loop inside the request handler keeps the CPU busy for 5 seconds. During this time, the event loop is blocked, and no other requests can be processed.  This leads to unresponsive behavior and potential crashes.

## Solution

The solution involves using asynchronous operations to avoid blocking the event loop.  This prevents the server from becoming unresponsive even under heavy load.