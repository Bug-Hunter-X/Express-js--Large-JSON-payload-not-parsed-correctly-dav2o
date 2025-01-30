# Express.js - Large JSON Payload Parsing Issue

This repository demonstrates a bug in an Express.js application where large JSON payloads are not parsed correctly when using body-parser. The issue manifests as an empty `req.body` object, leading to errors in the application's data processing logic.

## Bug Description

The application utilizes `express.json()` for parsing JSON requests. However, when handling requests with large JSON payloads exceeding a certain size limit, the request body remains empty. This results in an error when attempting to access data within `req.body`.

## Solution

The problem is typically caused by limitations in the default settings of the body-parser middleware. The solution involves increasing the `limit` property of the `express.json()` method to accommodate larger JSON payloads.