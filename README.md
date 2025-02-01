# 🎬 LikhonFlix API

A powerful API service that provides streaming links for movies and series using IMDB IDs. Supporting multiple languages including Hindi, English, Tamil, Telugu, and Bengali.

## 🚀 Features

- Get media information and streaming links
- Multi-language support
- Season and episode details for TV series
- Easy-to-use REST API endpoints
- Docker support
- Free and open source

## 📚 API Documentation

### 1. Get Media Info
Retrieve information and keys required for streaming.

**Endpoint:**
```
GET https://likhonflixapi.vercel.app/api/v1/mediaInfo?id=tt1877830
```

**Parameters:**

| Parameter | Description | Required | Method |
|-----------|-------------|----------|---------|
| id        | IMDB ID of movie/series | Yes | GET |

**Example Response:**
```json
{
    "success": true,
    "data": {
        "playlist": [
            {
                "title": "Hindi",
                "id": "24b8c045e7fcd28fb2ee654de75a5771",
                "file": "~0ALZ3tMP71lNTMdSBfbldjRRj..."
            },
            {
                "title": "English",
                "id": "fd93fd0a7fc57f1e0c9c54110322a05f",
                "file": "~GTE1z8T8rAcuWI3QaGEKR0oNFl..."
            }
            // Additional languages...
        ],
        "key": "yZBAPr58y7RIOpj4K$VhgXhXBTHz..."
    }
}
```

### 2. Get Season List
Retrieve available seasons, episodes, and language information for TV series.

**Endpoint:**
```
GET https://likhonflixapi.vercel.app/api/v1/getSeasonList?id=tt11737520
```

**Parameters:**

| Parameter | Description | Required |
|-----------|-------------|-----------|
| id        | IMDB ID of series | Yes |

**Example Response:**
```json
{
    "success": true,
    "data": {
        "seasons": [
            {
                "season": "Season 1",
                "totalEpisodes": 8,
                "lang": ["Hindi", "English"]
            }
        ],
        "type": "tv"
    }
}
```

### 3. Get Stream
Get the actual streaming link for content.

**Endpoint:**
```
POST https://likhonflixapi.vercel.app/api/v1/getStream
```

**Required Body Parameters:**

| Parameter | Description | Required |
|-----------|-------------|-----------|
| file      | File value from mediaInfo | Yes |
| key       | Key value from mediaInfo | Yes |

**Example Usage:**
```javascript
fetch('https://likhonflixapi.vercel.app/api/v1/getStream', {
    method: 'POST',
    headers: {
        'Content-Type': 'application/json'
    },
    body: JSON.stringify({
        file: '~8i-Mu-WONoEdJ9whQe+Ldow...',
        key: 'rcbeUV3KoCw-dSFJ-vN$-JwI4OXlCmOaAx05HkWyclbx46SNcazmpYmnFTXoNjo'
    })
})
.then(response => response.json())
.then(data => console.log(data))
.catch(error => console.error(error));
```

## 🛠️ Installation

### Local Setup

1. Clone the repository:
```bash
git clone https://github.com/likhonsheikhcodes/likhonflixapi.git
cd likhonflixapi
```

2. Using Node.js:
```bash
npm install
npm run build
npm run start
```

3. Using Docker:
```bash
docker build -t likhonflixapi .
docker run -p 3000:3000 -it -d likhonflixapi
```

## 🚀 Deploy

### Deploy to Vercel
[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/likhonsheikhcodes/likhonflixapi)

> Note: Vercel free tier has a 10-second serverless response time limit

### Deploy to Render
[![Deploy to Render](https://render.com/images/deploy-to-render-button.svg)](https://render.com/deploy?repo=https://github.com/likhonsheikhcodes/likhonflixapi)

## 📝 License

This project is open source and available under the [MIT License](LICENSE).

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to check the [issues page](https://github.com/likhonsheikhcodes/likhonflixapi/issues).

## ⭐ Show your support

Give a ⭐️ if this project helped you!
