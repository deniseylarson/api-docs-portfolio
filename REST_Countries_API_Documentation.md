# 🌍 REST Countries API Documentation

## Overview
This sample documentation demonstrates how I would approach documenting a public REST API for developers. I selected the REST Countries API because it provides clean, structured JSON responses and supports practical scenarios involving international data.

The REST Countries API allows users to retrieve country-specific details such as population, currencies, languages, regions, and borders. In a real-world context, this kind of API could be used in dashboards, data visualization tools, or apps requiring geographic insights. This documentation is designed to help developers understand available endpoints, make and test requests, interpret responses, and troubleshoot issues.

---

## Base URL
```
https://restcountries.com/v3.1/
```

---

## Authentication
No API key or authentication is required to access this API.

---

## Quick Start Example

**Retrieve country details using Postman:**

1. Set the request type to `GET`
2. Use the following URL:
   ```
   https://restcountries.com/v3.1/name/canada
   ```
3. Click **Send** to view country information

---

## Endpoints

### `GET /all`
Returns data for all countries.

**Request:**
```
GET https://restcountries.com/v3.1/all
```

**Response Example Snippet:**
```json
[
  {
    "name": {
      "common": "Canada",
      "official": "Canada"
    },
    "capital": ["Ottawa"],
    "region": "Americas",
    "population": 38005238
  }
]
```

---

### `GET /name/{name}`
Search by full or partial country name.

**Request:**
```
GET https://restcountries.com/v3.1/name/germany
```

**Query Parameters:**
- `fullText=true` (optional): Match the exact name

**Response Example:**
```json
[
   {
    "name": {
      "common": "Germany",
      "official": "Federal Republic of Germany"
    },
    "capital": ["Berlin"],
    "region": "Europe",
    "currencies": {
      "EUR": {
        "name": "Euro",
        "symbol": "€"
      }
    }
  }
]
```

---

### `GET /region/{region}`
Returns all countries in a given region.

**Regions Available:**
- Africa
- Americas
- Asia
- Europe
- Oceania

**Request:**
```
GET https://restcountries.com/v3.1/region/asia
```

---

### `GET /alpha/{code}`
Search for a country using its 2-letter or 3-letter ISO code.

**Request:**
```
GET https://restcountries.com/v3.1/alpha/ca
```

---

## Status Codes

| Code | Meaning              |
|------|----------------------|
| 200  | Success              |
| 404  | Country not found    |
| 400  | Bad request format   |
| 500  | Server error         |

---

## Common Use Cases
- Displaying country information in a dropdown menu
- Creating a world population heat map
- Supporting international shipping rules
- Adding multi-language and currency support

---

## Troubleshooting Tips
- If a request returns `404`, double-check your spelling or use the `/all` endpoint to confirm the country exists.
- API may rate-limit requests if hit too frequently. Consider caching results locally.
- JSON keys may change slightly between versions; validate response structure before parsing.

---

## Appendix: Tools Used
- Formatted and previewed Markdown using **StackEdit**
- Tested API endpoints using **Postman**
- Validated JSON responses with **jsonlint.com**
- Published content via **GitHub Pages**
