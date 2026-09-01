# Pixabay API Lab Practice

This repository documents four search requests made against the [Pixabay API](https://pixabay.com/api/docs/) using CURL, as part of the ITCC lab activity. Each challenge below shows the exact request that was sent and the JSON response that came back.

> **Note on the API key:** every screenshot and code block in this README uses `YOUR_API_KEY` as a stand-in. My real key is never committed to this repo or shown in any image, per the lab instructions.

---

## How requests are built

Pixabay exposes two separate endpoints:

- `https://pixabay.com/api/` — for **images**
- `https://pixabay.com/api/videos/` — for **videos**

Every request needs your personal `key`. Everything else is a **query parameter** — a `name=value` pair appended after the `?`, with additional pairs joined by `&`. The **request URL** is simply the base endpoint plus all of those query parameters strung together.

---

## Challenge 1: Rocket Launch (Video)

**Goal:** search Pixabay's video library for "Rocket Launch" videos in the Science category that are Editor's Choice, limited to 3 results.

### Request URL

```
https://pixabay.com/api/videos/?key=YOUR_API_KEY&q=Rocket+Launch&category=science&editors_choice=true&per_page=3
```

### CURL command

```bash
curl "https://pixabay.com/api/videos/?key=YOUR_API_KEY&q=Rocket+Launch&category=science&editors_choice=true&per_page=3"
```

| Parameter | Value | Purpose |
|---|---|---|
| `q` | `Rocket Launch` | search term |
| `category` | `science` | restricts results to the Science category |
| `editors_choice` | `true` | only Editor's Choice videos |
| `per_page` | `3` | limits results to 3 hits |

### Response

*(Insert screenshot of the terminal/browser JSON output here — remember to blur your key.)*

`![Challenge 1 response](images/challenge1-response.png)`

---

## Challenge 2: Basketball (Video)

**Goal:** search for "Basketball" videos in the Sports category, sorted by newest upload, limited to 3 results.

### Request URL

```
https://pixabay.com/api/videos/?key=YOUR_API_KEY&q=Basketball&category=sports&order=latest&per_page=3
```

### CURL command

```bash
curl "https://pixabay.com/api/videos/?key=YOUR_API_KEY&q=Basketball&category=sports&order=latest&per_page=3"
```

| Parameter | Value | Purpose |
|---|---|---|
| `q` | `Basketball` | search term |
| `category` | `sports` | restricts results to the Sports category |
| `order` | `latest` | sorts by most recently uploaded instead of most popular |
| `per_page` | `3` | limits results to 3 hits |

### Response

*(Insert screenshot of the terminal/browser JSON output here — remember to blur your key.)*

`![Challenge 2 response](images/challenge2-response.png)`

---

## Challenge 3: Forest (Video)

This challenge asks for the **individual query parameters** rather than one finished URL, to show each piece of the request on its own.

### Query parameters

| Parameter | Value |
|---|---|
| `key` | `YOUR_API_KEY` |
| `q` | `Forest` |
| `category` | `backgrounds` |
| `editors_choice` | `true` |
| `order` | `latest` |
| `per_page` | `3` |

Combined, these parameters form the same kind of endpoint used in Challenges 1 and 2 (`https://pixabay.com/api/videos/`), just assembled piece by piece:

```
https://pixabay.com/api/videos/?key=YOUR_API_KEY&q=Forest&category=backgrounds&editors_choice=true&order=latest&per_page=3
```

### CURL command

```bash
curl "https://pixabay.com/api/videos/?key=YOUR_API_KEY&q=Forest&category=backgrounds&editors_choice=true&order=latest&per_page=3"
```

### Response

*(Insert screenshot of the terminal/browser JSON output here — remember to blur your key.)*

`![Challenge 3 response](images/challenge3-response.png)`

---

## Challenge 4: Road Forest (Photo)

**Goal:** search Pixabay's **image** library (not video) for "Road Forest" photos in the Nature category that are Editor's Choice, limited to 3 results.

### Request URL

```
https://pixabay.com/api/?key=YOUR_API_KEY&q=Road+Forest&image_type=photo&category=nature&editors_choice=true&per_page=3
```

### CURL command

```bash
curl "https://pixabay.com/api/?key=YOUR_API_KEY&q=Road+Forest&image_type=photo&category=nature&editors_choice=true&per_page=3"
```

| Parameter | Value | Purpose |
|---|---|---|
| `q` | `Road Forest` | search term |
| `image_type` | `photo` | restricts results to photographs (excludes illustrations/vectors) |
| `category` | `nature` | restricts results to the Nature category |
| `editors_choice` | `true` | only Editor's Choice images |
| `per_page` | `3` | limits results to 3 hits |

### Response (first 30 lines)

*(JSON responses can run long — paste only the top 30 lines, or screenshot just the top portion.)*

```json
// paste the first 30 lines of the JSON response here
```

---

## Notes / Observations

- The **image** endpoint (`/api/`) and the **video** endpoint (`/api/videos/`) are separate — using the wrong one for a given challenge returns the wrong content type entirely.
- `editors_choice` and other booleans are passed as the strings `true`/`false` in the query string.
- `category` values must match Pixabay's fixed list (e.g. `backgrounds`, not `background`) or the parameter is silently ignored.
- Every response includes `total`, `totalHits`, and a `hits` array — `hits` is where the actual video/image objects live.
