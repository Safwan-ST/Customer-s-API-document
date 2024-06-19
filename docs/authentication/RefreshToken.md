### Refresh Token

**Endpoint**: `POST /api/Auth/Token/refreshToken`

**Description**: Refresh the authentication token, you must call the API if the token expires at the begining of the application so you will use it to get customer data, you have to make sure that the token is expired.

**Headers**:
- `token` (required): The old token that needs to be refreshed.

**Response Parameters**:
- `status`: Indicates if the operation was successful (`true` or `false`).
- `message`: Describes the outcome of the operation.
- `error`: Provides details of any errors encountered during the operation.
- `Data`: Contains additional data related to the operation.
  - `token`: The new authentication token.
  - `expires`: The expiration date and time of the new token.
