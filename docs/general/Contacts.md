## General Endpoints

### Get Contacts Info

**Endpoint**: `GET /api/General/Contacts`

**Description**: This endpoint retrieves the contact information for the service.

**Response Parameters**:
- `status` (boolean): Indicates whether the operation was successful.
- `message` (string): A message describing the result of the operation.
- `error` (string): An error message if the operation failed.
- `Data` (object): An object containing the following contact information:
  - `whatsapp` (string): The WhatsApp contact number.
  - `email` (string): The contact email address.
  - `phone` (string): The contact phone number.
  - `fb` (string): The Facebook page URL.
  - `twitter` (string): The Twitter profile URL.
  - `tiktok` (string): The TikTok profile URL.
  - `instagram` (string): The Instagram profile URL.
  - `youtube` (string): The YouTube channel URL.
  - `address` (string): The physical address.
  - `store_url` (string): The store URL.
  - `tos` (string): Terms of Service in Arabic.
  - `tos_eng` (string): Terms of Service in English.
  - `test_otp_phone_mumber` (string): The test OTP phone number.
  - `test_otp_result` (string): The test OTP result.

**Response Example**:
```json
{
  "status": true,
  "message": "تمت العمليه بنجاح",
  "error": "",
  "Data": {
    "whatsapp": "+966533206530",
    "email": "contactus@sayaratech.com",
    "phone": "+920000813",
    "fb": "https://www.facebook.com/sayaratechapp",
    "twitter": "https://twitter.com/sayaratechsa?s=21&t=FKpaacp7mza1qfvsxswvHg",
    "tiktok": "https://www.tiktok.com/@sayaratech",
    "instagram": "https://www.instagram.com/sayaratech/?igshid=YmMyMTA2M2Y%3D",
    "youtube": "https://Youtbue.com",
    "address": "المملكه العربيه السعوديه",
    "store_url": "https://store.sayaratech.com/shop/",
    "tos": "",
    "tos_eng": "",
    "test_otp_phone_mumber": "00000000",
    "test_otp_result": "0000"
  }
}
