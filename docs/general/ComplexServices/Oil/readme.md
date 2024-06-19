# Oil Service API Documentation

This document outlines the flow for using the Oil Service APIs, including retrieving available filters, selecting oil brands, finding providers, and placing service requests.

## 1. Retrieve Available Filters

### Endpoint
`GET /api/General/Services/Products/Filters/{id}`

### Description
Retrieves available filters for the oil service identified by `{id}`.

### Request Parameters
- `id` (required): The ID of the oil service.

### Response Parameters
- `Data`: An array of filter objects containing:
  - `id`: The ID of the filter.
  - `name`: The name of the filter.
  - `...`

## 2. Retrieve Oil Brands

### Endpoint
`GET /api/General/Services/Products/Brands/{id}`

### Description
Fetches all the brands for a specified oil service, including their IDs, names, and descriptions.

### Request Parameters
- `id` (required): The ID of the oil service.

### Response Parameters
- `Data`: An array of brand objects containing:
  - `id`: The ID of the brand.
  - `name`: The name of the brand.
  - `...`

## 3. Retrieve Available Providers

### Endpoint
`POST /api/General/Services/Request/Providers`

### Description
Fetches available providers for the selected oil filter and brand.

### Request Body Parameters
- `[id]` (required): List of the selected products. You must pass also the id of the selected filters from step 1

### Response Parameters
- `Data`: An array of provider objects.

## 4. Pick Schedule for the Service

### Endpoint
`POST /api/General/Services/Request/PickScheduleService`

### Description
Selects the schedule for the service request if the `allow_appointment` parameter is `true`.

### Request Body Parameters
- Various parameters required for scheduling the service (refer to the specific API documentation).

### Response Parameters
- `Data`: Contains details of the selected schedule.

## 5. Confirm Service Request

### Endpoint
`POST /api/Customer/Orders/AddNewRequest`

### Description
Confirms and creates a new service request.

### Request Body Parameters
- Various parameters required for creating the service request (refer to the specific API documentation).

### Response Parameters
- `Data`: Contains the ID of the newly created request.

## Important Parameters in Master Services Object

### `allow_appointment`
- If `true`, proceed to pick a schedule using `POST /api/General/Services/Request/PickScheduleService`. Otherwise, go directly to the confirmation page.

## Flow Summary

1. **Retrieve Available Filters**:
   - Use `GET /api/General/Services/Products/Filters/{id}` to get available filters for the oil service.
2. **Retrieve Oil Brands**:
   - Use `GET /api/General/Services/Products/Brands/{id}` to get brands for the oil service.
3. **Retrieve Providers**:
   - Use `POST /api/General/Services/Request/Providers` to get available providers for the selected filter and brand.
4. **Check Appointment Requirement**:
   - If `allow_appointment` is `true`, proceed to pick a schedule using `POST /api/General/Services/Request/PickScheduleService`. Otherwise, go directly to the confirmation page.
5. **Confirm Service Request**:
   - Use `POST /api/Customer/Orders/AddNewRequest` to confirm and create the service request.

This documentation provides a comprehensive guide to the flow for using the Oil Service APIs. Follow the steps and use the provided endpoints to successfully create and manage service requests.
