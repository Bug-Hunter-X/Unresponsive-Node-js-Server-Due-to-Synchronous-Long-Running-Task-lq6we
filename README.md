# Unresponsive Node.js Server

This repository demonstrates a common issue in Node.js where a long-running synchronous operation in the request handler blocks the event loop, causing the server to become unresponsive.  The `bug.js` file contains the problematic code, while `bugSolution.js` shows the corrected version using asynchronous operations.

## Problem

Node.js is single-threaded.  If a request handler performs a lengthy synchronous task, it blocks the event loop, preventing other requests from being processed. This leads to an unresponsive server.

## Solution

Use asynchronous operations (e.g., `setTimeout`, promises, async/await) to avoid blocking the event loop. This allows the server to handle other requests concurrently.