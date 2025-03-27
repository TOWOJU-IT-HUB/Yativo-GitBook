---
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# Payout

## **Payout API Documentation**

**Overview**

This document provides step-by-step instructions on how users can make payouts through our platform. All requests must be authenticated, and POST requests require a unique Idempotency-Key for each unique request. `CHL` (Chile), `COL` (Colombia), `PER` (Peru), `ARG` (Argentina), `MEX`(Mexico).

### **Step 1: Retrieve Payout Gateway ID**

To make a payout, first, retrieve the available payout methods for a specific country by making a `GET` request to:

_GET \{{host\}}/payment-methods/payout?country=\{{country\_iso3\_code\}}_

**Request Example:**

_GET \{{host\}}/payment-methods/payout?country=CHL_

_GET \{{host\}}/payment-methods/payout?country=COL_

_GET \{{host\}}/payment-methods/payout?country=PER_

_GET \{{host\}}/payment-methods/payout?country=ARG_

_GET \{{host\}}/payment-methods/payout?country=MEX_

**Response Example:**

<details>

<summary>Argentina</summary>



```json
{
    "status": "success",
    "status_code": 200,
    "message": "Request successful",
    "data": [
        {
            "id": 3,
            "method_name": "PayPal",
            "country": "ARG",
            "currency": "USD",
            "payment_method_code": null,
            "cutoff_hrs_start": null,
            "cutoff_hrs_end": null,
            "base_currency": "USD",
            "exchange_rate_float": null
        },
        {
            "id": 26,
            "method_name": "Volet(Advcash)",
            "country": "ARG",
            "currency": "USD",
            "payment_method_code": null,
            "cutoff_hrs_start": null,
            "cutoff_hrs_end": null,
            "base_currency": "USD",
            "exchange_rate_float": null
        },
        {
            "id": 64,
            "method_name": "Mastercard",
            "country": "ARG",
            "currency": "USD",
            "payment_method_code": null,
            "cutoff_hrs_start": null,
            "cutoff_hrs_end": null,
            "base_currency": "USD",
            "exchange_rate_float": null
        },
        {
            "id": 122,
            "method_name": "Visa",
            "country": "ARG",
            "currency": "USD",
            "payment_method_code": null,
            "cutoff_hrs_start": null,
            "cutoff_hrs_end": null,
            "base_currency": "USD",
            "exchange_rate_float": null
        },
        {
            "id": 492,
            "method_name": "Bank Transfer",
            "country": "ARG",
            "currency": "ARS",
            "payment_method_code": null,
            "cutoff_hrs_start": null,
            "cutoff_hrs_end": null,
            "base_currency": "USD",
            "exchange_rate_float": null
        }
    ]
}
```

</details>

<details>

<summary>Chile</summary>

```jsx
{
    "status": "success",
    "status_code": 200,
    "message": "Request successful",
    "data": [
        {
            "id": 7,
            "method_name": "PayPal",
            "country": "CHL",
            "currency": "USD",
            "payment_method_code": null,
            "cutoff_hrs_start": null,
            "cutoff_hrs_end": null,
            "base_currency": "USD",
            "exchange_rate_float": null
        },
        {
            "id": 29,
            "method_name": "Volet(Advcash)",
            "country": "CHL",
            "currency": "USD",
            "payment_method_code": null,
            "cutoff_hrs_start": null,
            "cutoff_hrs_end": null,
            "base_currency": "USD",
            "exchange_rate_float": null
        },
        {
            "id": 67,
            "method_name": "Mastercard",
            "country": "CHL",
            "currency": "USD",
            "payment_method_code": null,
            "cutoff_hrs_start": null,
            "cutoff_hrs_end": null,
            "base_currency": "USD",
            "exchange_rate_float": null
        },
        {
            "id": 125,
            "method_name": "Visa",
            "country": "CHL",
            "currency": "USD",
            "payment_method_code": null,
            "cutoff_hrs_start": null,
            "cutoff_hrs_end": null,
            "base_currency": "USD",
            "exchange_rate_float": null
        },
        {
            "id": 505,
            "method_name": "Bank Transfer",
            "country": "CHL",
            "currency": "CLP",
            "payment_method_code": null,
            "cutoff_hrs_start": null,
            "cutoff_hrs_end": null,
            "base_currency": "CLP",
            "exchange_rate_float": null
        },
        {
            "id": 508,
            "method_name": "Bank Transfer",
            "country": "CHL",
            "currency": "CLP",
            "payment_method_code": null,
            "cutoff_hrs_start": null,
            "cutoff_hrs_end": null,
            "base_currency": "CLP",
            "exchange_rate_float": null
        }
    ]
}
```

</details>

<details>

<summary>Colombia</summary>

```json
{
    "status": "success",
    "status_code": 200,
    "message": "Request successful",
    "data": [
        {
            "id": 2,
            "method_name": "Bank Transfer",
            "country": "COL",
            "currency": "COP",
            "payment_method_code": null,
            "cutoff_hrs_start": null,
            "cutoff_hrs_end": null,
            "base_currency": "USD",
            "exchange_rate_float": null
        },
        {
            "id": 8,
            "method_name": "PayPal",
            "country": "COL",
            "currency": "USD",
            "payment_method_code": null,
            "cutoff_hrs_start": null,
            "cutoff_hrs_end": null,
            "base_currency": "USD",
            "exchange_rate_float": null
        },
        {
            "id": 30,
            "method_name": "Volet(Advcash)",
            "country": "COL",
            "currency": "USD",
            "payment_method_code": null,
            "cutoff_hrs_start": null,
            "cutoff_hrs_end": null,
            "base_currency": "USD",
            "exchange_rate_float": null
        },
        {
            "id": 68,
            "method_name": "Mastercard",
            "country": "COL",
            "currency": "USD",
            "payment_method_code": null,
            "cutoff_hrs_start": null,
            "cutoff_hrs_end": null,
            "base_currency": "USD",
            "exchange_rate_float": null
        },
        {
            "id": 126,
            "method_name": "Visa",
            "country": "COL",
            "currency": "USD",
            "payment_method_code": null,
            "cutoff_hrs_start": null,
            "cutoff_hrs_end": null,
            "base_currency": "USD",
            "exchange_rate_float": null
        }
    ]
}
```

</details>

<details>

<summary>Mexico</summary>

```json
{
    "status": "success",
    "status_code": 200,
    "message": "Request successful",
    "data": [
        {
            "id": 1,
            "method_name": "SPEI",
            "country": "MEX",
            "currency": "MXN",
            "payment_method_code": null,
            "cutoff_hrs_start": null,
            "cutoff_hrs_end": null,
            "base_currency": "USD",
            "exchange_rate_float": null
        },
        {
            "id": 18,
            "method_name": "PayPal",
            "country": "MEX",
            "currency": "USD",
            "payment_method_code": null,
            "cutoff_hrs_start": null,
            "cutoff_hrs_end": null,
            "base_currency": "USD",
            "exchange_rate_float": null
        },
        {
            "id": 37,
            "method_name": "Volet(Advcash)",
            "country": "MEX",
            "currency": "USD",
            "payment_method_code": null,
            "cutoff_hrs_start": null,
            "cutoff_hrs_end": null,
            "base_currency": "USD",
            "exchange_rate_float": null
        },
        {
            "id": 75,
            "method_name": "Mastercard",
            "country": "MEX",
            "currency": "USD",
            "payment_method_code": null,
            "cutoff_hrs_start": null,
            "cutoff_hrs_end": null,
            "base_currency": "USD",
            "exchange_rate_float": null
        },
        {
            "id": 133,
            "method_name": "Visa",
            "country": "MEX",
            "currency": "USD",
            "payment_method_code": null,
            "cutoff_hrs_start": null,
            "cutoff_hrs_end": null,
            "base_currency": "USD",
            "exchange_rate_float": null
        }
    ]
}
```

</details>

<details>

<summary>Peru</summary>

```json
{
    "status": "success",
    "status_code": 200,
    "message": "Request successful",
    "data": [
        {
            "id": 21,
            "method_name": "PayPal",
            "country": "PER",
            "currency": "USD",
            "payment_method_code": null,
            "cutoff_hrs_start": null,
            "cutoff_hrs_end": null,
            "base_currency": "USD",
            "exchange_rate_float": null
        },
        {
            "id": 41,
            "method_name": "Volet(Advcash)",
            "country": "PER",
            "currency": "USD",
            "payment_method_code": null,
            "cutoff_hrs_start": null,
            "cutoff_hrs_end": null,
            "base_currency": "USD",
            "exchange_rate_float": null
        },
        {
            "id": 79,
            "method_name": "Mastercard",
            "country": "PER",
            "currency": "USD",
            "payment_method_code": null,
            "cutoff_hrs_start": null,
            "cutoff_hrs_end": null,
            "base_currency": "USD",
            "exchange_rate_float": null
        },
        {
            "id": 137,
            "method_name": "Visa",
            "country": "PER",
            "currency": "USD",
            "payment_method_code": null,
            "cutoff_hrs_start": null,
            "cutoff_hrs_end": null,
            "base_currency": "USD",
            "exchange_rate_float": null
        },
        {
            "id": 190,
            "method_name": "Bank Transfer",
            "country": "PER",
            "currency": "usd",
            "payment_method_code": null,
            "cutoff_hrs_start": null,
            "cutoff_hrs_end": null,
            "base_currency": "USD",
            "exchange_rate_float": null
        },
        {
            "id": 501,
            "method_name": "Bank Transfer",
            "country": "PER",
            "currency": "PEN",
            "payment_method_code": null,
            "cutoff_hrs_start": null,
            "cutoff_hrs_end": null,
            "base_currency": "USD",
            "exchange_rate_float": null
        },
        {
            "id": 502,
            "method_name": "Bank Transfer",
            "country": "PER",
            "currency": "USD",
            "payment_method_code": null,
            "cutoff_hrs_start": null,
            "cutoff_hrs_end": null,
            "base_currency": "USD",
            "exchange_rate_float": null
        },
        {
            "id": 506,
            "method_name": "Bank Transfer",
            "country": "PER",
            "currency": "USD",
            "payment_method_code": null,
            "cutoff_hrs_start": null,
            "cutoff_hrs_end": null,
            "base_currency": "USD",
            "exchange_rate_float": null
        },
        {
            "id": 507,
            "method_name": "Bank Transfer",
            "country": "PER",
            "currency": "PEN",
            "payment_method_code": null,
            "cutoff_hrs_start": null,
            "cutoff_hrs_end": null,
            "base_currency": "PEN",
            "exchange_rate_float": null
        }
    ]
}
```

</details>

***

Extract the `*id*` of the desired payment method to proceed.

### **Step 2: Retrieve Beneficiary Form**

Use the retrieved `gateway_id` to get the form fields required for beneficiary payment details:

_GET \{{host\}}/beneficiary/form/show/\{{gateway\_id\}}_

**Request Example:**

*   Argentina

    GET \{{host\}}/beneficiary/form/show/492
*   Chile

    GET \{{host\}}/beneficiary/form/show/505
*   Colombia

    GET \{{host\}}/beneficiary/form/show/2
*   Mexico

    GET \{{host\}}/beneficiary/form/show/1
*   Peru

    GET \{{host\}}/beneficiary/form/show/501

**Response Example:**



<details>

<summary>Argentina</summary>

```json
{
    "status": "success",
    "status_code": 200,
    "message": "Request successful",
    "data": {
        "payment_data": [
            {
                "type": "select",
                "name": "Tipo",
                "key": "beneficiary_type",
                "options": [
                    {
                        "value": "Corporate",
                        "label": "Corporativo"
                    },
                    {
                        "value": "Individual",
                        "label": "Natural"
                    }
                ]
            },
            {
                "type": "text",
                "name": "Nombres",
                "key": "beneficiary_first_name",
                "min": 3,
                "max": 50,
                "when": {
                    "key": "beneficiary_type",
                    "value": "Individual"
                }
            },
            {
                "type": "text",
                "name": "Apellidos",
                "key": "beneficiary_last_name",
                "min": 3,
                "max": 50,
                "when": {
                    "key": "beneficiary_type",
                    "value": "Individual"
                }
            },
            {
                "type": "text",
                "name": "Nombre de empresa",
                "key": "company_name",
                "min": 4,
                "max": 50,
                "when": {
                    "key": "beneficiary_type",
                    "value": "Corporate"
                }
            },
            {
                "type": "email",
                "name": "Correo",
                "key": "beneficiary_email",
                "max": 80
            },
            {
                "type": "text",
                "name": "Dirección",
                "key": "beneficiary_address",
                "min": 3,
                "max": 200
            },
            {
                "type": "select",
                "name": "Tipo de documento",
                "key": "beneficiary_document_type",
                "options": [
                    {
                        "value": "CUIL",
                        "label": "Código único de identificación laboral"
                    },
                    {
                        "value": "CUIT",
                        "label": "Código único de identificación tributaria"
                    }
                ]
            },
            {
                "type": "text",
                "name": "CUIL/CUIT",
                "key": "beneficiary_document_number",
                "min": 11,
                "max": 11
            },
            {
                "type": "select",
                "name": "Banco",
                "key": "bank_code",
                "options": [
                    {
                        "value": "956",
                        "label": "Mercado pago"
                    },
                    {
                        "value": "125",
                        "label": "Banco santander rio"
                    },
                    {
                        "value": "90",
                        "label": "Banco de galicia y buenos aires"
                    },
                    {
                        "value": "76",
                        "label": "A.b.n amro bank"
                    },
                    {
                        "value": "77",
                        "label": "American express bank ltd"
                    },
                    {
                        "value": "78",
                        "label": "Bacs banco de credito y securitizacion"
                    },
                    {
                        "value": "79",
                        "label": "Banca nazionale del lavoro"
                    },
                    {
                        "value": "80",
                        "label": "Banco b. i. creditanstalt"
                    },
                    {
                        "value": "81",
                        "label": "Banco bradesco argentina"
                    },
                    {
                        "value": "82",
                        "label": "Banco cetelem argentina"
                    },
                    {
                        "value": "83",
                        "label": "Banco cmf"
                    },
                    {
                        "value": "84",
                        "label": "Banco cofidis"
                    },
                    {
                        "value": "85",
                        "label": "Banco columbia"
                    },
                    {
                        "value": "86",
                        "label": "Banco comafi"
                    },
                    {
                        "value": "87",
                        "label": "Banco credicoop coop. l"
                    },
                    {
                        "value": "88",
                        "label": "Banco de corrientes"
                    },
                    {
                        "value": "89",
                        "label": "Banco de formosa"
                    },
                    {
                        "value": "91",
                        "label": "Banco de inversion y comercio exterior"
                    },
                    {
                        "value": "92",
                        "label": "Banco de la ciudad de buenos aires"
                    },
                    {
                        "value": "93",
                        "label": "Banco de la nacion argentina"
                    },
                    {
                        "value": "94",
                        "label": "Banco de la pampa sociedad de economia m"
                    },
                    {
                        "value": "95",
                        "label": "Banco de la provincia de buenos aires"
                    },
                    {
                        "value": "96",
                        "label": "Banco de la provincia de cordoba"
                    },
                    {
                        "value": "97",
                        "label": "Banco de la republica oriental del uruguay"
                    },
                    {
                        "value": "104",
                        "label": "Banco del chubut"
                    },
                    {
                        "value": "105",
                        "label": "Banco del sol"
                    },
                    {
                        "value": "106",
                        "label": "Banco del tucuman"
                    },
                    {
                        "value": "98",
                        "label": "Banco de san juan"
                    },
                    {
                        "value": "99",
                        "label": "Banco de santa cruz"
                    },
                    {
                        "value": "100",
                        "label": "Banco de santiago del estero"
                    },
                    {
                        "value": "101",
                        "label": "Banco de servicios financieros"
                    },
                    {
                        "value": "102",
                        "label": "Banco de servicios y transacciones"
                    },
                    {
                        "value": "103",
                        "label": "Banco de valores"
                    },
                    {
                        "value": "107",
                        "label": "Banco do brasil"
                    },
                    {
                        "value": "108",
                        "label": "Banco empresario de tucuman coop. l"
                    },
                    {
                        "value": "109",
                        "label": "Banco finansur"
                    },
                    {
                        "value": "110",
                        "label": "Banco hipotecario"
                    },
                    {
                        "value": "145",
                        "label": "Banco industrial s.a."
                    },
                    {
                        "value": "111",
                        "label": "Banco itau buen ayre"
                    },
                    {
                        "value": "112",
                        "label": "Banco julio"
                    },
                    {
                        "value": "113",
                        "label": "Banco macro"
                    },
                    {
                        "value": "114",
                        "label": "Banco mariva"
                    },
                    {
                        "value": "115",
                        "label": "Banco mas ventas"
                    },
                    {
                        "value": "116",
                        "label": "Banco mercurio"
                    },
                    {
                        "value": "117",
                        "label": "Banco meridian"
                    },
                    {
                        "value": "118",
                        "label": "Banco municipal de rosario"
                    },
                    {
                        "value": "119",
                        "label": "Banco patagonia sudameris"
                    },
                    {
                        "value": "120",
                        "label": "Banco piano"
                    },
                    {
                        "value": "121",
                        "label": "Banco privado de inversiones"
                    },
                    {
                        "value": "123",
                        "label": "Banco provincia del neuquen"
                    },
                    {
                        "value": "122",
                        "label": "Banco provincia de tierra del fuego"
                    },
                    {
                        "value": "124",
                        "label": "Banco regional de cuyo"
                    },
                    {
                        "value": "126",
                        "label": "Banco roela"
                    },
                    {
                        "value": "127",
                        "label": "Banco saenz"
                    },
                    {
                        "value": "128",
                        "label": "Banco supervielle s.a."
                    },
                    {
                        "value": "129",
                        "label": "Bank of america, national associa"
                    },
                    {
                        "value": "131",
                        "label": "Bbva banco frances"
                    },
                    {
                        "value": "1057",
                        "label": "Belo"
                    },
                    {
                        "value": "132",
                        "label": "Bnp paribas"
                    },
                    {
                        "value": "372",
                        "label": "Brubank"
                    },
                    {
                        "value": "133",
                        "label": "Citibank"
                    },
                    {
                        "value": "134",
                        "label": "Deutsche bank"
                    },
                    {
                        "value": "135",
                        "label": "Hsbc bank argentina"
                    },
                    {
                        "value": "130",
                        "label": "Industrial and commercial bank of china (icbc)"
                    },
                    {
                        "value": "136",
                        "label": "Ing bank"
                    },
                    {
                        "value": "137",
                        "label": "J p morgan chase bank sucursal buenos aires"
                    },
                    {
                        "value": "957",
                        "label": "Lemon"
                    },
                    {
                        "value": "138",
                        "label": "Lloyds tsb bank"
                    },
                    {
                        "value": "139",
                        "label": "M. b. a. banco de inversiones"
                    },
                    {
                        "value": "1055",
                        "label": "Naranja x"
                    },
                    {
                        "value": "140",
                        "label": "Nuevo banco bisel"
                    },
                    {
                        "value": "141",
                        "label": "Nuevo banco de entre rios"
                    },
                    {
                        "value": "142",
                        "label": "Nuevo banco de la rioja"
                    },
                    {
                        "value": "144",
                        "label": "Nuevo banco del chaco"
                    },
                    {
                        "value": "143",
                        "label": "Nuevo banco de santa fe"
                    },
                    {
                        "value": "146",
                        "label": "Nuevo banco suquia"
                    },
                    {
                        "value": "1056",
                        "label": "Prex"
                    },
                    {
                        "value": "147",
                        "label": "Rci banque argentina"
                    },
                    {
                        "value": "847",
                        "label": "Standard bank argentina"
                    },
                    {
                        "value": "148",
                        "label": "The bank of tokyo - mitsubishi"
                    },
                    {
                        "value": "729",
                        "label": "Uala"
                    },
                    {
                        "value": "374",
                        "label": "Wilobank"
                    }
                ]
            },
            {
                "type": "select",
                "name": "Tipo",
                "key": "account_type_bank",
                "options": [
                    {
                        "value": "C",
                        "label": "Cuenta corriente"
                    },
                    {
                        "value": "S",
                        "label": "Cuenta de ahorros"
                    }
                ]
            },
            {
                "type": "text",
                "name": "CBU / CVU",
                "key": "account_bank",
                "min": 18,
                "max": 22
            },
            {
                "type": "select",
                "name": "Tipo de cliente",
                "key": "fc_customer_type",
                "options": [
                    {
                        "value": "business",
                        "label": "Empresa"
                    },
                    {
                        "value": "natural",
                        "label": "Natural"
                    }
                ]
            },
            {
                "type": "text",
                "name": "Nombre completo",
                "key": "fc_legal_name",
                "min": 1,
                "max": 50,
                "when": {
                    "key": "fc_customer_type",
                    "value": "natural"
                }
            },
            {
                "type": "select",
                "name": "Tipo de documento",
                "key": "fc_document_type",
                "options": [
                    {
                        "value": "company_id",
                        "label": "Documento de identificación de empresas"
                    },
                    {
                        "value": "dni",
                        "label": "Documento nacional de identidad"
                    },
                    {
                        "value": "passport",
                        "label": "Pasaporte"
                    }
                ],
                "when": {
                    "key": "fc_customer_type",
                    "value": "natural"
                }
            },
            {
                "type": "text",
                "name": "Número de documento",
                "key": "fc_document_number",
                "min": 1,
                "max": 50,
                "when": {
                    "key": "fc_customer_type",
                    "value": "natural"
                }
            },
            {
                "type": "text",
                "name": "Domicilio completo",
                "key": "fc_legal_address",
                "min": 1,
                "max": 200,
                "when": {
                    "key": "fc_customer_type",
                    "value": "natural"
                }
            },
            {
                "type": "text",
                "name": "Razón social",
                "key": "fc_legal_name",
                "min": 1,
                "max": 50,
                "when": {
                    "key": "fc_customer_type",
                    "value": "business"
                }
            },
            {
                "type": "text",
                "name": "Nombre fantasía",
                "key": "fc_trade_name",
                "min": 0,
                "max": 50,
                "when": {
                    "key": "fc_customer_type",
                    "value": "business"
                }
            },
            {
                "type": "text",
                "name": "Número de TAX ID",
                "key": "fc_tax_id",
                "min": 1,
                "max": 50,
                "when": {
                    "key": "fc_customer_type",
                    "value": "business"
                }
            },
            {
                "type": "text",
                "name": "Domicilio legal",
                "key": "fc_legal_address",
                "min": 1,
                "max": 200,
                "when": {
                    "key": "fc_customer_type",
                    "value": "business"
                }
            },
            {
                "type": "text",
                "name": "Fecha de nacimiento (yyyy-mm-dd)",
                "key": "fc_birthdate",
                "when": {
                    "key": "fc_customer_type",
                    "value": "natural"
                }
            },
            {
                "type": "select",
                "name": "Propósito",
                "key": "purpose",
                "options": [
                    {
                        "value": "ISSAVG",
                        "label": "Ahorro / jubilación"
                    },
                    {
                        "value": "ISGDDS",
                        "label": "Compra venta de bienes"
                    },
                    {
                        "value": "ISSCVE",
                        "label": "Compra venta de servicios"
                    },
                    {
                        "value": "EPDISP",
                        "label": "Disponibilidades"
                    },
                    {
                        "value": "ISSTDY",
                        "label": "Educación"
                    },
                    {
                        "value": "EPPROP",
                        "label": "Inmuebles"
                    },
                    {
                        "value": "EPFAMT",
                        "label": "Mantenimiento familiar"
                    },
                    {
                        "value": "EPREMT",
                        "label": "Otros"
                    },
                    {
                        "value": "ISTAXS",
                        "label": "Pago de impuestos"
                    },
                    {
                        "value": "EPIVST",
                        "label": "Pago de inversión"
                    },
                    {
                        "value": "ISPAYR",
                        "label": "Pago de nómina"
                    },
                    {
                        "value": "ISSUPP",
                        "label": "Pago de proveedor"
                    },
                    {
                        "value": "ISMDCS",
                        "label": "Salud"
                    },
                    {
                        "value": "EPTOUR",
                        "label": "Turismo"
                    }
                ]
            },
            {
                "type": "text",
                "name": "Comentario",
                "key": "purpose_comentary",
                "min": 5,
                "max": 50
            }
        ]
    }
}
```



</details>

<details>

<summary>Chile</summary>

```json
{
    "status": "success",
    "status_code": 200,
    "message": "Request successful",
    "data": {
        "payment_data": [
            {
                "key": "beneficiary_id",
                "name": "RUT (Beneficiary ID)",
                "type": "text",
                "required": true
            },
            {
                "key": "beneficiary_name",
                "name": "Beneficiary Name",
                "type": "text",
                "required": true
            },
            {
                "key": "beneficiary_account",
                "name": "Beneficiary Account (CCI)",
                "type": "text",
                "required": true
            },
            {
                "key": "beneficiary_account_type",
                "name": "Beneficiary Account Type",
                "type": "text",
                "required": true
            },
            {
                "key": "beneficiary_bank_code",
                "name": "Beneficiary Bank Code",
                "type": "text",
                "required": true
            },
            {
                "key": "beneficiary_email",
                "name": "Beneficiary Email",
                "type": "text",
                "required": false
            },
            {
                "key": "description",
                "name": "Transfer Description",
                "type": "text",
                "required": true
            }
        ]
    }
}
```

</details>

<details>

<summary>Colombia</summary>

```json
{
    "status": "success",
    "status_code": 200,
    "message": "Request successful",
    "data": {
        "payment_data": [
            {
                "key": "bankAccount",
                "name": "Account Number",
                "type": "number",
                "value": null,
                "required": true
            },
            {
                "key": "AccountType",
                "name": "Account Type",
                "type": "select",
                "value": null,
                "options": [
                    {
                        "label": "US",
                        "value": "us"
                    },
                    {
                        "label": "IBAN",
                        "value": "iban"
                    }
                ],
                "required": true
            },
            {
                "key": "bankCode",
                "name": "Select Bank",
                "type": "select",
                "value": null,
                "options": [
                    {
                        "id": 366,
                        "code": "059",
                        "name": "Bancamia S.A.",
                        "countryCode": "COL",
                        "accountTypes": [
                            {
                                "code": "2",
                                "name": "Savings",
                                "minAddressLength": 3,
                                "maxAddressLength": 18
                            },
                            {
                                "code": "1",
                                "name": "Checking",
                                "minAddressLength": 3,
                                "maxAddressLength": 18
                            }
                        ],
                        "isActive": true
                    },
                    {
                        "id": 367,
                        "code": "040",
                        "name": "Banco Agrario",
                        "countryCode": "COL",
                        "accountTypes": [
                            {
                                "code": "2",
                                "name": "Savings",
                                "minAddressLength": 3,
                                "maxAddressLength": 12
                            },
                            {
                                "code": "1",
                                "name": "Checking",
                                "minAddressLength": 3,
                                "maxAddressLength": 12
                            }
                        ],
                        "isActive": true
                    },
                    {
                        "id": 368,
                        "code": "052",
                        "name": "Banco Av. Villas",
                        "countryCode": "COL",
                        "accountTypes": [
                            {
                                "code": "2",
                                "name": "Savings",
                                "minAddressLength": 3,
                                "maxAddressLength": 11
                            },
                            {
                                "code": "1",
                                "name": "Checking",
                                "minAddressLength": 3,
                                "maxAddressLength": 13
                            }
                        ],
                        "isActive": true
                    },
                    {
                        "id": 369,
                        "code": "032",
                        "name": "Banco Caja Social BCSC",
                        "countryCode": "COL",
                        "accountTypes": [
                            {
                                "code": "2",
                                "name": "Savings",
                                "minAddressLength": 3,
                                "maxAddressLength": 12
                            },
                            {
                                "code": "1",
                                "name": "Checking",
                                "minAddressLength": 3,
                                "maxAddressLength": 12
                            }
                        ],
                        "isActive": true
                    },
                    {
                        "id": 370,
                        "code": "019",
                        "name": "Scotiabank Colpatria",
                        "countryCode": "COL",
                        "accountTypes": [
                            {
                                "code": "2",
                                "name": "Savings",
                                "minAddressLength": 3,
                                "maxAddressLength": 10
                            },
                            {
                                "code": "1",
                                "name": "Checking",
                                "minAddressLength": 3,
                                "maxAddressLength": 10
                            }
                        ],
                        "isActive": true
                    },
                    {
                        "id": 371,
                        "code": "067",
                        "name": "Banco Compartir S.A.",
                        "countryCode": "COL",
                        "accountTypes": [
                            {
                                "code": "2",
                                "name": "Savings",
                                "minAddressLength": 3,
                                "maxAddressLength": 18
                            },
                            {
                                "code": "1",
                                "name": "Checking",
                                "minAddressLength": 3,
                                "maxAddressLength": 18
                            }
                        ],
                        "isActive": true
                    },
                    {
                        "id": 372,
                        "code": "051",
                        "name": "Banco Davivienda",
                        "countryCode": "COL",
                        "accountTypes": [
                            {
                                "code": "2",
                                "name": "Savings",
                                "minAddressLength": 3,
                                "maxAddressLength": 18
                            },
                            {
                                "code": "1",
                                "name": "Checking",
                                "minAddressLength": 3,
                                "maxAddressLength": 18
                            }
                        ],
                        "isActive": true
                    },
                    {
                        "id": 373,
                        "code": "001",
                        "name": "Banco de Bogota",
                        "countryCode": "COL",
                        "accountTypes": [
                            {
                                "code": "2",
                                "name": "Savings",
                                "minAddressLength": 3,
                                "maxAddressLength": 11
                            },
                            {
                                "code": "1",
                                "name": "Checking",
                                "minAddressLength": 3,
                                "maxAddressLength": 11
                            }
                        ],
                        "isActive": true
                    },
                    {
                        "id": 374,
                        "code": "023",
                        "name": "Banco de Occidente",
                        "countryCode": "COL",
                        "accountTypes": [
                            {
                                "code": "2",
                                "name": "Savings",
                                "minAddressLength": 3,
                                "maxAddressLength": 9
                            },
                            {
                                "code": "1",
                                "name": "Checking",
                                "minAddressLength": 3,
                                "maxAddressLength": 9
                            }
                        ],
                        "isActive": true
                    },
                    {
                        "id": 375,
                        "code": "062",
                        "name": "Banco Falabella S.A.",
                        "countryCode": "COL",
                        "accountTypes": [
                            {
                                "code": "2",
                                "name": "Savings",
                                "minAddressLength": 3,
                                "maxAddressLength": 12
                            },
                            {
                                "code": "1",
                                "name": "Checking",
                                "minAddressLength": 3,
                                "maxAddressLength": 12
                            }
                        ],
                        "isActive": true
                    },
                    {
                        "id": 376,
                        "code": "063",
                        "name": "Banco Finandina S.A.",
                        "countryCode": "COL",
                        "accountTypes": [
                            {
                                "code": "2",
                                "name": "Savings",
                                "minAddressLength": 3,
                                "maxAddressLength": 18
                            },
                            {
                                "code": "1",
                                "name": "Checking",
                                "minAddressLength": 3,
                                "maxAddressLength": 18
                            }
                        ],
                        "isActive": true
                    },
                    {
                        "id": 377,
                        "code": "064",
                        "name": "Banco Multibank S.A.",
                        "countryCode": "COL",
                        "accountTypes": [
                            {
                                "code": "2",
                                "name": "Savings",
                                "minAddressLength": 3,
                                "maxAddressLength": 18
                            },
                            {
                                "code": "1",
                                "name": "Checking",
                                "minAddressLength": 3,
                                "maxAddressLength": 18
                            }
                        ],
                        "isActive": true
                    },
                    {
                        "id": 378,
                        "code": "047",
                        "name": "Banco Mundo Mujer",
                        "countryCode": "COL",
                        "accountTypes": [
                            {
                                "code": "2",
                                "name": "Savings",
                                "minAddressLength": 3,
                                "maxAddressLength": 18
                            },
                            {
                                "code": "1",
                                "name": "Checking",
                                "minAddressLength": 3,
                                "maxAddressLength": 18
                            }
                        ],
                        "isActive": true
                    },
                    {
                        "id": 379,
                        "code": "060",
                        "name": "Banco Pichincha",
                        "countryCode": "COL",
                        "accountTypes": [
                            {
                                "code": "2",
                                "name": "Savings",
                                "minAddressLength": 3,
                                "maxAddressLength": 18
                            },
                            {
                                "code": "1",
                                "name": "Checking",
                                "minAddressLength": 3,
                                "maxAddressLength": 18
                            }
                        ],
                        "isActive": true
                    },
                    {
                        "id": 381,
                        "code": "058",
                        "name": "Banco Procredit",
                        "countryCode": "COL",
                        "accountTypes": [
                            {
                                "code": "2",
                                "name": "Savings",
                                "minAddressLength": 3,
                                "maxAddressLength": 13
                            },
                            {
                                "code": "1",
                                "name": "Checking",
                                "minAddressLength": 3,
                                "maxAddressLength": 13
                            }
                        ],
                        "isActive": true
                    },
                    {
                        "id": 382,
                        "code": "006",
                        "name": "Banco Santander",
                        "countryCode": "COL",
                        "accountTypes": [
                            {
                                "code": "2",
                                "name": "Savings",
                                "minAddressLength": 3,
                                "maxAddressLength": 9
                            },
                            {
                                "code": "1",
                                "name": "Checking",
                                "minAddressLength": 3,
                                "maxAddressLength": 9
                            }
                        ],
                        "isActive": true
                    },
                    {
                        "id": 383,
                        "code": "069",
                        "name": "Banco Serfinanza S.A.",
                        "countryCode": "COL",
                        "accountTypes": [
                            {
                                "code": "2",
                                "name": "Savings",
                                "minAddressLength": 3,
                                "maxAddressLength": 18
                            },
                            {
                                "code": "1",
                                "name": "Checking",
                                "minAddressLength": 3,
                                "maxAddressLength": 18
                            }
                        ],
                        "isActive": true
                    },
                    {
                        "id": 384,
                        "code": "012",
                        "name": "Banco Sudameris",
                        "countryCode": "COL",
                        "accountTypes": [
                            {
                                "code": "2",
                                "name": "Savings",
                                "minAddressLength": 3,
                                "maxAddressLength": 8
                            },
                            {
                                "code": "1",
                                "name": "Checking",
                                "minAddressLength": 3,
                                "maxAddressLength": 11
                            }
                        ],
                        "isActive": true
                    },
                    {
                        "id": 385,
                        "code": "053",
                        "name": "Banco W S.A.",
                        "countryCode": "COL",
                        "accountTypes": [
                            {
                                "code": "2",
                                "name": "Savings",
                                "minAddressLength": 3,
                                "maxAddressLength": 18
                            },
                            {
                                "code": "1",
                                "name": "Checking",
                                "minAddressLength": 3,
                                "maxAddressLength": 18
                            }
                        ],
                        "isActive": true
                    },
                    {
                        "id": 386,
                        "code": "031",
                        "name": "Bancoldex S.A.",
                        "countryCode": "COL",
                        "accountTypes": [
                            {
                                "code": "2",
                                "name": "Savings",
                                "minAddressLength": 3,
                                "maxAddressLength": 18
                            },
                            {
                                "code": "1",
                                "name": "Checking",
                                "minAddressLength": 3,
                                "maxAddressLength": 18
                            }
                        ],
                        "isActive": true
                    },
                    {
                        "id": 387,
                        "code": "007",
                        "name": "Bancolombia",
                        "countryCode": "COL",
                        "accountTypes": [
                            {
                                "code": "2",
                                "name": "Savings",
                                "minAddressLength": 3,
                                "maxAddressLength": 11
                            },
                            {
                                "code": "1",
                                "name": "Checking",
                                "minAddressLength": 3,
                                "maxAddressLength": 11
                            }
                        ],
                        "isActive": true
                    },
                    {
                        "id": 388,
                        "code": "061",
                        "name": "Bancoomeva",
                        "countryCode": "COL",
                        "accountTypes": [
                            {
                                "code": "2",
                                "name": "Savings",
                                "minAddressLength": 3,
                                "maxAddressLength": 12
                            },
                            {
                                "code": "1",
                                "name": "Checking",
                                "minAddressLength": 3,
                                "maxAddressLength": 12
                            }
                        ],
                        "isActive": true
                    },
                    {
                        "id": 389,
                        "code": "013",
                        "name": "BBVA",
                        "countryCode": "COL",
                        "accountTypes": [
                            {
                                "code": "2",
                                "name": "Savings",
                                "minAddressLength": 3,
                                "maxAddressLength": 16
                            },
                            {
                                "code": "1",
                                "name": "Checking",
                                "minAddressLength": 3,
                                "maxAddressLength": 16
                            }
                        ],
                        "isActive": true
                    },
                    {
                        "id": 390,
                        "code": "370",
                        "name": "Coltefinanciera S.A.",
                        "countryCode": "COL",
                        "accountTypes": [
                            {
                                "code": "2",
                                "name": "Savings",
                                "minAddressLength": 3,
                                "maxAddressLength": 18
                            },
                            {
                                "code": "1",
                                "name": "Checking",
                                "minAddressLength": 3,
                                "maxAddressLength": 18
                            }
                        ],
                        "isActive": true
                    },
                    {
                        "id": 391,
                        "code": "292",
                        "name": "Confiar",
                        "countryCode": "COL",
                        "accountTypes": [
                            {
                                "code": "2",
                                "name": "Savings",
                                "minAddressLength": 3,
                                "maxAddressLength": 9
                            },
                            {
                                "code": "1",
                                "name": "Checking",
                                "minAddressLength": 3,
                                "maxAddressLength": 9
                            }
                        ],
                        "isActive": true
                    },
                    {
                        "id": 392,
                        "code": "076",
                        "name": "Coopcentral S.A.",
                        "countryCode": "COL",
                        "accountTypes": [
                            {
                                "code": "1",
                                "name": "Checking",
                                "minAddressLength": 3,
                                "maxAddressLength": 9
                            }
                        ],
                        "isActive": true
                    },
                    {
                        "id": 394,
                        "code": "289",
                        "name": "Cotrafa Cooperativa Financiera",
                        "countryCode": "COL",
                        "accountTypes": [
                            {
                                "code": "1",
                                "name": "Checking",
                                "minAddressLength": 3,
                                "maxAddressLength": 13
                            }
                        ],
                        "isActive": true
                    },
                    {
                        "id": 395,
                        "code": "551",
                        "name": "Daviplata",
                        "countryCode": "COL",
                        "accountTypes": [
                            {
                                "code": "2",
                                "name": "Savings",
                                "minAddressLength": 3,
                                "maxAddressLength": 18
                            },
                            {
                                "code": "1",
                                "name": "Checking",
                                "minAddressLength": 3,
                                "maxAddressLength": 18
                            }
                        ],
                        "isActive": true
                    },
                    {
                        "id": 396,
                        "code": "296",
                        "name": "Financiera Juriscoop",
                        "countryCode": "COL",
                        "accountTypes": [
                            {
                                "code": "1",
                                "name": "Checking",
                                "minAddressLength": 3,
                                "maxAddressLength": 12
                            }
                        ],
                        "isActive": true
                    },
                    {
                        "id": 397,
                        "code": "010",
                        "name": "HSBC",
                        "countryCode": "COL",
                        "accountTypes": [
                            {
                                "code": "2",
                                "name": "Savings",
                                "minAddressLength": 3,
                                "maxAddressLength": 15
                            },
                            {
                                "code": "1",
                                "name": "Checking",
                                "minAddressLength": 3,
                                "maxAddressLength": 15
                            }
                        ],
                        "isActive": true
                    },
                    {
                        "id": 398,
                        "code": "014",
                        "name": "Itau",
                        "countryCode": "COL",
                        "accountTypes": [
                            {
                                "code": "2",
                                "name": "Savings",
                                "minAddressLength": 3,
                                "maxAddressLength": 9
                            },
                            {
                                "code": "1",
                                "name": "Checking",
                                "minAddressLength": 3,
                                "maxAddressLength": 9
                            }
                        ],
                        "isActive": true
                    },
                    {
                        "id": 399,
                        "code": "507",
                        "name": "Nequi",
                        "countryCode": "COL",
                        "accountTypes": [
                            {
                                "code": "2",
                                "name": "Savings",
                                "minAddressLength": 3,
                                "maxAddressLength": 18
                            },
                            {
                                "code": "1",
                                "name": "Checking",
                                "minAddressLength": 3,
                                "maxAddressLength": 18
                            }
                        ],
                        "isActive": true
                    },
                    {
                        "id": 400,
                        "code": "637",
                        "name": "Iris",
                        "countryCode": "COL",
                        "accountTypes": [
                            {
                                "code": "2",
                                "name": "Savings",
                                "minAddressLength": 3,
                                "maxAddressLength": 18
                            },
                            {
                                "code": "1",
                                "name": "Checking",
                                "minAddressLength": 3,
                                "maxAddressLength": 18
                            }
                        ],
                        "isActive": true
                    },
                    {
                        "id": 401,
                        "code": "097",
                        "name": "Banco Dale",
                        "countryCode": "COL",
                        "accountTypes": [
                            {
                                "code": "2",
                                "name": "Savings",
                                "minAddressLength": 3,
                                "maxAddressLength": 18
                            },
                            {
                                "code": "1",
                                "name": "Checking",
                                "minAddressLength": 3,
                                "maxAddressLength": 18
                            }
                        ],
                        "isActive": true
                    }
                ],
                "required": true
            }
        ]
    }
}
```

</details>

<details>

<summary>Mexico</summary>

```json
{
    "status": "success",
    "status_code": 200,
    "message": "Request successful",
    "data": {
        "payment_data": [
            {
                "key": "clabe",
                "name": "Clabe Number",
                "type": "number",
                "value": null,
                "required": true
            },
            {
                "key": "beneficiary",
                "name": "Beneficiary Full Name",
                "type": "text",
                "value": null,
                "required": true
            }
        ]
    }
}
```

</details>

<details>

<summary>Peru</summary>

```json
{
    "status": "success",
    "status_code": 200,
    "message": "Request successful",
    "data": {
        "payment_data": [
            {
                "type": "text",
                "name": "Nombres",
                "key": "beneficiary_first_name",
                "min": 3,
                "max": 50
            },
            {
                "type": "text",
                "name": "Apellidos",
                "key": "beneficiary_last_name",
                "min": 3,
                "max": 50
            },
            {
                "type": "email",
                "name": "Correo",
                "key": "beneficiary_email",
                "max": 80
            },
            {
                "type": "text",
                "name": "Dirección",
                "key": "beneficiary_address",
                "min": 3,
                "max": 200
            },
            {
                "type": "text",
                "name": "Ciudad",
                "key": "city",
                "min": 3,
                "max": 50
            },
            {
                "type": "text",
                "name": "Teléfono",
                "key": "phone",
                "min": 6,
                "max": 9
            },
            {
                "type": "select",
                "name": "Tipo de documento",
                "key": "beneficiary_document_type",
                "options": [
                    {
                        "value": "CE",
                        "label": "Carnet de extranjería"
                    },
                    {
                        "value": "DNI",
                        "label": "Documento nacional de identidad"
                    },
                    {
                        "value": "PASS",
                        "label": "Pasaporte"
                    },
                    {
                        "value": "RUC",
                        "label": "Registro único de contribuyentes"
                    }
                ]
            },
            {
                "type": "text",
                "name": "Nro de documento",
                "key": "beneficiary_document_number",
                "min": 6
            },
            {
                "type": "select",
                "name": "Banco",
                "key": "bank_code",
                "options": [
                    {
                        "value": "265",
                        "label": "Banco de crédito del perú"
                    },
                    {
                        "value": "266",
                        "label": "Interbank"
                    },
                    {
                        "value": "269",
                        "label": "Bbva continental"
                    },
                    {
                        "value": "1024",
                        "label": "Alfin banco"
                    },
                    {
                        "value": "264",
                        "label": "Banco central de reserva"
                    },
                    {
                        "value": "271",
                        "label": "Banco de comercio"
                    },
                    {
                        "value": "270",
                        "label": "Banco de la nación"
                    },
                    {
                        "value": "277",
                        "label": "Banco falabella"
                    },
                    {
                        "value": "272",
                        "label": "Banco financiero"
                    },
                    {
                        "value": "276",
                        "label": "Banco gnb perú s.a."
                    },
                    {
                        "value": "273",
                        "label": "Banco interamericano de finanzas (bif)"
                    },
                    {
                        "value": "1054",
                        "label": "Banco pichincha"
                    },
                    {
                        "value": "279",
                        "label": "Caja metropolitana de lima"
                    },
                    {
                        "value": "282",
                        "label": "Caja municipal de ahorro y crédito arequipa"
                    },
                    {
                        "value": "284",
                        "label": "Caja municipal de ahorro y crédito cuzco"
                    },
                    {
                        "value": "285",
                        "label": "Caja municipal de ahorro y crédito huancayo"
                    },
                    {
                        "value": "280",
                        "label": "Caja municipal de ahorro y crédito piura sac"
                    },
                    {
                        "value": "283",
                        "label": "Caja municipal de ahorro y crédito sullana"
                    },
                    {
                        "value": "286",
                        "label": "Caja municipal de ahorro y crédito tacna"
                    },
                    {
                        "value": "281",
                        "label": "Caja municipal de ahorro y crédito trujillo"
                    },
                    {
                        "value": "267",
                        "label": "Citibank"
                    },
                    {
                        "value": "274",
                        "label": "Crediscotia financiera"
                    },
                    {
                        "value": "275",
                        "label": "Mi banco"
                    },
                    {
                        "value": "278",
                        "label": "Santander"
                    },
                    {
                        "value": "268",
                        "label": "Scotiabank"
                    }
                ]
            },
            {
                "type": "select",
                "name": "Tipo",
                "key": "account_type_bank",
                "options": [
                    {
                        "value": "C",
                        "label": "Cuenta corriente"
                    },
                    {
                        "value": "S",
                        "label": "Cuenta de ahorros"
                    },
                    {
                        "value": "M",
                        "label": "Cuenta maestra"
                    }
                ]
            },
            {
                "type": "text",
                "name": "Código interbancario",
                "key": "account_bank",
                "min": 20,
                "max": 20
            },
            {
                "type": "select",
                "name": "Tipo de cliente",
                "key": "fc_customer_type",
                "options": [
                    {
                        "value": "business",
                        "label": "Empresa"
                    },
                    {
                        "value": "natural",
                        "label": "Natural"
                    }
                ]
            },
            {
                "type": "text",
                "name": "Nombre completo",
                "key": "fc_legal_name",
                "min": 1,
                "max": 50,
                "when": {
                    "key": "fc_customer_type",
                    "value": "natural"
                }
            },
            {
                "type": "select",
                "name": "Tipo de documento",
                "key": "fc_document_type",
                "options": [
                    {
                        "value": "company_id",
                        "label": "Documento de identificación de empresas"
                    },
                    {
                        "value": "dni",
                        "label": "Documento nacional de identidad"
                    },
                    {
                        "value": "passport",
                        "label": "Pasaporte"
                    }
                ],
                "when": {
                    "key": "fc_customer_type",
                    "value": "natural"
                }
            },
            {
                "type": "text",
                "name": "Número de documento",
                "key": "fc_document_number",
                "min": 1,
                "max": 50,
                "when": {
                    "key": "fc_customer_type",
                    "value": "natural"
                }
            },
            {
                "type": "text",
                "name": "Domicilio completo",
                "key": "fc_legal_address",
                "min": 1,
                "max": 200,
                "when": {
                    "key": "fc_customer_type",
                    "value": "natural"
                }
            },
            {
                "type": "text",
                "name": "Razón social",
                "key": "fc_legal_name",
                "min": 1,
                "max": 50,
                "when": {
                    "key": "fc_customer_type",
                    "value": "business"
                }
            },
            {
                "type": "text",
                "name": "Nombre fantasía",
                "key": "fc_trade_name",
                "min": 0,
                "max": 50,
                "when": {
                    "key": "fc_customer_type",
                    "value": "business"
                }
            },
            {
                "type": "text",
                "name": "Número de TAX ID",
                "key": "fc_tax_id",
                "min": 1,
                "max": 50,
                "when": {
                    "key": "fc_customer_type",
                    "value": "business"
                }
            },
            {
                "type": "text",
                "name": "Domicilio legal",
                "key": "fc_legal_address",
                "min": 1,
                "max": 200,
                "when": {
                    "key": "fc_customer_type",
                    "value": "business"
                }
            },
            {
                "type": "text",
                "name": "Fecha de nacimiento (yyyy-mm-dd)",
                "key": "fc_birthdate",
                "when": {
                    "key": "fc_customer_type",
                    "value": "natural"
                }
            },
            {
                "type": "select",
                "name": "Propósito",
                "key": "purpose",
                "options": [
                    {
                        "value": "ISSAVG",
                        "label": "Ahorro / jubilación"
                    },
                    {
                        "value": "ISGDDS",
                        "label": "Compra venta de bienes"
                    },
                    {
                        "value": "ISSCVE",
                        "label": "Compra venta de servicios"
                    },
                    {
                        "value": "EPDISP",
                        "label": "Disponibilidades"
                    },
                    {
                        "value": "ISSTDY",
                        "label": "Educación"
                    },
                    {
                        "value": "EPPROP",
                        "label": "Inmuebles"
                    },
                    {
                        "value": "EPFAMT",
                        "label": "Mantenimiento familiar"
                    },
                    {
                        "value": "EPREMT",
                        "label": "Otros"
                    },
                    {
                        "value": "ISTAXS",
                        "label": "Pago de impuestos"
                    },
                    {
                        "value": "EPIVST",
                        "label": "Pago de inversión"
                    },
                    {
                        "value": "ISPAYR",
                        "label": "Pago de nómina"
                    },
                    {
                        "value": "ISSUPP",
                        "label": "Pago de proveedor"
                    },
                    {
                        "value": "ISMDCS",
                        "label": "Salud"
                    },
                    {
                        "value": "EPTOUR",
                        "label": "Turismo"
                    }
                ]
            },
            {
                "type": "text",
                "name": "Comentario",
                "key": "purpose_comentary",
                "min": 5,
                "max": 50
            }
        ]
    }
}
```

</details>

### **Step 3: Add Beneficiary Payment Details**

Submit a `POST` request to add the beneficiary payment details using the obtained form structure:

_POST \{{host\}}/beneficiaries/payment-methods/_

**Payload Example**

*   Argentina

    ```json
    {
        "gateway_id": 492,
        "nickname": "Arg acct",
        "currency": "ARS",
        "payment_data": {
    		  "beneficiary_type": "Individual",
    		  "beneficiary_first_name": "Louis Favour",
    		  "beneficiary_last_name": "Chigemezu",
    		  "company_name": null,
    		  "beneficiary_email": "user@example.com", // Not provided in data
    		  "beneficiary_address": "Address not provided", // Placeholder
    		  "beneficiary_document_type": "CUIL",
    		  "beneficiary_document_number": "20631466665", // CUIL/T 20-63146666-5 (formatted without hyphens)
    		  "bank_code": "92", // Banco Ciudad's code
    		  "account_type_bank": "C", // Default to "Cuenta corriente"
    		  "account_bank": "0290015510000595848657", // CBU formatted without hyphens
    		  "fc_customer_type": "natural",
    		  "fc_legal_name": "Louis Favour Chigemezu",
    		  "fc_document_type": "dni",
    		  "fc_document_number": "63146666", // Last 8 digits of CUIL
    		  "fc_legal_address": "Address not provided", // Placeholder
    		  "fc_birthdate": "1990-01-01", // Placeholder (required field)
    		  "purpose": "EPFAMT", // "Mantenimiento familiar"
    		  "purpose_comentary": "Mantenimiento familiar"
    		}
    }

    ```
*   Chile

    ```json
    {
        "gateway_id": 505,
        "nickname": "CHL acct",
        "currency": "CLP",
        "payment_data": {
        "beneficiary_id" : "777920731",
        "beneficiary_name" : "Zee Technologies spa",
        "beneficiary_account" : "89512227",
        "beneficiary_account_type": "2",
        "beneficiary_bank_code": "016",
        "beneficiary_email": "michael@yativo.com",
        "description": "transfer"
    }
        //"customer_id": "d2be5158-ea3f-40ab-88e8-7c7d10fa04f4"
    }
    ```
*   Colombia

    ```json
    {
        "gateway_id": 2,
        "nickname": "COL acct",
        "currency": "COL",
        "payment_data": {
        "bankAccount" : "059-000073-51",
        "AccountType" : "2",
        "bankCode" : "007"
    }
        //"customer_id": "d2be5158-ea3f-40ab-88e8-7c7d10fa04f4"
    }
    ```
*   Mexico

    ```json
    {
        "gateway_id": 1,
        "nickname": "MXN acct",
        "currency": "MXN",
        "payment_data": {
        "clabe" : "638180010192109625",
        "beneficiary": "Carolina Rosero"
    }
        //"customer_id": "d2be5158-ea3f-40ab-88e8-7c7d10fa04f4"
    }
    ```
*   Peru

    ```json
    {
        "gateway_id": 501,
        "nickname": "Peru acct",
        "currency": "PEN",
        "payment_data": {
        "beneficiary_first_name" : "Laureano Serafin",
        "beneficiary_last_name" : "Rodriguez Polo",
        "beneficiary_email" : "emma@yativo.com",
        "beneficiary_address": "1 saint street, Lima",
        "city": "Lima",
        "phone": "099922",
        "beneficiary_document_type": "DNI",
        "beneficiary_document_number": 40224529,
        "bank_code": 265,
        "account_type_bank": "c",
        "account_bank": "00219311305166509915",
        "fc_customer_type": "natural",
        "fc_legal_name" : "Laureano Serafin Rodriguez Polo",
        "fc_document_type": "DNI",
        "fc_document_number": 40224529,
        "fc_legal_address": "1 saint street, Lima",
        "fc_birthdate": "1990-02-02",
        "purpose": "ISSCVE",
        "purpose_comentary": "Payment"
    }
        //"customer_id": "d2be5158-ea3f-40ab-88e8-7c7d10fa04f4"
    }
    ```

**Response Example:**

*   Argentina

    ```json
    {
        "status": "success",
        "status_code": 200,
        "message": "Request successful",
        "data": {
            "message": "Payment data processed successfully",
            "data": {
                "user_id": 4,
                "currency": "ARS",
                "gateway_id": 492,
                "nickname": "Arg acct",
                "address": null,
                "payment_data": {
                    "beneficiary_type": "Individual",
                    "beneficiary_first_name": "Louis Favour",
                    "beneficiary_last_name": "Chigemezu",
                    "company_name": null,
                    "beneficiary_email": "user@example.com",
                    "beneficiary_address": "Address not provided",
                    "beneficiary_document_type": "CUIL",
                    "beneficiary_document_number": "20631466665",
                    "bank_code": "92",
                    "account_type_bank": "C",
                    "account_bank": "0290015510000595848657",
                    "fc_customer_type": "natural",
                    "fc_legal_name": "Louis Favour Chigemezu",
                    "fc_document_type": "dni",
                    "fc_document_number": "63146666",
                    "fc_legal_address": "Address not provided",
                    "fc_birthdate": "1990-01-01",
                    "purpose": "EPFAMT",
                    "purpose_comentary": "Mantenimiento familiar"
                },
                "beneficiary_id": null,
                "created_at": "2025-02-17T11:38:04.000000Z",
                "id": 7
            }
        }
    }
    ```
*   Chile

    ```json
    {
        "status": "success",
        "status_code": 200,
        "message": "Request successful",
        "data": {
            "message": "Payment data processed successfully",
            "data": {
                "user_id": 4,
                "currency": "CLP",
                "gateway_id": 505,
                "nickname": "CHL acct",
                "address": null,
                "payment_data": {
                    "beneficiary_id": "777920731",
                    "beneficiary_name": "Zee Technologies spa",
                    "beneficiary_account": "89512227",
                    "beneficiary_account_type": "2",
                    "beneficiary_bank_code": "016",
                    "beneficiary_email": "michael@yativo.com",
                    "description": "transfer"
                },
                "beneficiary_id": null,
                "created_at": "2025-02-17T13:35:19.000000Z",
                "id": 12
            }
        }
    }
    ```
*   Colombia

    ```json
    {
        "status": "success",
        "status_code": 200,
        "message": "Request successful",
        "data": {
            "message": "Payment data processed successfully",
            "data": {
                "user_id": 4,
                "currency": "COP",
                "gateway_id": 2,
                "nickname": "COL acct",
                "address": null,
                "payment_data": {
                    "bankAccount": "059-000073-51",
                    "AccountType": "2",
                    "bankCode": "007"
                },
                "beneficiary_id": null,
                "created_at": "2025-02-17T13:22:48.000000Z",
                "id": 11
            }
        }
    }
    ```
*   Mexico

    ```json
    {
        "status": "success",
        "status_code": 200,
        "message": "Request successful",
        "data": {
            "message": "Payment data processed successfully",
            "data": {
                "user_id": 4,
                "currency": "MXN",
                "gateway_id": 1,
                "nickname": "MXN acct",
                "address": null,
                "payment_data": {
                    "clabe": "638180010192109625",
                    "beneficiary": "Carolina Rosero"
                },
                "beneficiary_id": null,
                "created_at": "2025-02-17T12:41:32.000000Z",
                "id": 9
            }
        }
    }
    ```
*   Peru

    ```json
    {
        "status": "success",
        "status_code": 200,
        "message": "Request successful",
        "data": {
            "message": "Payment data processed successfully",
            "data": {
                "user_id": 4,
                "currency": "PEN",
                "gateway_id": 501,
                "nickname": "Peru acct",
                "address": null,
                "payment_data": {
                    "beneficiary_first_name": "Laureano Serafin",
                    "beneficiary_last_name": "Rodriguez Polo",
                    "beneficiary_email": "emma@yativo.com",
                    "beneficiary_address": "1 saint street, Lima",
                    "city": "Lima",
                    "phone": "099922",
                    "beneficiary_document_type": "DNI",
                    "beneficiary_document_number": 40224529,
                    "bank_code": 265,
                    "account_type_bank": "c",
                    "account_bank": "00219311305166509915",
                    "fc_customer_type": "natural",
                    "fc_legal_name": "Laureano Serafin Rodriguez Polo",
                    "fc_document_type": "DNI",
                    "fc_document_number": 40224529,
                    "fc_legal_address": "1 saint street, Lima",
                    "fc_birthdate": "1990-02-02",
                    "purpose": "ISSCVE",
                    "purpose_comentary": "Payment"
                },
                "beneficiary_id": null,
                "created_at": "2025-02-17T13:06:48.000000Z",
                "id": 10
            }
        }
    }
    ```

### **Step 4: Retrieve Beneficiary Payment Details**

To retrieve all added beneficiary payment details, make a `GET` request to:

_GET \{{host\}}/beneficiaries/payment-methods/all_

**Response Example:**

```json
{
    "status": "success",
    "status_code": 200,
    "message": "Request successful",
    "data": [
        {
            "id": 12,
            "gateway_id": 505,
            "beneficiary_id": null,
            "nickname": "CHL acct",
            "currency": "CLP",
            "address": null,
            "payment_data": {
                "beneficiary_id": "777920731",
                "beneficiary_name": "Zee Technologies spa",
                "beneficiary_account": "89512227",
                "beneficiary_account_type": "2",
                "beneficiary_bank_code": "016",
                "beneficiary_email": "michael@yativo.com",
                "description": "transfer"
            },
            "created_at": "2025-02-17T13:35:19.000000Z",
            "user_id": 4,
            "bridge_id": null,
            "bridge_customer_id": null,
            "bridge_response": null,
            "gateway": {
                "id": 505,
                "method_name": "Bank Transfer",
                "country": "CHL",
                "currency": "CLP",
                "payment_method_code": null,
                "cutoff_hrs_start": null,
                "cutoff_hrs_end": null,
                "base_currency": "CLP",
                "exchange_rate_float": null
            }
        },
        {
            "id": 11,
            "gateway_id": 2,
            "beneficiary_id": null,
            "nickname": "COL acct",
            "currency": "COP",
            "address": null,
            "payment_data": {
                "bankAccount": "059-000073-51",
                "AccountType": "2",
                "bankCode": "007"
            },
            "created_at": "2025-02-17T13:22:48.000000Z",
            "user_id": 4,
            "bridge_id": null,
            "bridge_customer_id": null,
            "bridge_response": null,
            "gateway": {
                "id": 2,
                "method_name": "Bank Transfer",
                "country": "COL",
                "currency": "COP",
                "payment_method_code": null,
                "cutoff_hrs_start": null,
                "cutoff_hrs_end": null,
                "base_currency": "USD",
                "exchange_rate_float": null
            }
        },
        {
            "id": 10,
            "gateway_id": 501,
            "beneficiary_id": null,
            "nickname": "Peru acct",
            "currency": "PEN",
            "address": null,
            "payment_data": {
                "beneficiary_first_name": "Laureano Serafin",
                "beneficiary_last_name": "Rodriguez Polo",
                "beneficiary_email": "emma@yativo.com",
                "beneficiary_address": "1 saint street, Lima",
                "city": "Lima",
                "phone": "099922",
                "beneficiary_document_type": "DNI",
                "beneficiary_document_number": 40224529,
                "bank_code": 265,
                "account_type_bank": "c",
                "account_bank": "00219311305166509915",
                "fc_customer_type": "natural",
                "fc_legal_name": "Laureano Serafin Rodriguez Polo",
                "fc_document_type": "DNI",
                "fc_document_number": 40224529,
                "fc_legal_address": "1 saint street, Lima",
                "fc_birthdate": "1990-02-02",
                "purpose": "ISSCVE",
                "purpose_comentary": "Payment"
            },
            "created_at": "2025-02-17T13:06:48.000000Z",
            "user_id": 4,
            "bridge_id": null,
            "bridge_customer_id": null,
            "bridge_response": null,
            "gateway": {
                "id": 501,
                "method_name": "Bank Transfer",
                "country": "PER",
                "currency": "PEN",
                "payment_method_code": null,
                "cutoff_hrs_start": null,
                "cutoff_hrs_end": null,
                "base_currency": "USD",
                "exchange_rate_float": null
            }
        },
        {
            "id": 9,
            "gateway_id": 1,
            "beneficiary_id": null,
            "nickname": "MXN acct",
            "currency": "MXN",
            "address": null,
            "payment_data": {
                "clabe": "638180010192109625",
                "beneficiary": "Carolina Rosero"
            },
            "created_at": "2025-02-17T12:41:32.000000Z",
            "user_id": 4,
            "bridge_id": null,
            "bridge_customer_id": null,
            "bridge_response": null,
            "gateway": {
                "id": 1,
                "method_name": "SPEI",
                "country": "MEX",
                "currency": "MXN",
                "payment_method_code": null,
                "cutoff_hrs_start": null,
                "cutoff_hrs_end": null,
                "base_currency": "USD",
                "exchange_rate_float": null
            }
        },
        {
            "id": 8,
            "gateway_id": 494,
            "beneficiary_id": null,
            "nickname": "BRA acct",
            "currency": "BRL",
            "address": null,
            "payment_data": {
                "taxId": "41901030806",
                "pixKey": "41901030806"
            },
            "created_at": "2025-02-17T12:15:52.000000Z",
            "user_id": 4,
            "bridge_id": null,
            "bridge_customer_id": null,
            "bridge_response": null,
            "gateway": {
                "id": 494,
                "method_name": "Pix",
                "country": "BRA",
                "currency": "BRL",
                "payment_method_code": null,
                "cutoff_hrs_start": null,
                "cutoff_hrs_end": null,
                "base_currency": "USD,BRL",
                "exchange_rate_float": null
            }
        },
        {
            "id": 7,
            "gateway_id": 492,
            "beneficiary_id": null,
            "nickname": "Arg acct",
            "currency": "ARS",
            "address": null,
            "payment_data": {
                "beneficiary_type": "Individual",
                "beneficiary_first_name": "Louis Favour",
                "beneficiary_last_name": "Chigemezu",
                "company_name": null,
                "beneficiary_email": "user@example.com",
                "beneficiary_address": "Address not provided",
                "beneficiary_document_type": "CUIL",
                "beneficiary_document_number": "20631466665",
                "bank_code": "92",
                "account_type_bank": "C",
                "account_bank": "0290015510000595848657",
                "fc_customer_type": "natural",
                "fc_legal_name": "Louis Favour Chigemezu",
                "fc_document_type": "dni",
                "fc_document_number": "63146666",
                "fc_legal_address": "Address not provided",
                "fc_birthdate": "1990-01-01",
                "purpose": "EPFAMT",
                "purpose_comentary": "Mantenimiento familiar"
            },
            "created_at": "2025-02-17T11:38:04.000000Z",
            "user_id": 4,
            "bridge_id": null,
            "bridge_customer_id": null,
            "bridge_response": null,
            "gateway": {
                "id": 492,
                "method_name": "Bank Transfer",
                "country": "ARG",
                "currency": "ARS",
                "payment_method_code": null,
                "cutoff_hrs_start": null,
                "cutoff_hrs_end": null,
                "base_currency": "USD",
                "exchange_rate_float": null
            }
        },
        {
            "id": 5,
            "gateway_id": 492,
            "beneficiary_id": null,
            "nickname": "Arg acct",
            "currency": "ARS",
            "address": null,
            "payment_data": {
                "beneficiary_type": "Individual",
                "beneficiary_first_name": "Louis Favour",
                "beneficiary_last_name": "Chigemezu",
                "company_name": null,
                "beneficiary_email": "user@example.com",
                "beneficiary_address": "Address not provided",
                "beneficiary_document_type": "CUIL",
                "beneficiary_document_number": "20631466665",
                "bank_code": "92",
                "account_type_bank": "C",
                "account_bank": "0290015510000595848657",
                "fc_customer_type": "natural",
                "fc_legal_name": "Louis Favour Chigemezu",
                "fc_document_type": "dni",
                "fc_document_number": "63146666",
                "fc_legal_address": "Address not provided",
                "fc_birthdate": "1990-01-01",
                "purpose": "EPFAMT",
                "purpose_comentary": "Mantenimiento familiar"
            },
            "created_at": "2025-02-16T21:31:52.000000Z",
            "user_id": 4,
            "bridge_id": null,
            "bridge_customer_id": null,
            "bridge_response": null,
            "gateway": {
                "id": 492,
                "method_name": "Bank Transfer",
                "country": "ARG",
                "currency": "ARS",
                "payment_method_code": null,
                "cutoff_hrs_start": null,
                "cutoff_hrs_end": null,
                "base_currency": "USD",
                "exchange_rate_float": null
            }
        },
        {
            "id": 4,
            "gateway_id": 333,
            "beneficiary_id": null,
            "nickname": "Bridge payment sample EUR",
            "currency": "IDR",
            "address": null,
            "payment_data": {
                "account_number": "FR2213127390004078439692S06",
                "account_name": "Joanne Smith",
                "routing_number": "SWIFT42345",
                "account_type": "iban",
                "address": {
                    "line1": "456 Market Ave",
                    "line2": null,
                    "city": "Paris",
                    "state": "Île-de-France",
                    "postal_code": "75001",
                    "country": "FR"
                },
                "iban_account_number": "FR2213127390004078439692S06",
                "iban_bic": "BNPAFRPP",
                "iban_country": "FR",
                "account_owner_type": "individual",
                "first_name": "Joanne",
                "last_name": "Smith"
            },
            "created_at": "2025-02-15T12:36:53.000000Z",
            "user_id": 4,
            "bridge_id": null,
            "bridge_customer_id": null,
            "bridge_response": null,
            "gateway": {
                "id": 333,
                "method_name": "Bank Artha Graha",
                "country": "IDN",
                "currency": "IDR",
                "payment_method_code": null,
                "cutoff_hrs_start": "1",
                "cutoff_hrs_end": "15",
                "base_currency": "USD",
                "exchange_rate_float": null
            }
        },
        {
            "id": 2,
            "gateway_id": 505,
            "beneficiary_id": null,
            "nickname": "palmpay",
            "currency": "CLP",
            "address": null,
            "payment_data": {
                "accountNumber": "8188572925"
            },
            "created_at": "2025-02-13T21:08:49.000000Z",
            "user_id": 4,
            "bridge_id": null,
            "bridge_customer_id": null,
            "bridge_response": null,
            "gateway": {
                "id": 505,
                "method_name": "Bank Transfer",
                "country": "CHL",
                "currency": "CLP",
                "payment_method_code": null,
                "cutoff_hrs_start": null,
                "cutoff_hrs_end": null,
                "base_currency": "CLP",
                "exchange_rate_float": null
            }
        }
    ]
}
```

### **Step 5: Initiate Payout**

Use the `id` from the previous response as the `payment_method_id` to make a payout request:

_POST \{{host\}}/wallet/payout_

**Payload Example:**

*   Argentina

    ```json
    {
        "debit_wallet": "USD",
        "amount": 17,
        "payment_method_id": 5
    }
    ```
*   Chile

    ```json
    {
        "debit_wallet": "CLP",
        "amount": 1000,
        "payment_method_id": 12
    }
    ```
*   Colombia

    ```json
    {
        "debit_wallet": "USD",
        "amount": 10000,
        "payment_method_id": 11
    }
    ```
*   Mexico

    ```json
    {
        "debit_wallet": "USD",
        "amount": 1,
        "payment_method_id": 9
    }
    ```
*   Peru

    ```json
    {
        "debit_wallet": "USD",
        "amount": 75,
        "payment_method_id": 10
    }
    ```

**Response Example:**

*   Argentina

    ```json
    {
        "status": "success",
        "status_code": 201,
        "message": "Withdrawal request received and will be processed shortly.",
        "data": {
            "amount": 17,
            "debit_wallet": "USD",
            "user_id": 4,
            "raw_data": {
                "debit_wallet": "USD",
                "amount": 17,
                "payment_method_id": 5
            },
            "currency": "ARS",
            "beneficiary_id": 5,
            "payout_id": "bf3b5096-f24d-419c-967f-dd8c75512ec4",
            "updated_at": "2025-02-17T11:34:38.000000Z",
            "created_at": "2025-02-17T11:34:38.000000Z"
        }
    }
    ```
*   Chile

    ```json
    {
        "status": "success",
        "status_code": 201,
        "message": "Withdrawal request received and will be processed shortly.",
        "data": {
            "amount": 10000,
            "debit_wallet": "CLP",
            "user_id": 4,
            "raw_data": {
                "debit_wallet": "CLP,
                "amount": 1000,
                "payment_method_id": 12
            },
            "currency": "CLP",
            "beneficiary_id": 12,
            "payout_id": "4a269cd6-f7a3-47e3-9946-d954a21c57da",
            "updated_at": "2025-02-17T13:23:57.000000Z",
            "created_at": "2025-02-17T13:23:57.000000Z"
        }
    }
    ```
*   Colombia

    ```json
    {
        "status": "success",
        "status_code": 201,
        "message": "Withdrawal request received and will be processed shortly.",
        "data": {
            "amount": 10000,
            "debit_wallet": "USD",
            "user_id": 4,
            "raw_data": {
                "debit_wallet": "USD",
                "amount": 10000,
                "payment_method_id": 11
            },
            "currency": "COP",
            "beneficiary_id": 11,
            "payout_id": "4a269cd6-f7a3-47e3-9946-d954a21c57da",
            "updated_at": "2025-02-17T13:23:57.000000Z",
            "created_at": "2025-02-17T13:23:57.000000Z"
        }
    }
    ```
*   Mexico

    ```json
    {
        "status": "success",
        "status_code": 201,
        "message": "Withdrawal request received and will be processed shortly.",
        "data": {
            "amount": 1,
            "debit_wallet": "USD",
            "user_id": 4,
            "raw_data": {
                "debit_wallet": "USD",
                "amount": 1,
                "payment_method_id": 9
            },
            "currency": "MXN",
            "beneficiary_id": 9,
            "payout_id": "767b0063-2427-421e-a56c-b3253a1d0bde",
            "updated_at": "2025-02-17T12:42:17.000000Z",
            "created_at": "2025-02-17T12:42:17.000000Z"
        }
    }
    ```
*   Peru

    ```json
    {
        "status": "success",
        "status_code": 201,
        "message": "Withdrawal request received and will be processed shortly.",
        "data": {
            "amount": 75,
            "debit_wallet": "USD",
            "user_id": 4,
            "raw_data": {
                "debit_wallet": "USD",
                "amount": 75,
                "payment_method_id": 10
            },
            "currency": "PEN",
            "beneficiary_id": 10,
            "payout_id": "ca59fba7-dad6-4d2a-bb04-deb4500b68d3",
            "updated_at": "2025-02-17T13:07:55.000000Z",
            "created_at": "2025-02-17T13:07:55.000000Z"
        }
    }
    ```

### **Authentication & Idempotency**

* **Authentication:** All requests must be authenticated using an API key.
* **Idempotency:** POST requests require a unique Idempotency-Key header to ensure duplicate requests are not processed multiple times.

For further support, please contact Us.

```json
{
    "gateway_id": 184,
    "nickname": "EUR acct",
    "currency": "EUR",
    "payment_data": {
    "account_number" : "8339856447",
    "account_name" : "Michael Chukwuka Bernard",
    "routing_number" : "026073150",
    "account_type": "iban",
    "beneficiary_bank_code": "016",
    "beneficiary_email": "michael@yativo.com",
    "description": "transfer"
}
    //"customer_id": "d2be5158-ea3f-40ab-88e8-7c7d10fa04f4"
}
```
