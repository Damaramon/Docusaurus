---
title: Inventory API Documentation
sidebar_position: 1
---

## Overview

Inventory API is a REST API used by an internal inventory application to retrieve, create, and view item data.

## Base Information

| Field | Value |
| --- | --- |
| Base URL | `http://localhost:3000/api` |
| Content Type | `application/json` |
| Authentication | Bearer Token |
| API Version | `v1` |

## Authentication

All endpoints require a Bearer Token in the HTTP Authorization header.

```
Authorization: Bearer YOUR_TOKEN
Content-Type: application/json
```

## Endpoints

| Method | Path | Description |
| --- | --- | --- |
| GET | `/items` | Retrieve the list of inventory items. |
| POST | `/items` | Create a new inventory item. |
| GET | `/items/{id}` | Retrieve a specific inventory item by ID. |

## Endpoint Details

### GET `/items`

Returns all inventory items. The API returns HTTP 200 when the request is successful.

**Request Example:**

```http
GET /api/items HTTP/1.1
Authorization: Bearer YOUR_TOKEN
```

**Response Example:**

```json
[
  {
    "id": 101,
    "name": "Wireless Mouse",
    "quantity": 24,
    "location": "A-01"
  }
]
```

---

### POST `/items`

Creates a new inventory item. The API expects a JSON body with `name`, `quantity`, and `location`. The API returns HTTP 201 when the item is created.

**Request Example:**

```json
{
  "name": "Mechanical Keyboard",
  "quantity": 10,
  "location": "B-02"
}
```

**Response Example:**

```json
{
  "id": 102,
  "name": "Mechanical Keyboard",
  "quantity": 10,
  "location": "B-02"
}
```

---

### GET `/items/{id}`

Returns one inventory item by ID.

**Request Example:**

```http
GET /api/items/101 HTTP/1.1
Authorization: Bearer YOUR_TOKEN
```

**Response Example:**

```json
{
  "id": 101,
  "name": "Wireless Mouse",
  "quantity": 24,
  "location": "A-01"
}