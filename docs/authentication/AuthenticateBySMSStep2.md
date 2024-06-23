### Step 2: Authenticate by SMS (Step 2)

- **Endpoint URL**: `POST /api/Auth/Token/AuthenticateBySMSStep2`

- **Description**: Completes the authentication process by verifying the SMS code received in Step 1.
- **Request Parameters**:
  - `mobileno` (query parameter, required): The mobile number of the user.
  - `step1id` (query parameter, required): The ID received in the response of Step 1.
  - `smscode` (query parameter, required): The SMS code received on the user's mobile.
  - `lng` (header, optional): Language preference (`ar` for Arabic, `en` for English). Default is `ar`.
- **Full Test URL**: `https://satc.live/api/Auth/Token/AuthenticateBySMSStep2?mobileno=966548093416&step1id=14817&smscode=3026`
**Response Parameters**:
- `status` (boolean): Indicates whether the operation was successful.
- `message` (string): A message describing the result of the operation.
- `error` (string): An error message if the operation failed.
- `Data` (string): Customer's token

- **Response Example**:
    ```json
    {
        "status": true,
        "message": "Operation Done Successfully",
        "error": "",
        "Data": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1bmlxdWVfbmFtZSI6IjU0ODA5MzQxNiIsInJvbGUiOiJDdXN0b21lcnMiLCJBZ2VuY3lfSUQiOiIxMDM2OCIsIlVzZXJJZCI6IjIxMzUzIiwibmJmIjoxNzE4MDM3NTY2LCJleHAiOjE3MTgwNDQ3NjYsImlhdCI6MTcxODAzNzU2NiwiaXNzIjoiaHR0cHM6Ly9zYXlhcmF0ZWNoLmNvbS8iLCJhdWQiOiJodHRwczovL3NheWFyYXRlY2guY29tLyJ9.avtv0eTaA4xBYYDzMnMuw2oUGicDvqT08zIu-G6f24E"
    }
    ```
