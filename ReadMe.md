# Akaunting API Documentation

## Purpose

This repository contains API documentation for integrating with the [Akaunting](https://akaunting.com) accounting platform. It is designed for AI coding agents to read, understand, and generate code against the Akaunting REST API.

## Structure

- `API-Docs.md` — Endpoint documentation with request/response examples
- `ReadMe.md` — This file

## For AI Agents

When using this repo as context:

1. Read `API-Docs.md` for available endpoints, auth method, and response formats
2. All endpoints use **Basic Auth** with email/password
3. The `X-Company` header is required for most endpoints
4. Variable placeholders use `{{variable_name}}` syntax (e.g., `{{akaunting_url}}`)

## Environment Variables

| Variable | Description | Example |
|----------|-------------|---------|
| `AKAUNTING_URL` | Base API URL | `https://app.akaunting.com/api` |
| `AKAUNTING_EMAIL` | Auth email | `user@example.com` |
| `AKAUNTING_PASSWORD` | Auth password | `your_password` |
| `AKAUNTING_COMPANY_ID` | Company identifier | `399523` |
| `AKAUNTING_PAGE` | Pagination page | `1` |
| `AKAUNTING_LIMIT` | Results per page | `25` |
| `AKAUNTING_CURRENCY_ID` | Default currency ID | `1` |
| `AKAUNTING_TAX_ID` | Default tax ID | `1` |

> **Note:** These values can be stored in `.env` or in your database as Akaunting config. Dynamic IDs (document_id, contact_id, item_id, etc.) are per-request values — store them in your database.

## Current Endpoints

### Users
- List users

### Companies
- List companies

### Items
- List items

### Customers (Contacts)
- List customers
- Create customer

### Vendors (Contacts)
- List vendors
- Create vendor

### Invoices (Documents)
- List invoices
- Create invoice
- Get invoice
- Update invoice
- Delete invoice
- Add invoice payment

### Bills
- List bills
- Get bill
- Create bill

### Transactions
- Create expense transaction
- List expense transactions

More endpoints will be added as they are documented.