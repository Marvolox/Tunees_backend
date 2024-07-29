# Tunees_backend

## Overview

This repository contains the backend for the Music Player Application. It provides API endpoints to manage the playlist, handle song playback, and serve metadata for songs. The backend is built using Node.js and Express, ensuring a scalable and efficient server to support the music player functionality.

## Features

- RESTful API to manage the playlist (CRUD operations).
- Endpoints to fetch song details and metadata.
- Endpoint to handle song playback.
- Middleware for error handling and request logging.

## Getting Started

### Prerequisites

- Node.js (version 14 or higher)
- npm (version 6 or higher)
- MongoDB (for storing playlist data)

### Installation

1. **Clone the repository:**


2. **Install the dependencies:**

    ```bash
    npm install
    ```

3. **Set up environment variables:**

    Create a `.env` file in the root directory and add the following variables:

    ```env
    PORT=5000
    MONGODB_URI=mongodb://localhost:27017/music-player
    ```

4. **Start the server:**

    ```bash
    npm start
    ```

5. The server should now be running at `http://localhost:5000`.

## API Endpoints

### Playlist

- **GET /api/playlist**: Fetch all songs in the playlist.
- **POST /api/playlist**: Add a new song to the playlist.
- **GET /api/playlist/:id**: Fetch details of a specific song.
- **PUT /api/playlist/:id**: Update a song in the playlist.
- **DELETE /api/playlist/:id**: Remove a song from the playlist.

### Song Playback

- **GET /api/play/:id**: Handle song playback by fetching the song file.

### Example API Requests

#### Fetch All Songs

```bash
GET /api/playlist
```

#### Add a New Song

```bash
POST /api/playlist
Content-Type: application/json

{
    "title": "Song Title",
    "artist": "Artist Name",
    "album": "Album Name",
    "duration": 180,
    "fileUrl": "http://example.com/song.mp3"
}
```

#### Fetch Song Details

```bash
GET /api/playlist/:id
```

#### Update a Song

```bash
PUT /api/playlist/:id
Content-Type: application/json

{
    "title": "Updated Song Title",
    "artist": "Updated Artist Name",
    "album": "Updated Album Name",
    "duration": 200,
    "fileUrl": "http://example.com/updated-song.mp3"
}
```

#### Delete a Song

```bash
DELETE /api/playlist/:id
```

## Project Structure

```
music-player-backend/
├── controllers/
│   ├── playlistController.js
│   └── playbackController.js
├── models/
│   └── song.js
├── routes/
│   ├── playlist.js
│   └── playback.js
├── middleware/
│   ├── errorHandler.js
│   └── logger.js
├── .env
├── app.js
├── server.js
├── package.json
└── README.md
```

## Development

### Running Locally

To run the server locally, use:

```bash
npm run dev
```

This will start the server using `nodemon` for automatic restarts on code changes.

### Linting

To check the code for linting errors, use:

```bash
npm run lint
```

## Contributing

1. Fork the repository.
2. Create your feature branch (`git checkout -b feature/YourFeature`).
3. Commit your changes (`git commit -m 'Add some feature'`).
4. Push to the branch (`git push origin feature/YourFeature`).
5. Open a pull request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgements

- This project uses [Express](https://expressjs.com/) for server-side operations.
- MongoDB is used for data storage.
