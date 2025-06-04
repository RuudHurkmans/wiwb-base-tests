# wiwb-base-tests

This repository contains a collection of request and response cases for testing the WIWB API (versions 1 and 2).

## Test Sets

Each JSON file in the `regression` folder represents a test set:
- `general.json`: General tests for both API versions.
- `fews.json`: Requests sent by FEWS systems.

## Test Case Structure

Each test case is structured as follows:
```json
{
  "name": "Name of request",
  "request": {
    "method": "POST" | "GET",
    "url": "{{base_url}}/api/route/to/test",
    "headers": {
      // Request headers; {{bearer}} will be replaced with the actual token
    },
    "json": {
      // Request body, including readers and exporters
    }
  },
  "expected": {
    "status": 200,                // Expected response code (e.g., 200, 500)
    "body_contains": "TMP",       // Checks if the response body contains the specified key
    "expected_response": { ... }  // Used for checking structure and some values (see below)
  }
}
```

### `expected_response` Parsing

The `expected_response` field is used to check the structure of the response and some of its values. Values that do not need to match exactly can be set as `<masked>` in the `expected_response`.
