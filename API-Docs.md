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
    ],
    "links": {
        "first": "https://app.akaunting.com/api/users?page=1",
        "last": "https://app.akaunting.com/api/users?page=1",
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
                "url": "https://app.akaunting.com/api/users?page=1",
                "label": "1",
                "active": true
            },
            {
                "url": null,
                "label": "Next",
                "active": false
            }
        ],
        "path": "https://app.akaunting.com/api/users",
        "per_page": 25,
        "to": 1,
        "total": 1
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
