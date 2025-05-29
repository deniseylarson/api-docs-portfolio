# 🌍 REST Countries API Documentation

## Overview
This documentation provides a sample guide for using the REST Countries API. It is intended to demonstrate technical writing skills in documenting unauthenticated API endpoints, request parameters, response formats, and common use cases.

The REST Countries API allows developers to programmatically retrieve country-specific data such as population, currencies, languages, regions, and borders. It is commonly used in applications that involve international data, data visualization, or geographic insights.

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
Use `curl` or Postman to test a simple request:

```bash
curl https://restcountries.com/v3.1/name/canada
```

---

## Endpoints

### `GET /all`
Returns data for all countries.

**Request:**
```
GET https://restcountries.com/v3.1/all
```

**Sample Response Snippet:**
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

**Sample Response:**
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
- API may rate-limit requests if hit too frequently — consider caching results locally.
- JSON keys may change slightly between versions; validate response structure before parsing.

---

## Appendix: Tools Used
- Formatted and previewed Markdown using **StackEdit**
- Tested API endpoints using **Postman**
- Validated JSON responses with **jsonlint.com**
- Published content via **GitHub Pages**
