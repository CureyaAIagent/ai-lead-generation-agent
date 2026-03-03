----------
name: api-connector
description: Generic external API integration handler.

input_schema:
  type: object
  properties:
    endpoint:
      type: string
    method:
      type: string
    headers:
      type: object
    payload:
      type: object

output_schema:
  type: object
  properties:
    status_code:
      type: number
    response_body:
      type: object
    error:
      type: string

instructions: |
  Perform HTTP request based on:
  - method (GET, POST, PUT, DELETE)
  - endpoint
  - headers
  - payload

  Handle:
  - Timeout errors
  - 4xx errors
  - 5xx errors

  Return structured JSON response.
  Never log authentication tokens in output.
