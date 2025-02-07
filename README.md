# Data-Retrieval-Spotify
Python Programming - Spotify Data Retrieval (API)

# Spotify Data Retrieval Tools

A collection of Python scripts to interact with Spotify Web API for retrieving user library data and artist information. This repository provides easy-to-use tools for accessing various Spotify data endpoints.

## Features

### User Library Data Retrieval:
- Access saved albums
- View liked songs
- List user playlists

### Artist Data Retrieval:
- Search for artists
- Get artist's top tracks
- Access artist's albums
- View album tracks
- Retrieve detailed artist information

## Prerequisites
- Python 3.6 or higher
- Spotify Developer account
- Spotify API credentials (Client ID and Client Secret)

## Setup and Installation

Clone the repository:
```sh
git clone https://github.com/nurulashraf/spotify-data-retrieval.git
cd spotify-data-retrieval
```

Install required packages:
```sh
pip install -r requirements.txt
```

Create a Spotify Developer account and register your application at [Spotify Developer Dashboard](https://developer.spotify.com/dashboard/).

## Usage

### Configuration
In the Spotify Developer Dashboard:
1. Create a new application
2. Get your Client ID and Client Secret
3. Set up your Redirect URI
4. Add the URI to your application settings

Update the credentials in the scripts:
- Open `src/spotify_user_data_retrieval.ipynb`
- Replace the placeholder values with your credentials:
  ```python
  client_id = 'your_client_id'
  client_secret = 'your_client_secret'
  redirect_uri = 'your_redirect_uri'
  ```
- Do the same for `src/spotify_artist_data_retrieval.ipynb`

### Running the Scripts

#### For User Data Retrieval:
1. Open `src/spotify_user_data_retrieval.ipynb` in Jupyter Notebook or Google Colab.
2. Run the first cell with authentication code.
3. A Spotify authorization page will open in your browser.
4. Authorize the application.
5. You will be redirected to your redirect URI.
6. In the URL of the redirect page, look for the `code` parameter after `?code=`.
7. Copy the `code` value (everything after `?code=` and before any `&` if present).
8. In the second cell of the notebook, replace the placeholder:
   ```python
   auth_code = 'your_authorization_code'  # Replace with the code from the URL
   ```
9. Run the remaining cells to fetch user data.

#### For Artist Data Retrieval:
1. Open `src/spotify_artist_data_retrieval.ipynb`
2. In the second cell, locate the search query variable:
   ```python
   search_query = 'desired_artist_name'  # Replace with desired artist name
   ```
3. Replace the placeholder with your desired artist name (e.g., 'Taylor Swift', 'The Beatles').
4. The script will return:
   - List of matching artists (top 5 results)
   - Detailed information about the top match
   - Top tracks from the artist
   - Recent albums
   - Tracks from their most recent album
5. Run all cells to get the complete artist information.

## Scopes Used
The following Spotify API scopes are used in this project:
- `user-library-read`: Access user's saved albums and tracks
- `user-top-read`: Access user's top artists and tracks
- `user-read-playback-state`: Read user's playback state

## Limitations
- Access token expires after a short period
- Requires manual token refresh

## Contributing
Contributions, issues, and feature requests are welcome!

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
