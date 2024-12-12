# Webhook

**Set Webhook Endpoint**

This API allows you to set a webhook URL where status notifications from Yativo will be sent.

* **Endpoint**: `{{baseUrl}}/api/v1/business/webhook`
* **Method**: `POST`
* **Content-Type**: `application/json`

```json
{
  "url": "Your_Webhook_Address"
}
```



{% swagger src="../.gitbook/assets/Zee_v3_OpenAPI.yaml" path="/business/webhook" method="post" %}
[Zee_v3_OpenAPI.yaml](../.gitbook/assets/Zee_v3_OpenAPI.yaml)
{% endswagger %}

**Get Webhook Endpoint**

This API allows you to Get the webhook URL you set.

* **Endpoint**: `{{baseUrl}}/api/v1/business/webhook`
* **Method**: `GET`
* **Content-Type**: `application/json`



**Update Webhook Endpoint**

This API allows you to Get the webhook URL you set.

* **Endpoint**: `{{baseUrl}}/api/v1/business/webhook`
* **Method**: `PUT`
* **Content-Type**: `application/json`
