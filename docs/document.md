---

title: Inventory API
sidebar_position: 1
---

# Inventory API

## Overview
Inventory API is a REST API used by an internal inventory application to retrieve, create, and view item data.

## Authentication
All endpoints require a Bearer Token in the HTTP Authorization header.

## Endpoint List
| Method | Path | Description |
| --- | --- | --- |
| GET |DEX /items | Retrieve the list of inventory items. |
| POST | /items | Create a new inventory item. |
| GET | /items/{id} | Retrieve a specific inventory item by ID. |

## Endpoint Details
### GET /items
Returns all inventory items. The API returns HTTP 200 when the request is successful.

```http
GET /api/items HTTP/1.1
Authorization: Bearer YOUR_TOKEN
[
  {
    "id": 101,
    "name": "Wireless Mouse",
    "quantity": 24,
    "location": "A-01"
  }
]
```

### POST /items
Creates a new inventory item. The API expects a JSON body with name, quantity, and location. The API returns HTTP 201 when the item is created.

```http
{
  "name": "Mechanical Keyboard",
  "quantity": 10,
  "location": "B-02"
 matra
}
```

### GET /items/{id}
Returns one inventory item by ID.

```http
GET /api/items/101 HTTP/1.1
Authorization: Bearer YOUR_TOKEN
{
  "id": 101,
  "name": "Wireless Mouse",
  "quantity": 24,
  "location": "A-01"
}
```