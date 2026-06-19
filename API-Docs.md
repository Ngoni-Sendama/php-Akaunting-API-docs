# Using Akaunting API in Laravel Projects

## Overview
This documentation explains how to integrate the Akaunting API into a Laravel application. Akaunting is an open-source accounting software, and its API allows you to programmatically manage invoices, contacts, accounts, and other financial data.

## Environment Configuration

Before making any API calls, configure the following environment variables in your Laravel project's `.env` file:

```env
AKAUNTING_URL=https://app.akaunting.com/api
AKAUNTING_EMAIL=your_email
AKAUNTING_PASSWORD=your_password
AKAUNTING_PAGE=1
AKAUNTING_LIMIT=25
AKAUNTING_COMPANY_ID=your_company_id
AKAUNTING_ITEM_ID=your_item_id
AKAUNTING_USER_ID=your_user_id
AKAUNTING_CONTACT_ID=your_contact_id
AKAUNTING_DOCUMENT_ID=your_document_id
AKAUNTING_ACCOUNT_ID=your_account_id
AKAUNTING_TRANSACTION_ID=your_transaction_id
AKAUNTING_TRANSFER_ID=your_transfer_id
AKAUNTING_TRANSFER_FROM_ACCOUNT_ID=your_transfer_from_account_id
AKAUNTING_TRANSFER_TO_ACCOUNT_ID=your_transfer_to_account_id
AKAUNTING_CATEGORY_ID=your_category_id
AKAUNTING_CURRENCY_ID=your_currency_id
AKAUNTING_TAX_ID=your_tax_id
AKAUNTING_REPORT_ID=your_report_id
```

## API Endpoints

### Users

**List Users**

`GET {{akaunting_url}}/users?page={{akaunting_page}}&limit={{akaunting_limit}}`

**Authorization**
- Basic Auth
  - Username: {{akaunting_email}}
  - Password: {{akaunting_password}}

**Request Headers**
- `X-Company`: {{akaunting_company_id}}

**Query Parameters**
- `page`: {{akaunting_page}}
- `limit`: {{akaunting_limit}}

**Code Snippet (PHP)**
```php
<?php
$client = new Client();
$headers = [
  'X-Company' => '399523',
  'Authorization' => '[[Authorization-masked-secret]]'
];
$request = new Request('GET', 'https://app.akaunting.com/api/users?page=1&limit=25', $headers);
$res = $client->sendAsync($request)->wait();
echo $res->getBody();
```

**Example Response**
```json
{
    "data": [
        {
            "id": 419518,
            "name": "Yuwa News",
            "email": "yuwanews825@gmail.com",
            "locale": "en-GB",
            "landing_page": "dashboard",
            "enabled": true,
            "created_from": "site:api",
            "created_by": 2,
            "last_logged_in_at": "2026-06-19T15:27:14+01:00",
            "created_at": "2026-06-18T14:13:06+01:00",
            "updated_at": "2026-06-19T13:38:27+01:00",
            "companies": {
                "data": [
                    {
                        "id": 399523,
                        "name": "code with tari",
                        "email": "yuwanews825@gmail.com",
                        "currency": "USD",
                        "domain": "code with tari",
                        "address": null,
                        "logo": "public/img/company.png",
                        "enabled": true,
                        "created_from": "cloud::api",
                        "created_by": 419518,
                        "created_at": "2026-06-19T13:27:06+01:00",
                        "updated_at": "2026-06-19T13:27:06+01:00"
                    }
                ]
            },
            "roles": {
                "data": [
                    {
                        "id": 2,
                        "name": "Manager",
                        "code": "manager",
                        "created_from": null,
                        "created_by": null,
                        "created_at": "2017-09-19T16:33:38+01:00",
                        "updated_at": "2022-11-02T11:54:39+00:00"
                    }
                ]
    }
}
```

### Items

**List Items**

`GET {{akaunting_url}}/items?page={{akaunting_page}}&limit={{akaunting_limit}}`

**Authorization**
- Basic Auth
  - Username: {{akaunting_email}}
  - Password: {{akaunting_password}}

**Request Headers**
- `X-Company`: {{akaunting_company_id}}

**Query Parameters**
- `page`: {{akaunting_page}}
- `limit`: {{akaunting_limit}}

**Code Snippet (PHP)**
```php
<?php
$client = new Client();
$headers = [
  'X-Company' => '399523',
  'Authorization' => '[[Authorization-masked-secret]]'
];
$request = new Request('GET', 'https://app.akaunting.com/api/items?page=1&limit=25', $headers);
$res = $client->sendAsync($request)->wait();
echo $res->getBody();
```

**Example Response**
```json
{
    "data": [
        {
            "id": 5848381,
            "company_id": 399523,
            "type": "product",
            "name": "Library Fee",
            "description": "Library Access",
            "sale_price": 50,
            "sale_price_formatted": "$50.00",
            "purchase_price": 50,
            "purchase_price_formatted": "$50.00",
            "category_id": null,
            "picture": false,
            "enabled": true,
            "created_from": "core::api",
            "created_by": 419518,
            "created_at": "2026-06-19T18:21:42+01:00",
            "updated_at": "2026-06-19T18:21:42+01:00",
            "taxes": {
                "data": []
            },
            "category": {
                "id": null,
                "company_id": null,
                "name": "N/A",
                "type": null,
                "color": null,
                "enabled": null,
                "parent_id": null,
                "created_from": null,
                "created_by": null,
                "created_at": "",
                "updated_at": ""
            }
        },
        {
            "id": 5848387,
            "company_id": 399523,
            "type": "product",
            "name": "School Fees",
            "description": "School Fees",
            "sale_price": 23,
            "sale_price_formatted": "$23.00",
            "purchase_price": 23,
            "purchase_price_formatted": "$23.00",
            "category_id": null,
            "picture": false,
            "enabled": true,
            "created_from": "core::api",
            "created_by": 419518,
            "created_at": "2026-06-19T19:12:31+01:00",
            "updated_at": "2026-06-19T19:12:31+01:00",
            "taxes": {
                "data": []
            },
            "category": {
                "id": null,
                "company_id": null,
                "name": "N/A",
                "type": null,
                "color": null,
                "enabled": null,
                "parent_id": null,
                "created_from": null,
                "created_by": null,
                "created_at": "",
                "updated_at": ""
            }
        },
        {
            "id": 5848380,
            "company_id": 399523,
            "type": "product",
            "name": "Tuition Fee",
            "description": "Term 1 Tuition",
            "sale_price": 100,
            "sale_price_formatted": "$100.00",
            "purchase_price": 100,
            "purchase_price_formatted": "$100.00",
            "category_id": null,
            "picture": false,
            "enabled": true,
            "created_from": "core::api",
            "created_by": 419518,
            "created_at": "2026-06-19T18:21:41+01:00",
            "updated_at": "2026-06-19T18:21:41+01:00",
            "taxes": {
                "data": []
            },
            "category": {
                "id": null,
                "company_id": null,
                "name": "N/A",
                "type": null,
                "color": null,
                "enabled": null,
                "parent_id": null,
                "created_from": null,
                "created_by": null,
                "created_at": "",
                "updated_at": ""
            }
        }
    ],
    "links": {
        "first": "https://app.akaunting.com/api/items?page=1",
        "last": "https://app.akaunting.com/api/items?page=1",
        "prev": null,
        "next": null
    },
    "meta": {
        "current_page": 1,
        "from": 1,
        "last_page": 1,
        "links": [
            {
                "url": null,
                "label": "Previous",
                "active": false
            },
            {
                "url": "https://app.akaunting.com/api/items?page=1",
                "label": "1",
                "active": true
            },
            {
                "url": null,
                "label": "Next",
                "active": false
            }
        ],
        "path": "https://app.akaunting.com/api/items",
        "per_page": 25,
        "to": 3,
        "total": 3
    }
}
```

### Companies

**List Companies**

`GET {{akaunting_url}}/companies`

**Authorization**
- Basic Auth
  - Username: {{akaunting_email}}
  - Password: {{akaunting_password}}

**Code Snippet (PHP)**
```php
<?php
$client = new Client();
$headers = [
  'Authorization' => '[[Authorization-masked-secret]]'
];
$request = new Request('GET', 'https://app.akaunting.com/api/companies', $headers);
$res = $client->sendAsync($request)->wait();
echo $res->getBody();
```

**Example Response**
```json
{
    "data": [
        {
            "id": 399523,
            "name": "code with tari",
            "email": "yuwanews825@gmail.com",
            "currency": "USD",
            "domain": "code with tari",
            "address": null,
            "logo": "public/img/company.png",
            "enabled": true,
            "created_from": "cloud::api",
            "created_by": 419518,
            "created_at": "2026-06-19T13:27:06+01:00",
            "updated_at": "2026-06-19T13:27:06+01:00"
        }
    ],
    "links": {
        "first": "https://app.akaunting.com/api/companies?page=1",
        "last": "https://app.akaunting.com/api/companies?page=1",
        "prev": null,
        "next": null
    },
    "meta": {
        "current_page": 1,
        "from": 1,
        "last_page": 1,
        "links": [
            {
                "url": null,
                "label": "Previous",
                "active": false
            },
            {
                "url": "https://app.akaunting.com/api/companies?page=1",
                "label": "1",
                "active": true
            },
            {
                "url": null,
                "label": "Next",
                "active": false
            }
        ],
        "path": "https://app.akaunting.com/api/companies",
        "per_page": 25,
        "to": 1,
        "total": 1
    }
}
```

### Customers (Contacts)

**List Customers**

`GET {{akaunting_url}}/contacts?search=type:customer&page={{akaunting_page}}&limit={{akaunting_limit}}`

**Authorization**
- Basic Auth
  - Username: {{akaunting_email}}
  - Password: {{akaunting_password}}

**Request Headers**
- `X-Company`: {{akaunting_company_id}}

**Query Parameters**
- `search`: `type:customer`
- `page`: {{akaunting_page}}
- `limit`: {{akaunting_limit}}

**Code Snippet (PHP)**
```php
<?php
$client = new Client();
$headers = [
  'X-Company' => '399523',
  'Authorization' => '[[Authorization-masked-secret]]'
];
$request = new Request('GET', 'https://app.akaunting.com/api/contacts?search=type:customer&page=1&limit=25', $headers);
$res = $client->sendAsync($request)->wait();
echo $res->getBody();
```

**Example Response**
```json
{
    "data": [
        {
            "id": 2380457,
            "company_id": 399523,
            "user_id": null,
            "type": "customer",
            "name": "Anotida Grace Chikwanha",
            "email": "anotida.chikwanha@student.school.com",
            "tax_number": null,
            "phone": "+263771310001",
            "address": "Harare",
            "website": null,
            "currency_code": "USD",
            "enabled": true,
            "reference": null,
            "created_from": "core::api",
            "created_by": 419518,
            "created_at": "2026-06-19T18:58:33+01:00",
            "updated_at": "2026-06-19T18:58:33+01:00",
            "contact_persons": {
                "data": []
            }
        },
        {
            "id": 2380451,
            "company_id": 399523,
            "user_id": null,
            "type": "customer",
            "name": "ngoni",
            "email": "email@gamix.co.nz",
            "tax_number": "5235667",
            "phone": "567890",
            "address": "20 Here Street",
            "website": null,
            "currency_code": "USD",
            "enabled": true,
            "reference": "84890",
            "created_from": "core::api",
            "created_by": 419518,
            "created_at": "2026-06-19T18:05:58+01:00",
            "updated_at": "2026-06-19T18:05:58+01:00",
            "contact_persons": {
                "data": []
            }
        }
    ],
    "links": {
        "first": "https://app.akaunting.com/api/contacts?page=1",
        "last": "https://app.akaunting.com/api/contacts?page=1",
        "prev": null,
        "next": null
    },
    "meta": {
        "current_page": 1,
        "from": 1,
        "last_page": 1,
        "links": [
            {
                "url": null,
                "label": "Previous",
                "active": false
            },
            {
                "url": "https://app.akaunting.com/api/contacts?page=1",
                "label": "1",
                "active": true
            },
            {
                "url": null,
                "label": "Next",
                "active": false
            }
        ],
        "path": "https://app.akaunting.com/api/contacts",
        "per_page": 25,
        "to": 10,
        "total": 10
    }
}
```

**Create Customer**

`POST {{akaunting_url}}/contacts`

**Authorization**
- Basic Auth
  - Username: {{akaunting_email}}
  - Password: {{akaunting_password}}

**Request Headers**
- `X-Company`: {{akaunting_company_id}}

**Query Parameters**
- `name`: Customer name
- `email`: Customer email
- `type`: `customer`
- `tax_number`: Tax number
- `currency_code`: Currency code (e.g., `USD`, `NZD`)
- `phone`: Phone number
- `website`: Website URL
- `address`: Street address
- `city`: City
- `post_code`: Postal code
- `country`: Country name
- `enabled`: `1` (enabled) or `0` (disabled)
- `reference`: Custom reference

**Code Snippet (PHP)**
```php
<?php
$client = new Client();
$headers = [
  'X-Company' => '399523',
  'Authorization' => '[[Authorization-masked-secret]]'
];
$request = new Request('POST', 'https://app.akaunting.com/api/contacts?name=Customer02&email=email@gamix.co.nz&tax_number=5235667&currency_code=NZD&phone=567890&website=&address=20 Here Street&enabled=1&reference=84890&type=customer&city=Auckland&post_code=2016&country=New Zealand', $headers);
$res = $client->sendAsync($request)->wait();
echo $res->getBody();
```

**Example Response**
```json
{
    "data": {
        "id": 2380451,
        "company_id": 399523,
        "user_id": null,
        "type": "customer",
        "name": "ngoni",
        "email": "email@gamix.co.nz",
        "tax_number": "5235667",
        "phone": "567890",
        "address": "20 Here Street",
        "website": null,
        "currency_code": "USD",
        "enabled": true,
        "reference": "84890",
        "created_from": "core::api",
        "created_by": 419518,
        "created_at": "2026-06-19T18:05:58+01:00",
        "updated_at": "2026-06-19T18:05:58+01:00",
        "contact_persons": {
            "data": []
        }
    }
}
```

### Invoices (Documents)

**List Invoices**

`GET {{akaunting_url}}/documents?search=type:invoice&page={{akaunting_page}}&limit={{akaunting_limit}}`

**Authorization**
- Basic Auth
  - Username: {{akaunting_email}}
  - Password: {{akaunting_password}}

**Request Headers**
- `X-Company`: {{akaunting_company_id}}

**Query Parameters**
- `search`: `type:invoice`
- `page`: {{akaunting_page}}
- `limit`: {{akaunting_limit}}

**Code Snippet (PHP)**
```php
<?php
$client = new Client();
$headers = [
  'X-Company' => '399523',
  'Authorization' => '[[Authorization-masked-secret]]'
];
$request = new Request('GET', 'https://app.akaunting.com/api/documents?search=type:invoice&page=1&limit=25', $headers);
$res = $client->sendAsync($request)->wait();
echo $res->getBody();
```

**Example Response (truncated for brevity)**
```json
{
    "data": [
        {
            "id": 3768808,
            "company_id": 399523,
            "type": "invoice",
            "document_number": "INV-00011",
            "order_number": null,
            "status": "paid",
            "issued_at": "2026-06-19T19:30:54+01:00",
            "due_at": "2026-06-19T19:30:54+01:00",
            "amount": 123,
            "amount_formatted": "$123.00",
            "category_id": 2479260,
            "currency_code": "USD",
            "currency_rate": 1,
            "contact_id": 2380455,
            "contact_name": "Rumbidzai Mavis Mugari",
            "contact_email": "rumbidzai.mugari@student.school.com",
            "notes": null,
            "items": {
                "data": [
                    {
                        "id": 69702697,
                        "item_id": 5848387,
                        "name": "School Fees",
                        "description": "School Fees",
                        "price": 23,
                        "total": 23
                    },
                    {
                        "id": 69702698,
                        "item_id": 5848380,
                        "name": "Tuition Fee",
                        "description": "Term 1 Tuition",
                        "price": 100,
                        "total": 100
                    }
                ]
            },
            "totals": {
                "data": [
                    {
                        "code": "sub_total",
                        "amount": 123
                    },
                    {
                        "code": "total",
                        "amount": 123
                    }
                ]
            }
        }
    ],
    "links": {
        "first": "https://app.akaunting.com/api/documents?page=1",
        "last": "https://app.akaunting.com/api/documents?page=1",
        "prev": null,
        "next": null
    },
    "meta": {
        "current_page": 1,
        "from": 1,
        "last_page": 1,
        "per_page": 25,
        "total": 11
    }
}
```

**Create Invoice**

`POST {{akaunting_url}}/documents`

**Authorization**
- Basic Auth
  - Username: {{akaunting_email}}
  - Password: {{akaunting_password}}

**Request Headers**
- `X-Company`: {{akaunting_company_id}}

**Query Parameters**

| Parameter | Description | Example |
|-----------|-------------|---------|
| `type` | Document type | `invoice` |
| `search` | Filter type | `type:invoice` |
| `document_number` | Invoice number | `0000003` |
| `status` | Draft or paid | `draft` |
| `category_id` | Income category ID | `3` |
| `account_id` | Account ID | `497848` |
| `currency_code` | Currency code | `USD` |
| `currency_rate` | Currency rate | `1` |
| `issued_at` | Issue date | `2022-04-23` |
| `due_at` | Due date | `2022-05-22` |
| `contact_id` | Customer ID | `2` |
| `contact_name` | Customer name | `Name` |
| `contact_email` | Customer email | `mail@mail.com` |
| `contact_address` | Customer address | `Client address` |
| `notes` | Invoice notes | `This is note for invoice` |
| `amount` | Total amount | `2` |
| `items[0][item_id]` | Item ID | `1` |
| `items[0][name]` | Item name | `Service` |
| `items[0][quantity]` | Quantity | `2` |
| `items[0][price]` | Unit price | `1` |
| `items[0][total]` | Line total | `2` |
| `items[0][discount]` | Discount | `0` |
| `items[0][description]` | Item description | `This is custom item description` |
| `items[0][tax_ids][0]` | Tax ID | `1` |

**Code Snippet (PHP)**
```php
<?php
$client = new Client();
$headers = [
  'X-Company' => '399523',
  'Authorization' => '[[Authorization-masked-secret]]'
];
$request = new Request('POST', 'https://app.akaunting.com/api/documents?category_id=3&document_number=0000003&status=draft&issued_at=2022-04-23&due_at=2022-05-22&account_id=497848&currency_code=USD&currency_rate=1&notes=This is note for invoice&contact_id=2&contact_name=Name&contact_email=mail@mail.com&contact_address=Client address&items[0][item_id]=1&items[0][name]=Service&items[0][quantity]=2&items[0][price]=1&items[0][total]=2&items[0][discount]=0&items[0][description]=This is custom item description&items[0][tax_ids][0]=1&items[0][tax_ids][1]=1&amount=2&type=invoice&search=type:invoice', $headers);
$res = $client->sendAsync($request)->wait();
echo $res->getBody();
```

**Example Response**
```json
{
    "data": {
        "id": 3768805,
        "company_id": 399523,
        "type": "invoice",
        "document_number": "0000003",
        "status": "draft",
        "issued_at": "2022-04-23T19:21:32+01:00",
        "due_at": "2022-05-22T19:21:32+01:00",
        "amount": 4,
        "amount_formatted": "$4.00",
        "category_id": "3",
        "currency_code": "USD",
        "currency_rate": 1,
        "contact_id": "2",
        "contact_name": "Name",
        "contact_email": "mail@mail.com",
        "contact_address": "Client address",
        "notes": "This is note for invoice",
        "items": {
            "data": [
                {
                    "id": 69702681,
                    "item_id": 1,
                    "name": "Service",
                    "description": "This is custom item description",
                    "price": 1,
                    "total": 2
                }
            ]
        },
        "totals": {
            "data": [
                {
                    "code": "sub_total",
                    "amount": 2
                },
                {
                    "code": "total",
                    "amount": 4
                }
            ]
        }
    }
}
```

**Get Invoice**

`GET {{akaunting_url}}/documents/{{akaunting_document_id}}?search=type:invoice`

**Authorization**
- Basic Auth
  - Username: {{akaunting_email}}
  - Password: {{akaunting_password}}

**Request Headers**
- `X-Company`: {{akaunting_company_id}}

**Query Parameters**
- `search`: `type:invoice`

**Code Snippet (PHP)**
```php
<?php
$client = new Client();
$headers = [
  'X-Company' => '399523',
  'Authorization' => '[[Authorization-masked-secret]]'
];
$request = new Request('GET', 'https://app.akaunting.com/api/documents/3768808?search=type:invoice', $headers);
$res = $client->sendAsync($request)->wait();
echo $res->getBody();
```

**Example Response**
```json
{
    "data": {
        "id": 3768808,
        "company_id": 399523,
        "type": "invoice",
        "document_number": "INV-00011",
        "status": "paid",
        "issued_at": "2026-06-19T19:30:54+01:00",
        "due_at": "2026-06-19T19:30:54+01:00",
        "amount": 123,
        "amount_formatted": "$123.00",
        "category_id": 2479260,
        "currency_code": "USD",
        "currency_rate": 1,
        "contact_id": 2380455,
        "contact_name": "Rumbidzai Mavis Mugari",
        "contact_email": "rumbidzai.mugari@student.school.com",
        "contact_phone": "+263771310003",
        "contact_address": "Harare",
        "notes": null,
        "items": {
            "data": [
                {
                    "id": 69702697,
                    "item_id": 5848387,
                    "name": "School Fees",
                    "description": "School Fees",
                    "price": 23,
                    "total": 23
                },
                {
                    "id": 69702698,
                    "item_id": 5848380,
                    "name": "Tuition Fee",
                    "description": "Term 1 Tuition",
                    "price": 100,
                    "total": 100
                }
            ]
        },
        "totals": {
            "data": [
                {
                    "code": "sub_total",
                    "amount": 123
                },
                {
                    "code": "total",
                    "amount": 123
                }
            ]
        },
        "transactions": {
            "data": [
                {
                    "id": 7108676,
                    "number": "TRA-00001",
                    "type": "income",
                    "amount": 123,
                    "paid_at": "2026-06-19T19:31:13+01:00",
                    "payment_method": "offline-payments.cash.1"
                }
            ]
        }
    }
}
```
