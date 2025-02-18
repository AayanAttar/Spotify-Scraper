# Spotify-Scraper

Spotify Playlist Scraper

Overview

This Python script uses Selenium and BeautifulSoup to scrape details of songs from a Spotify playlist. The extracted data is saved in an Excel file with hyperlinks for easy access.

Features

Automates browser interaction using Selenium WebDriver.

Scrolls down the playlist page to load 50 songs dynamically.

Extracts details such as:

Song Name

Song Link

Album Name & Link

Artist Name & Link

Image Link

Date Added

Duration

Saves the extracted data into an Excel file (xlsx) with:

Clickable hyperlinks for songs, albums, and artists.

Auto-adjusted column widths for better readability.

Prerequisites

1. Install Dependencies

Make sure you have the following Python libraries installed:

pip install selenium beautifulsoup4 pandas openpyxl

2. Set Up WebDriver

Download ChromeDriver (compatible with your Chrome version) from: https://chromedriver.chromium.org/downloads

Place it in your system's PATH or specify its location in the script.

How It Works

1. Initialize WebDriver & Open Playlist

The script initializes Selenium WebDriver with Chrome options.

It opens the Spotify playlist URL and waits for the content to load.

2. Scrolling Mechanism

The script scrolls PAGE DOWN until 50 songs are loaded.

It ensures no redundant scrolling if all songs are already loaded.

3. Extracting Song Details

Using BeautifulSoup, the script extracts the following details for each song:

Song Name & Link (by locating <a> tags inside tracklist rows)

Album Name & Link

Artist Name & Link

Song Image (Extracted from <img> tags)

Date Added (Extracted from <span> tags)

Duration (Extracted from <div> tags)

4. Saving Data to Excel

Data is written into an Excel file (spotify_playlist.xlsx) using pandas.

Hyperlinks are applied to song, album, and artist links.

Column widths are auto-adjusted for readability.

5. Opening the Excel File & Formatting

The script automatically opens the Excel file after saving.

Hyperlinks are formatted in blue with underlines.

Column widths are adjusted dynamically.

<!-- Output Example (Excel File)

Image Link

Song Name

Song Link

Album Name

Album Link

Artist Name

Artist Link

Date Added

Duration

🔗 (URL)

Song 1

🔗 (URL)

Album 1

🔗 (URL)

Artist 1

🔗 (URL)

2024-02-18

3:45

🔗 (URL)

Song 2

🔗 (URL)

Album 2

🔗 (URL)

Artist 2

🔗 (URL)

2024-02-18

4:12 -->

Customization

Modify Target Playlist:

Change the playlist URL in the script:

playlist_url = "https://open.spotify.com/playlist/37i9dQZF1DX0XUfTFmNBRM"

Adjust Song Limit:

Modify the target_song_count to extract more/less than 50 songs:

target_song_count = 100  # Extracts 100 songs instead of 50

Error Handling & Notes

Spotify's UI may change over time, breaking selectors. If this happens, update the CSS selectors in the script.

Ensure ChromeDriver is updated whenever Chrome updates to avoid compatibility issues.

Long playlists may require higher wait times for page loading.