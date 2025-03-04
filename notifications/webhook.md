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



{% openapi src="../.gitbook/assets/Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml" path="/business/webhook" method="post" %}
[Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml](<../.gitbook/assets/Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml>)
{% endopenapi %}

{% openapi src="broken-reference" path="/business/webhook" method="post" %}
[Broken link](broken-reference)
{% endopenapi %}

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
