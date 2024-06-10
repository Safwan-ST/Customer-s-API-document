### Step 1: Authenticate by SMS (Step 1)

- **Endpoint URL**: `/api/Auth/Token/AuthenticateBySMSStep1`
- **HTTP Method**: GET
- **Description**: Initiates the authentication process by sending an SMS code to the user's mobile number.
- **Request Parameters**:
  - `mobileno` (query parameter, required): The mobile number of the user.
  - `lng` (header, optional): Language preference (`ar` for Arabic, `en` for English). Default is `ar`.
- **Full Test URL**: `https://satc.live/api/Auth/Token/AuthenticateBySMSStep1?mobileno=966548093416`
- **Response Example**:
    ```json
    {
        "status": true,
        "message": "Operation Done Successfully",
        "error": "",
        "Data": {
            "id_step2": 14817,
            "smscode": "3026"
        }
    }
    ```
