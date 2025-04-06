# GitHub Trending Scraper API

A Node.js backend service that scrapes GitHub's trending developers and repositories pages to provide data in JSON format.

## Features

- Fetch trending GitHub developers
- Fetch trending GitHub repositories
- Filter results by time period (daily/weekly/monthly)
- CORS enabled for frontend integration

## Tech Stack

- Node.js
- Express.js
- Axios
- Cheerio (for web scraping)
- Dotenv (for environment variables)
- CORS

## Installation

1. Clone the repository
2. Install dependencies:
```bash
npm install
```
3. Create a `.env` file in the root directory and add:
```
PORT=8080
```

## Running the Application

Development mode with auto-reload:
```bash
npm run dev
```

Production mode:
```bash
npm start
```

## API Endpoints

### Get Trending Developers

```
GET /scrape/github-developers?date=[daily|weekly|monthly]
```

Parameters:
- `date` (optional): Time period for trending developers. Default is "daily"

Response format:
```json
[
  {
    "name": "Developer Name",
    "username": "github_username",
    "avatar": "avatar_url",
    "repo": "repository_name",
    "repo_url": "repository_url",
    "description": "repository_description"
  }
]
```

### Get Trending Repositories

```
GET /scrape/github-repositories?date=[daily|weekly|monthly]
```

Parameters:
- `date` (optional): Time period for trending repositories. Default is "daily"

Response format:
```json
[
  {
    "title": "repository_name",
    "repo_url": "repository_url",
    "description": "repository_description",
    "language": "programming_language",
    "stars": "total_stars",
    "forks": "total_forks",
    "todayStars": "stars_today"
  }
]
```

## Error Handling

The API returns:
- `200 OK` for successful requests
- `500 Internal Server Error` for failed scraping attempts
