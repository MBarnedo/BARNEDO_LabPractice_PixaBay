# Pixabay API Lab Practice

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

<img width="1917" height="618" alt="image" src="https://github.com/user-attachments/assets/0797d43f-e0a0-45e0-bd17-482f92d68c6d" />


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

<img width="1917" height="396" alt="image" src="https://github.com/user-attachments/assets/0633cffb-3e5d-4fb7-9838-9273f5cf4c97" />


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
<img width="1917" height="488" alt="image" src="https://github.com/user-attachments/assets/64e1ccc8-23e9-45fb-8b41-ff02f5ab7566" />

### CURL command

```bash
curl "https://pixabay.com/api/videos/?key=YOUR_API_KEY&q=Forest&category=backgrounds&editors_choice=true&order=latest&per_page=3"
```

### Response

*(Insert screenshot of the terminal/browser JSON output here — remember to blur your key.)*

`![Challenge 3 response](images/road.png)`

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

*(Insert screenshot of the terminal/browser JSON output here — remember to blur your key.)*

<img width="1917" height="365" alt="image" src="https://github.com/user-attachments/assets/48da86c1-9ee1-4f78-b61c-145ef13c63d2" />

---

