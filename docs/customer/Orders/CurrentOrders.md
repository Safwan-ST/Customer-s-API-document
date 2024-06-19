### Get Current Non-Closed Bookings

**Endpoint**: `POST /api/Customer/Orders/Current`

**Description**: Retrieves the current non-closed bookings to follow up.

**Authentication**: Requires Bearer Token Authentication in the header.

**Response Parameters**:
- `status` (boolean): Indicates whether the operation was successful.
- `message` (string): A message describing the result of the operation.
- `error` (string): An error message if the operation failed.
- `Data` (array): A list of current non-closed bookings.
  - `id` (integer): Booking ID.
  - `provider_id` (integer): Provider ID.
  - `provier_name` (string): Provider name.
  - `provier_eng_name` (string): Provider name in English.
  - `master_service_id` (integer): Master service ID.
  - `service_name` (string): Service name.
  - `service_eng_name` (string): Service name in English.
  - `is_prepaid` (boolean): Indicates if the service is prepaid.
  - `total` (decimal): Total amount for the service.
  - `prepaid_amount` (decimal): Prepaid amount.
  - `total_topay` (decimal): Total amount to pay.
  - `is_simple_service` (boolean): Indicates if it is a simple service.
  - `is_for_vehicle_repair` (boolean): Indicates if it is for vehicle repair.
  - `is_for_oil` (boolean): Indicates if it is for oil service.
  - `is_for_tires` (boolean): Indicates if it is for tires service.
  - `is_for_battaries` (boolean): Indicates if it is for batteries service.
  - `is_package_service` (boolean): Indicates if it is a package service.
  - `is_shipping_service` (boolean): Indicates if it is a shipping service.
  - `is_for_pickup` (boolean|null): Indicates if it is for pickup service.
  - `service_img` (string|null): Service image URL.
  - `require_appointment` (boolean): Indicates if an appointment is required.
  - `service_master_group_id` (integer): Service master group ID.
  - `service_master_group_name` (string): Service master group name.
  - `service_master_group_eng_name` (string): Service master group name in English.
  - `is_need_customer_action` (boolean): Indicates if customer action is needed.
  - `booked_date` (string): Booked date.
  - `booked_time` (string): Booked time.
  - `is_invoice_uploaded` (boolean): Indicates if the invoice is uploaded.
  - `can_reset_schedule` (boolean): Indicates if the schedule can be reset.
  - `can_cancel` (boolean): Indicates if the booking can be canceled.
  - `is_canceled` (boolean): Indicates if the booking is canceled.
  - `cancel_reason_id` (integer|null): Cancel reason ID.
  - `cancel_reason` (string|null): Cancel reason.
  - `cancel_eng_reason` (string|null): Cancel reason in English.
  - `car_info` (object): Information about the car.
    - `car_profile_id` (integer): Car profile ID.
    - `car_vendor_id` (integer): Car vendor ID.
    - `car_vendor_name` (string): Car vendor name.
    - `car_vendor_eng_name` (string): Car vendor name in English.
    - `car_model_id` (integer): Car model ID.
    - `car_model_name` (string): Car model name.
    - `car_model_eng_name` (string): Car model name in English.
    - `car_color_id` (integer): Car color ID.
    - `car_color_name` (string): Car color name.
    - `car_color_eng_name` (string): Car color name in English.
    - `car_year` (integer): Car year.
    - `car_cylender_name` (integer): Car cylinder name.
  - `status_id` (integer): Status ID.
  - `status_name` (string): Status name.
  - `status_eng_name` (string): Status name in English.
  - `shipping_address` (string|null): Shipping address.
  - `shipping_courier` (string|null): Shipping courier.
- `total` (decimal): Total amount for all bookings.

**Response Example**:
```json
{
  "status": true,
  "message": "تمت العمليه بنجاح",
  "error": "",
  "Data": [
    {
      "id": 16964,
      "provider_id": 10031,
      "provier_name": "sayaratech",
      "provier_eng_name": "sayaratech",
      "master_service_id": 10022,
      "service_name": "غسيل اكسبريس",
      "service_eng_name": "Express Wash",
      "is_prepaid": true,
      "total": 140,
      "prepaid_amount": 0,
      "total_topay": 140,
      "is_simple_service": true,
      "is_for_vehicle_repair": false,
      "is_for_oil": false,
      "is_for_tires": false,
      "is_for_battaries": false,
      "is_package_service": false,
      "is_shipping_service": false,
      "is_for_pickup": null,
      "service_img": null,
      "require_appointment": true,
      "service_master_group_id": 1,
      "service_master_group_name": "الخدمات المتنقله",
      "service_master_group_eng_name": "Mobile services",
      "is_need_customer_action": false,
      "booked_date": "2024-06-21T00:00:00",
      "booked_time": "05:45:00",
      "is_invoice_uploaded": false,
      "can_reset_schedule": true,
      "can_cancel": true,
      "is_canceled": false,
      "cancel_reason_id": null,
      "cancel_reason": null,
      "cancel_eng_reason": null,
      "car_info": {
        "car_profile_id": 18871,
        "car_vendor_id": 1,
        "car_vendor_name": "تويوتا",
        "car_vendor_eng_name": "Toyota",
        "car_model_id": 11,
        "car_model_name": "كامري",
        "car_model_eng_name": "camry",
        "car_color_id": 0,
        "car_color_name": "",
        "car_color_eng_name": null,
        "car_year": 0,
        "car_cylender_name": 5
      },
      "status_id": 100,
      "status_name": "قيد المعالجه",
      "status_eng_name": "Under Process",
      "shipping_address": null,
      "shipping_courier": null
    }
  ],
  "total": 140
}
```