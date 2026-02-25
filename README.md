# Google Play Product Scraper

[<img width="950" height="300" alt="Google Play Store App product scraper" src="https://github.com/user-attachments/assets/24a29469-0988-48cf-881b-28ff2ec2ae2e" />](https://serpapi.com/google-play-api?utm_source=github_google_play_scraper)

Google Play Product Scraper - A tool to scrape detailed product information from the Google Play Store with a simple API. Get app details like description, rating, reviews, developer contact, media assets, and more.

We provide the results in a structured JSON format, eliminating the need for parsing, coding, proxies, or any other web scraping headaches for developers.

## How to scrape Google Play Product details?

Using a simple GET request, you can retrieve Google Play product information:

```
https://serpapi.com/search.json?engine=google_play_product&product_id=com.google.android.apps.maps&store=apps&api_key=YOUR_API_KEY
```

- Register for free at [SerpApi to get your API Key](https://serpapi.com?utm_source=github_google_play_product_scraper)
- `product_id` parameter: defines the product ID to look up on Google Play.
- `store` parameter: defines the type of Google Play store (e.g., `apps`, `movies`, `books`).

## Code examples
Here are some code examples based on your favorite programming languages.

### cURL Integration

``` bash
curl --get https://serpapi.com/search \
 -d engine="google_play_product" \
 -d product_id="com.google.android.apps.maps" \
 -d store="apps" \
 -d api_key="secret_api_key"
```

### Python Integration

Step 1:
Create a new `main.py` file.

Step 2:
Install [requests package](https://pypi.org/project/requests/) with:
```
pip install requests
```

Step 3:
Add this code to your file:
``` py
import requests
SERPAPI_API_KEY = "YOUR_SERPAPI_API_KEY"

params = {
    "api_key": SERPAPI_API_KEY,
    "engine": "google_play_product",
    "product_id": "com.google.android.apps.maps",
    "store": "apps"
}

search = requests.get("https://serpapi.com/search", params=params)
response = search.json()
print(response)
```

If you're only interested in the `product_info`, you can print it from the response directly:

``` py
print(response["product_info"])
```

### JavaScript Integration

Step 1:
Install the [SerpApi JavaScript package](https://github.com/serpapi/serpapi-javascript):
```
npm install serpapi
```

Step 2:
Create a new `index.js` file.

Step 3:
Add this to your file:
``` js
const { getJson } = require("serpapi");
getJson({
  api_key: API_KEY,
  engine: "google_play_product",
  product_id: "com.google.android.apps.maps",
  store: "apps"
}, (json) => {
  console.log(json["product_info"]);
});
```

### Other Programming Languages
While you can use our APIs using a simple GET request with any programming language, you can also see our ready-to-use libraries here: [SerpApi Integrations](https://serpapi.com/integrations?utm_source=github_google_play_product_scraper).

## Google Play Product Scraper Parameters
Please find the parameters for the Google Play Product API below:

| Name               | Description                                                                                                  | Requirement |
|--------------------|--------------------------------------------------------------------------------------------------------------|-------------|
| product_id         | Parameter defines the product ID to look up                                                                  | Required    |
| store              | Parameter defines the store type: `apps`, `movies`, `tv`, `books`, or `audiobooks`                          | Required    |
| **Localization**   |                                                                                                              |             |
| gl                 | Parameter defines the two-letter country code (default: `us`)                                                | Optional    |
| hl                 | Parameter defines the two-letter language code (default: `en`)                                               | Optional    |
| **TV Store**       |                                                                                                              |             |
| season_id          | Parameter defines the ID for a specific TV season                                                            | Optional    |
| **Reviews**        |                                                                                                              |             |
| all_reviews        | Parameter to retrieve all product reviews: `true` or `false` (default)                                      | Optional    |
| platform           | Parameter to filter reviews by device: `phone` (default), `tablet`, `watch`, `chromebook`, or `tv`          | Optional    |
| rating             | Parameter to filter reviews by star rating (1-5)                                                             | Optional    |
| sort_by            | Parameter to sort reviews: `1` (most relevant), `2` (newest), `3` (rating)                                  | Optional    |
| num                | Parameter defines the maximum number of reviews per request (up to 199)                                     | Optional    |
| next_page_token    | Parameter to retrieve subsequent page results                                                                | Optional    |

Visit [our documentation](https://serpapi.com/google-play-product-api) for more information on all available parameters.


## Available data on Google Play Product (JSON Response)
Google Play Product API can return different information from time to time. Here is what the response may contain:

### Product Info
``` json
"product_info": {
  "title": "String - Title of the app",
  "authors": "Array - Developer/publisher information",
  "rating": "Float - App rating (out of 5)",
  "reviews": "Integer - Total number of reviews",
  "downloads": "String - Number of downloads",
  "thumbnail": "String - URL to the app icon",
  "content_rating": "String - Content/age rating",
  "last_updated": "String - Date of last update",
  "media": "video or images of the product"
}
```

### Reviews
``` json
"reviews": [
  {
    "id": "String - Unique review identifier",
    "title": "String - Reviewer name",
    "avatar": "String - Profile image URL",
    "rating": "Integer - Star rating (1-5)",
    "snippet": "String - Review text content",
    "likes": "Integer - Number of likes",
    "date": "String - Human-readable date",
    "iso_date": "String - ISO 8601 timestamp"
  }
]
```

The API response also includes:
- `media`: Screenshots and video previews
- `about_this_app`: Detailed app description and metadata
- `ratings`: Rating distribution breakdown
- `developer_contact`: Developer website, email, and address
- `similar_results`: Related apps

## Tutorial
- [Video on scraping Google Play Store App Reviews](https://www.youtube.com/watch?v=V-uc-Fi9SpI)
- [Blog - Scrape All Google Play App Reviews in Python](https://serpapi.com/blog/scrape-all-google-play-app-reviews-in-python/)

## Use cases
Here are some use cases for the Google Play Product API:

- Monitor app details such as ratings, reviews, and download counts over time.
- Analyze user feedback by scraping reviews filtered by rating or device platform.
- Track app updates and version changes for competitive intelligence.
- Build app comparison tools using detailed product metadata.
- Aggregate developer contact information for outreach and partnerships.
- Research content ratings and app requirements across different markets.

## Related scraper
- [Google Play Store Scraper](https://github.com/serpapi/google-play-scraper/)

## Contacts
Feel free to reach out via `contact@serpapi.com`.

Check other [Google Scrapers](https://github.com/serpapi/google-scraper) from SerpApi.
