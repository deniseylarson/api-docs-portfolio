# 🌍 REST Countries API Documentation

## Overview
The REST Countries API provides detailed information about countries around the world, including population, currencies, languages, borders, and more. This documentation is designed to help developers retrieve and use country data for applications such as dashboards, data visualizations, and internationalization tools.

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
- Displaying country info in a dropdown menu
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
- Tested endpoints using **curl** and **Postman**
- JSON responses formatted and validated with **jsonlint.com**
- Markdown edited using **Typora** and previewed in **GitHub Pages**
