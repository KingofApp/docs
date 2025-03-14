
# **Push Notification API Documentation**

## **Overview**
The Push Notification System is installed on a custom domain or subdomain within the **King of App** server. It provides a **REST API** that allows the sending of push notifications to specific users or groups. 

### **Setup Requirements**
- The Firebase Service Account file associated with the Firebase account must be uploaded to the **Push Notification Server** (`PUSH_SERVER`).
- API authentication is handled using **Basic Authentication**, requiring a **Base64-encoded** string of the `PUSH_SERVER` username and application password.

---

## **Authentication**
Every API request must include an **Authorization** header using **Basic Authentication**:

```
Authorization: Basic [[base64-encoded username:password]]
```

---

## **Endpoints**
### **1. Send Push Notification**
This endpoint allows sending a push notification to either:
- A **specific device**, using a `device_token`
- A **group of users**, by specifying a `topic`

#### **Endpoint**
```
POST https://[[domain_of_push_server]]/?rest_route=/firebase/v1/send-notification/
```

#### **Headers**
| Key             | Value                           |
|----------------|--------------------------------|
| Content-Type   | application/json              |
| Authorization  | Basic [[base64-encoded string]] |

#### **Request Body**
```json
{
    "title": "Title of the notification",
    "body": "Content of the push notification",
    "device_token": "[[device token from the user phone]]",
    "topic": "[[topic_name]]"
}
```
> **Note**: Only **one** of `device_token` or `topic` should be provided.

#### **Example CURL Command**
```bash
curl --location 'https://[[domain_of_push_server]]/?rest_route=/firebase/v1/send-notification/' \
--header 'Content-Type: application/json' \
--header 'Authorization: Basic [[base64_encoded_string]]' \
--data '{
    "title": "Title of the notification",
    "body": "Content of the push notification",
    "device_token": "[[device_token_from_user_phone]]"
}'
```
OR for sending to a **topic**:
```bash
curl --location 'https://[[domain_of_push_server]]/?rest_route=/firebase/v1/send-notification/' \
--header 'Content-Type: application/json' \
--header 'Authorization: Basic [[base64_encoded_string]]' \
--data '{
    "title": "Title of the notification",
    "body": "Content of the push notification",
    "topic": "[[topic_name]]"
}'
```

---

### **2. Create or Update a Topic**
This endpoint allows the creation of a **new topic** or updating an **existing topic**. When updating, all previous device tokens in the topic will be replaced by the new list provided.

#### **Endpoint**
```
POST https://[[domain_of_push_server]]/?rest_route=/firebase/v1/create-update-topic/
```

#### **Headers**
| Key             | Value                           |
|----------------|--------------------------------|
| Content-Type   | application/json              |
| Authorization  | Basic [[base64-encoded string]] |

#### **Request Body**
```json
{
    "topic_name": "[[valid_topic_name]]",
    "device_token_list": ["[[token_1]]", "[[token_2]]", "[[token_3]]"]
}
```
> **Note**: `topic_name` must be a valid string without special characters or numbers at the beginning.

#### **Example CURL Command**
```bash
curl --location 'https://[[domain_of_push_server]]/?rest_route=/firebase/v1/create-update-topic/' \
--header 'Content-Type: application/json' \
--header 'Authorization: Basic [[base64_encoded_string]]' \
--data '{
    "topic_name": "[[valid_topic_name]]",
    "device_token_list": ["[[token_1]]", "[[token_2]]", "[[token_3]]"]
}'
```

---

## **Error Handling**
| HTTP Status Code | Description |
|-----------------|-------------|
| **200 OK** | Request was successful. |
| **400 Bad Request** | Invalid request body or missing required fields. |
| **401 Unauthorized** | Invalid authentication credentials. |
| **500 Internal Server Error** | Server encountered an issue processing the request. |

---

## **Final Notes**
- Make sure to replace `[[placeholders]]` with actual values before making requests.
- Use only **one** of `device_token` or `topic` when sending a push notification.
- When updating a topic, **all previous tokens** will be **replaced** with the new list provided.
