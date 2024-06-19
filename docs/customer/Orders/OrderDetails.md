### Get Order Request Details

**Endpoint**: `POST /api/Customer/Orders/RequestDetails`

**Description**: Retrieves detailed information about a specific order request.

**Authentication**: Requires Bearer Token Authentication in the header.

**Request Parameters**:
- `id` (integer, required): The order ID.

**Response Parameters**:
- `status` (boolean): Indicates whether the operation was successful.
- `message` (string): A message describing the result of the operation.
- `error` (string): An error message if the operation failed.
- `Data` (object): Contains detailed information about the order, including:
  - `id` (integer): The order ID.
  - `is_for_vehicle_repair` (boolean): Indicates if the service is for vehicle repair.
  - `require_appointment` (boolean): Indicates if an appointment is required.
  - `is_simple_service` (boolean): Indicates if the service is a simple service.
  - `is_for_oil` (boolean): Indicates if the service is for oil.
  - `is_for_tires` (boolean): Indicates if the service is for tires.
  - `is_for_battaries` (boolean): Indicates if the service is for batteries.
  - `is_shipping_service` (boolean): Indicates if the service is a shipping service.
  - `is_package_service` (boolean): Indicates if the service is a package service.
  - `is_for_pickup` (boolean or null): Indicates if the service is for pickup.
  - `is_required_attachments_on_new_request` (boolean): Indicates if attachments are required on new requests.
  - `min_attachment_files` (integer or null): Minimum number of attachment files required.
  - `max_attachment_files` (integer or null): Maximum number of attachment files allowed.
  - `is_prepaid` (boolean): Indicates if the service is prepaid.
  - `service_master_group_id` (integer): The master service group ID.
  - `service_master_group_name` (string): The master service group name in Arabic.
  - `service_master_group_eng_name` (string): The master service group name in English.
  - `is_need_customer_action` (boolean): Indicates if customer action is needed.
  - `status_id` (integer): The status ID of the order.
  - `status_name` (string): The status name of the order in Arabic.
  - `status_eng_name` (string): The status name of the order in English.
  - `is_paid` (boolean): Indicates if the order has been paid.
  - `is_invoice_uploaded` (boolean): Indicates if the invoice has been uploaded.
  - `InvoiceNumber` (string): The invoice number.
  - `created_date` (string): The creation date of the order.
  - `booked_date` (string): The booked date of the order.
  - `booked_time` (string): The booked time of the order.
  - `Paid_Amount` (number): The amount paid for the order.
  - `Paid_Amount_To_Wallet` (number): The amount paid to the wallet.
  - `Paid_Date` (string): The date when the payment was made.
  - `Payment_Options_id` (integer): The payment options ID.
  - `Payment_Options_name` (string): The payment options name in Arabic.
  - `Payment_Options_eng_name` (string): The payment options name in English.
  - `service_id` (integer): The service ID.
  - `service_name` (string): The service name in Arabic.
  - `service_eng_name` (string): The service name in English.
  - `service_img` (string or null): The service image.
  - `can_reset_schedule` (boolean): Indicates if the schedule can be reset.
  - `can_cancel` (boolean): Indicates if the order can be canceled.
  - `is_canceled` (boolean): Indicates if the order has been canceled.
  - `cancel_reason_id` (integer or null): The cancel reason ID.
  - `cancel_reason` (string or null): The cancel reason in Arabic.
  - `cancel_eng_reason` (string or null): The cancel reason in English.
  - `notes` (string or null): Additional notes.
  - `summary` (object): Contains summary details of the order, including:
    - `totalbeforetax` (number): Total amount before tax.
    - `Total` (number): Total amount of the order.
    - `totalTax` (number): Total tax amount.
    - `amount_to_pay` (number): Amount left to pay.
    - `discount` (number): Discount amount.
    - `CouponDiscountPercentage` (number): Discount percentage from the coupon.
    - `is_fixed_discount_amount` (boolean): Indicates if the discount amount is fixed.
    - `prepaid_amount` (number): Prepaid amount.
    - `status` (string): Status of the invoice in Arabic.
    - `status_color` (string): Color representing the status.
  - `provier` (object): Provider information, including:
    - `id` (integer): Provider ID.
    - `name` (string): Provider name in Arabic.
    - `eng_name` (string): Provider name in English.
    - `logo_binary_image` (string): Provider logo image in binary.
  - `car_info` (object): Car information, including:
    - `car_profile_id` (integer): Car profile ID.
    - `car_board_no` (string): Car board number.
    - `car_lic_no` (string): Car license number.
    - `car_vendor_id` (integer): Car vendor ID.
    - `car_vendor_name` (string): Car vendor name in Arabic.
    - `car_vendor_eng_name` (string): Car vendor name in English.
    - `car_model_id` (integer): Car model ID.
    - `car_model_name` (string): Car model name in Arabic.
    - `car_model_eng_name` (string): Car model name in English.
    - `car_color_id` (integer): Car color ID.
    - `car_color_name` (string): Car color name in Arabic.
    - `car_color_eng_name` (string or null): Car color name in English.
    - `car_cylender_name` (integer): Car cylinder name.
    - `expected_duration_of_repair` (integer): Expected duration of repair.
  - `address` (object): Address information, including:
    - `address_type_id` (integer): Address type ID.
    - `addressType_name` (string): Address type name in Arabic.
    - `addressType_eng_name` (string): Address type name in English.
    - `lat` (string): Latitude of the address.
    - `lng` (string): Longitude of the address.
    - `desc` (string or null): Description of the location.
    - `city_id` (integer): City ID.
    - `city_name` (string): City name in Arabic.
    - `city_eng_name` (string): City name in English.
    - `zone_id` (integer): Zone ID.
    - `zone_name` (string): Zone name in Arabic.
    - `zone_eng_name` (string): Zone name in English.
    - `area_id` (integer): Area ID.
    - `area_name` (string): Area name in Arabic.
    - `area_eng_name` (string): Area name in English.
  - `items` (array): List of items associated with the order, each containing:
    - `id` (integer): Item ID.
    - `is_approved_by_customer` (boolean or null): Indicates if the item is approved by the customer.
    - `service_item_id` (integer): Service item ID.
    - `service_item_name` (string): Service item name in Arabic.
    - `service_item_brand_name` (string): Service item brand name in Arabic.
    - `service_item_brand_eng_name` (string): Service item brand name in English.
    - `brand_id` (integer or null): Brand ID.
    - `brand_name` (string or null): Brand name in Arabic.
    - `brand_eng_name` (string or null): Brand name in English.
    - `manufacture_year` (integer or null): Manufacture year of the item.
    - `qty` (integer): Quantity of the item.
    - `price` (number): Price of the item.
    - `total` (number): Total price of the item.
    - `qty1` (integer): Quantity of the first additional item.
    - `price1` (number): Price of the first additional item.
    - `is_mandatory` (boolean or null): Indicates if the item is mandatory.
    - `is_extra_service` (boolean or null): Indicates if the item is an extra service.
    - `item_desc` (string or null): Description of the item.
    - `service_item_group_id` (integer or null): Service item group ID.
    - `service_item_group_name` (string or null): Service item group name in Arabic.
    - `service_item_group_eng_name` (string or null): Service item group name in English.
    - `check_option` (boolean or null): Check option for the item.
  - `shipping_address` (object or null): Shipping address details.
  - `shipping_courier` (object or null): Shipping courier details.
  - `chat_option` (object): Chat options, including:
    - `can_send_chat_message` (boolean): Indicates if chat messages can be sent.
    - `can_view_chat_messages` (boolean): Indicates if chat messages can be viewed.
    - `from_id` (integer): ID of the sender.
    - `from_name` (string): Name of the sender.
    - `to_ids` (array): List of recipient IDs.
    - `to_fcm_tokens` (array): List of recipient FCM tokens.
  - `attached_images` (object): Attached images, including:
    - `before` (array): List of images before the service.
    - `after` (array): List of images after the service.
  - `payment_gateways` (array): List of payment gateways.

**Response Example**:
```json
{
  "status": true,
  "message": "تمت العمليه بنجاح",
  "error": "",
  "Data": {
    "id": 16964,
    "is_for_vehicle_repair": false,
    "require_appointment": true,
    "is_simple_service": true,
    "is_for_oil": false,
    "is_for_tires": false,
    "is_for_battaries": false,
    "is_shipping_service": false,
    "is_package_service": false,
    "is_for_pickup": null,
    "is_required_attachments_on_new_request": false,
    "min_attachment_files": null,
    "max_attachment_files": null,
    "is_prepaid": true,
    "service_master_group_id": 1,
    "service_master_group_name": "الخدمات المتنقله",
    "service_master_group_eng_name": "Mobile services",
    "is_need_customer_action": false,
    "status_id": 6,
    "status_name": "تم الانتهاء من الخدمة",
    "status_eng_name": "Car Service Finished",
    "is_paid": true,
    "is_invoice_uploaded": true,
    "InvoiceNumber": "3722",
    "created_date": "2024-06-18T20:24:28.92",
    "booked_date": "2024-06-21T00:00:00",
    "booked_time": "05:45:00",
    "Paid_Amount": 140,
    "Paid_Amount_To_Wallet": 0,
    "Paid_Date": "2024-06-19T02:44:53.807",
    "Payment_Options_id": 3,
    "Payment_Options_name": "كاش ومحفظة",
    "Payment_Options_eng_name": "Cash And Wallet",
    "service_id": 10022,
    "service_name": "غسيل اكسبريس",
    "service_eng_name": "Express Wash",
    "service_img": null,
    "can_reset_schedule": false,
    "can_cancel": false,
    "is_canceled": false,
    "cancel_reason_id": null,
    "cancel_reason": null,
    "cancel_eng_reason": null,
    "notes": null,
    "summary": {
      "totalbeforetax": 173.913,
      "Total": 140,
      "totalTax": 18.2609,
      "amount_to_pay": 0,
      "discount": 52.1739,
      "CouponDiscountPercentage": 30,
      "is_fixed_discount_amount": false,
      "prepaid_amount": 0,
      "status": "تم دفع الفاتوره",
      "status_color": "#00FF00"
    },
    "provier": {
      "id": 10031,
      "name": "sayaratech",
      "eng_name": "sayaratech",
      "logo_binary_image": ""
    },
    "car_info": {
      "car_profile_id": 18871,
      "car_board_no": "",
      "car_lic_no": "",
      "car_vendor_id": 1,
      "car_vendor_name": "تويوتا",
      "car_vendor_eng_name": "Toyota",
      "car_model_id": 11,
      "car_model_name": "كامري",
      "car_model_eng_name": "camry",
      "car_color_id": 0,
      "car_color_name": "",
      "car_color_eng_name": null,
      "car_cylender_name": 5,
      "expected_duration_of_repair": 0
    },
    "address": {
      "address_type_id": 10,
      "addressType_name": "آخر",
      "addressType_eng_name": "Other",
      "lat": "24.689679",
      "lng": "46.62729",
      "desc": "",
      "city_id": 1,
      "city_name": "الرياض",
      "city_eng_name": "Riyadh",
      "zone_id": 13,
      "zone_name": "R8",
      "zone_eng_name": "R8",
      "area_id": 41,
      "area_name": "السفارات",
      "area_eng_name": "Al Safarat"
    },
    "items": [
      {
        "id": 43448,
        "is_approved_by_customer": null,
        "service_item_id": 13999,
        "service_item_name": "غسيل اكسبريس",
        "service_item_brand_name": "غسيل اكسبريس",
        "service_item_brand_eng_name": "Express Wash",
        "brand_id": null,
        "brand_name": null,
        "brand_eng_name": null,
        "manufacture_year": null,
        "qty": 1,
        "price": 200,
        "total": 200,
        "qty1": 0,
        "price1": 0,
        "is_mandatory": null,
        "is_extra_service": null,
        "item_desc": null,
        "service_item_group_id": null,
        "service_item_group_name": null,
        "service_item_group_eng_name": null,
        "check_option": null
      }
    ],
    "shipping_address": null,
    "shipping_courier": null,
    "chat_option": {
      "can_send_chat_message": true,
      "can_view_chat_messages": true,
      "from_id": 21368,
      "from_name": "Hassq satc",
      "to_ids": [
        20206,
        20133
      ],
      "to_fcm_tokens": [
        "cRAl3VsPR2-RJJjsNDaWG7:APA91bFBIRZ1ikfNNY8bHP2YRxHRoPF9pfwo4Y4PI_1zZF4Ql3xIp8VCwRGh8DRyOutGoNLi81_zCga8YOj7y86rrea4N4K8qPomkRIGADgW2gBguwXEqLedMYb6u8zTf11ouGkUW_zt",
        "cmOR2a8fROaKmO4vjrcd5Q:APA91bG5tIG6gIRoFms29zwvLEhQH2DSGQs3RrlCw9JZqtPe8_WvuvrXbNiXDSv81O-tfX63lmKU-V9Pex7eKv2WUhi4SKAu4Rz6__8CIfFPQ_q3tltvau5-tFB8N33PDDzoKbsbaSt2",
        "fDkOdcsNQJmm1LiAP7LxaV:APA91bHBsmDehT7XwiGjzUrZucpbKiG6wKczZ6oO4l1IG-E0c6RxWgLefSN9HOHOgX5FycdkLA7Ns1rXJLOgdj4Gc7j33fwJZbEGGRRHXVxerXsO7ywCZwcuVYYQYgt1bbDKVc2LggLt"
      ]
    },
    "attached_images": {
      "before": [],
      "after": []
    },
    "payment_gateways": []
  }
}
```