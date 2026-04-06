# LaunchPoint

A tool that scores any U.S. city for small business viability using GPT-4 analysis and local market data.

---

## Demo

> _Screenshot placeholder — add a screenshot of the home page and results page here._

---

## What It Does

You pick a city, a business category, and a subcategory. LaunchPoint sends that combination to GPT-4, which weighs four factors — local competition, nearby popular establishments, city demographics, and socio-economic conditions — and returns a score out of 100. Competition is weighted slightly heavier than the other factors.

The results page shows the overall score alongside a plain-English explanation for each factor. Each demographic explanation ends with the city's population, and each socio-economic explanation ends with the area's median household income. A Google Map centered on your chosen city is also shown alongside the results.

Supported business types:

- **Restaurant** with cuisine options: African, American, Chinese, Indian, Italian, Japanese, Korean, Mediterranean, Mexican, Middle Eastern, Thai
- **Boutique/Services** with options: Cafe/Bakery, Fashion/Apparel Retail, Grocery/Convenience, Health/Wellness

---

## Tech Stack

| Layer    | Technology                                                                  |
| -------- | --------------------------------------------------------------------------- |
| Frontend | React 18, React Router v6, React Bootstrap, Axios                           |
| Maps     | Google Maps JavaScript API (`@react-google-maps/api`), Google Geocoding API |
| Backend  | Node.js, Express                                                            |
| AI       | OpenAI API (GPT-4)                                                          |
| Styling  | CSS, Bootstrap 5                                                            |

---

## Running It Locally

### Prerequisites

- Node.js (v18 or later recommended)
- An OpenAI API key
- A Google Maps API key (with Maps JavaScript API, Geocoding API, and Places API enabled)

### 1. Clone the repo

```bash
git clone <your-repo-url>
cd LaunchPoint
```

### 2. Set up the backend

```bash
cd backend
npm install
```

Create a `.env` file in the `backend` folder:

```
OPENAI_API_KEY=your_key_here
```

Start the backend server:

```bash
npm run dev
```

The server runs on `http://localhost:3000`.

### 3. Set up the frontend

Open a new terminal tab:

```bash
cd frontend
npm install
```

Create a `.env` file in the `frontend` folder:

```
REACT_APP_GOOGLE_MAPS_API_KEY=your_key_here
```

Start the frontend:

```bash
npm start
```

The app opens at `http://localhost:3001` (or the next available port).

---

## Environment Variables

| Variable                        | Where           | Description                                           |
| ------------------------------- | --------------- | ----------------------------------------------------- |
| `OPENAI_API_KEY`                | `backend/.env`  | OpenAI API key used to call GPT-4                     |
| `REACT_APP_GOOGLE_MAPS_API_KEY` | `frontend/.env` | Google Maps API key for the map display and geocoding |

---

## Project Structure

```
LaunchPoint/
├── backend/
│   ├── script.js          # Express server; handles the /api/generate-business-score route and GPT-4 calls
│   ├── package.json
│   └── .env               # Not committed — holds OPENAI_API_KEY
│
└── frontend/
    ├── public/
    │   └── index.html
    └── src/
        ├── App.js                      # Root component; defines routes and the header
        ├── App.css                     # Global layout and background image styles
        ├── components/
        │   ├── SearchBar.js            # Home page form for location, business type, and subcategory
        │   ├── SearchBar.css
        │   ├── Rating.js               # Results page; fetches score, renders map and factor breakdown
        │   └── Rating.css
        └── assets/
            └── Attachment-1.jpeg       # Background image on the home page
```

---

## Built by

Viet Tran, Justin Hwang, Aneesh Sunkarapalli, Justin Seo
