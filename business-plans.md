---
description: Yativo Business Plans
---

# Business Plans

#### Pricing Tiers Overview

Yativo API offers scalable pricing tiers to meet the diverse needs of businesses. Here's a brief overview of each tier:

**Start:** Ideal for getting started with basic payment processing needs. It includes support for all major currencies, standard transaction fees, unlimited transactions, and treasury wallets.

**Scale:** Designed for growing businesses that require additional features. In addition to everything offered in the Start tier, Scale provides discounted transaction fees, virtual account issuing capabilities, and wallet services, along with compliance features to ensure regulatory adherence.

**Enterprise:** Tailored for large enterprises with advanced requirements. Enterprise includes all features from the Scale tier, plus the flexibility of custom transaction fees, card issuing capabilities, payins support, and the option for whitelabel solutions to maintain brand identity.

Each tier is designed to offer increasingly sophisticated capabilities, ensuring businesses can scale their payment operations efficiently and effectively. For detailed pricing and to discuss specific needs, please contact our sales team.





| Start                     | Scale ($1000 yearly)        | Enterprise              |
| ------------------------- | --------------------------- | ----------------------- |
| All supported currencies  | Everything in Start +:      | Everything in Scale +:  |
| Standard transaction fees | Discounted Transaction Fees | Custom transaction fees |
| Unlimited transactions    | Virtual account issuing     | Card issuing            |
| Treasury wallets          | Wallets as a service        | Payins                  |
|                           | Compliance                  | Whitelabel              |



### 1. Fetch All Plans

#### Endpoint

**GET** `/business/plans/all`

#### Description

Fetches a list of all available business plans.

#### Request

**Headers**

* `Authorization: Bearer YOUR_ACCESS_TOKEN`
* `Content-Type: application/json`



### 2. Get Current Plan

#### Endpoint

**GET** `{{baseUrl}}/business/plans/current`

#### Description

Fetches the current subscribed plan for the authenticated user.

#### Request

**Headers**

* `Authorization: Bearer YOUR_ACCESS_TOKEN`
* `Content-Type: application/json`

### 3. Subscribe to Plan

#### Endpoint

**POST** `{{baseUrl}}/business/plans/subscribe/{{plan_id}}`

#### Description

Subscribes the authenticated user to a specific plan.

#### Request

**Headers**

* `Authorization: Bearer YOUR_ACCESS_TOKEN`
* `Content-Type: application/json`

### 4. Switch Plan

#### Endpoint

**PUT** `{{baseUrl}}/business/plans/upgrade/{{plan_id}}`

#### Description

Switches the current subscribed plan to a new plan identified by `plan_id`.

#### Request

**Headers**

* `Authorization: Bearer YOUR_ACCESS_TOKEN`
* `Content-Type: application/json`



{% tabs %}
{% tab title="PHP" %}
```php
<?php

$baseUrl = "https://api.yativo.com/api/v1";
$accessToken = "YOUR_ACCESS_TOKEN";
$planId = "plan_id_2"; // Example plan ID

// Fetch all plans
$ch = curl_init("$baseUrl/business/plans/all");
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_HTTPHEADER, [
    "Authorization: Bearer $accessToken",
    "Content-Type: application/json"
]);
$response = curl_exec($ch);
curl_close($ch);

echo "Fetch All Plans Response:\n";
echo $response . "\n\n";

// Get current plan
$ch = curl_init("$baseUrl/business/plans/current");
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_HTTPHEADER, [
    "Authorization: Bearer $accessToken",
    "Content-Type: application/json"
]);
$response = curl_exec($ch);
curl_close($ch);

echo "Get Current Plan Response:\n";
echo $response . "\n\n";

// Subscribe to plan
$data = [
    "payment_method" => "credit_card",
    "billing_info" => [
        "name" => "John Doe",
        "card_number" => "1234567890123456",
        "expiry_month" => "12",
        "expiry_year" => "2025",
        "cvv" => "123"
    ]
];

$ch = curl_init("$baseUrl/business/plans/subscribe/$planId");
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_POST, true);
curl_setopt($ch, CURLOPT_POSTFIELDS, json_encode($data));
curl_setopt($ch, CURLOPT_HTTPHEADER, [
    "Authorization: Bearer $accessToken",
    "Content-Type: application/json"
]);
$response = curl_exec($ch);
curl_close($ch);

echo "Subscribe to Plan Response:\n";
echo $response . "\n\n";

// Switch plan
$newPlanId = "plan_id_3"; // Example new plan ID

$ch = curl_init("$baseUrl/business/plans/upgrade/$newPlanId");
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_CUSTOMREQUEST, "PUT");
curl_setopt($ch, CURLOPT_HTTPHEADER, [
    "Authorization: Bearer $accessToken",
    "Content-Type: application/json"
]);
$response = curl_exec($ch);
curl_close($ch);

echo "Switch Plan Response:\n";
echo $response . "\n";
?>

```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
const baseUrl = "https://api.yativo.com/api/v1";
const accessToken = "YOUR_ACCESS_TOKEN";
const planId = "plan_id_2"; // Example plan ID

// Fetch all plans
fetch(`${baseUrl}/business/plans/all`, {
  method: 'GET',
  headers: {
    'Authorization': `Bearer ${accessToken}`,
    'Content-Type': 'application/json'
  }
})
.then(response => response.json())
.then(data => {
  console.log('Fetch All Plans Response:');
  console.log(data);
});

// Get current plan
fetch(`${baseUrl}/business/plans/current`, {
  method: 'GET',
  headers: {
    'Authorization': `Bearer ${accessToken}`,
    'Content-Type': 'application/json'
  }
})
.then(response => response.json())
.then(data => {
  console.log('Get Current Plan Response:');
  console.log(data);
});

// Subscribe to plan
const subscribeData = {
  payment_method: "credit_card",
  billing_info: {
    name: "John Doe",
    card_number: "1234567890123456",
    expiry_month: "12",
    expiry_year: "2025",
    cvv: "123"
  }
};

fetch(`${baseUrl}/business/plans/subscribe/${planId}`, {
  method: 'POST',
  headers: {
    'Authorization': `Bearer ${accessToken}`,
    'Content-Type': 'application/json'
  },
  body: JSON.stringify(subscribeData)
})
.then(response => response.json())
.then(data => {
  console.log('Subscribe to Plan Response:');
  console.log(data);
});

// Switch plan
const newPlanId = "plan_id_3"; // Example new plan ID

fetch(`${baseUrl}/business/plans/upgrade/${newPlanId}`, {
  method: 'PUT',
  headers: {
    'Authorization': `Bearer ${accessToken}`,
    'Content-Type': 'application/json'
  }
})
.then(response => response.json())
.then(data => {
  console.log('Switch Plan Response:');
  console.log(data);
});

```
{% endtab %}
{% endtabs %}
