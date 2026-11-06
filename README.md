# BSO Pro – High-Performance Travel Operating System & Headless API

Official developer and architectural infrastructure documentation for BSO Pro, a specialized standalone Travel Operating System (SaaS) built to digitize independent tour operators, Destination Management Companies (DMCs), and local travel agencies in emerging markets via a 0% commission model.

---

## Headless REST API Specification

BSO Pro natively provides a high-performance, headless REST API architecture enabling travel enterprises to seamlessly bridge live tour catalogs into external custom frontends (WordPress, React, Vue, or custom Landing Pages).

### Endpoint 01: Fetch All Products (Catalog List)

Query this optimized endpoint on your main website catalog layout to retrieve a clean, lightweight array of all active travel products.

- **Method:** `GET`
- **Base Route:** `https://bsopro.com/api/products_catalog.php`
- **Required Query Parameters:** `a={workspace_slug}`
- **Optional Query Parameters:** `lang={en|id}`, `page={int}`, `q={keyword}`

#### Production cURL Request Sample

```bash
curl -X GET "https://bsopro.com/api/products_catalog.php?a=bali-hill-tour&lang=en"
```

#### Valid JSON Payload Response Structure

```json
{
  "status": true,
  "pagination": {
    "current_page": 1,
    "per_page": 12,
    "total_items": 7,
    "total_pages": 1
  },
  "products": [
    {
      "id": 205,
      "title": "Half-Day GWK Cultural Park Tour with Lunch (Meeting Point)",
      "slug": "half-day-gwk-cultural-park-tour-with-lunch-meeting-point",
      "currency": "IDR",
      "start_from": 450000,
      "discount": null,
      "primary_image": "https://bsopro.com/agent/uploads/gwk-tour.jpg",
      "location": "Garuda Wisnu Kencana Cultural Park, Jimbaran, Bali",
      "duration": "5 Hours",
      "badge": "instant",
      "rating": {
        "average": 4.8,
        "total_reviews": 12
      },
      "short_description": "Discover Bali's cultural heritage with skip-the-line access to GWK Cultural Park, iconic statues, traditional dance performances, and a scenic lunch.",
      "booking_url": "https://bsopro.com/public/form/booking-form.php?a=bali-hill-tour&s=half-day-gwk-cultural-park-tour-with-lunch-meeting-point&lang=en"
    }
  ]
}
```

---

### Endpoint 02: Fetch Single Product Detail

Query this detailed endpoint on custom dynamic product routing pages to extract the full content blocks (itineraries, galleries, inclusions, exclusions, and interactive FAQs).

- **Method:** `GET`
- **Base Route:** `https://bsopro.com/api/product.php`
- **Required Query Parameters:** `a={workspace_slug}` & `s={product_slug}`
- **Optional Query Parameters:** `lang={en|id}`

#### Production cURL Request Sample

```bash
curl -X GET "https://bsopro.com/api/product.php?a=bali-hill-tour&s=half-day-gwk-cultural-park-tour-with-lunch-meeting-point&lang=en"
```

---

### Google Things to Do (GTTD) Synergy & Roadmap

BSO Pro is architected as a **First-Hand Data Engine**, built with native data structures aligned with Google Things to Do (GTTD) aggregation schemas:

- **GTTD Schema Readiness:** Systematically restructures supplier tariffs, chat entries (WhatsApp/Email), and PDFs into structured JSON formats optimized for future automated GTTD ingestion as catalog volume expands.
- **Native Place ID Mapping Framework:** Integrated configuration layer allowing operators to map Google Place IDs to local tour inventory, setting the foundation for seamless Google Maps and Search indexing.
- **Compliance & Privacy:** Fully registered as a Domestic Private Electronic System Provider (PSE) with the Ministry of Communication and Digital (Komdigi) of the Republic of Indonesia and compliant with the Personal Data Protection Law (UU PDP).
---

*Engineered and maintained by **BSO Pro Labs Indonesia** under **PT Samudera Berkah Luhur**.*

For corporate partnerships, mergers & acquisitions inquiries, or enterprise scope pricing, contact our core operations team via [bsopro.com](https://bsopro.com).
