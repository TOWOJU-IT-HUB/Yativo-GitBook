# Webhook

#### Overview

Webhooks allow you to receive real-time notifications for key events, such as completed transactions or wallet updates.

#### Use Case

* **Notifications:** Notify users of payments or balance changes instantly.
* **Automation:** Trigger workflows based on webhook events.

#### Endpoints

**Create Webhook**

* **URL:** `POST /api/v1/webhooks/create`
* **Description:** Registers a new webhook for event notifications.
* **Request Example:**
* ```json
  {
      "webhook_name": "Transaction Notifications",
      "webhook_url": "https://example.com/webhook",
      "webhook_secret": "securesecret123",
      "whitelist_ips": ["192.168.1.1"]
  }
  ```
* **Response Example:**
* ```json
  {
      "status": "success",
      "webhook_id": "web123",
      "message": "Webhook created successfully."
  }
  ```

**Fetch All Webhooks**

* **URL:** `GET /api/v1/webhooks`
* **Response Example:**

```json
[
    {
        "webhook_id": "web123",
        "name": "Transaction Notifications",
        "url": "https://example.com/webhook"
    }
]
```
