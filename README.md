<h3 align="center">
    <img src="https://i.ibb.co/CWY693F/beatprints-logo.png" width="175"/>
</h3>
<h3 align="center">
    BeatPrints: Quick, stylish posters for your favorite tracks! 🎷☕️
</h3>

<p align="center">Create eye-catching, Pinterest-style music posters effortlessly. BeatPrints integrates with <b>Spotify</b> and <b>LRClib API</b> to help you design custom posters for your favorite tracks or albums. 🍀</p>

<p align="center">
  <a href="https://gitHub.com/TrueMyst/BeatPrints/graphs/commit-activity">
    <img src="https://img.shields.io/badge/Maintained%3F-Yes-%23c4b9a6?style=for-the-badge&logo=Undertale&logoColor=%23b5a790&labelColor=%23312123" alt="Maintenance"></a>
  <a href="https://github.com/TrueMyst/BeatPrints/stargazers">
    <img alt="GitHub Repo stars" src="https://img.shields.io/github/stars/TrueMyst/BeatPrints?style=for-the-badge&logo=Apache%20Spark&logoColor=%23b5a790&labelColor=%23312123&color=%23c4b9a6"></a>
  <a href="https://github.com/psf/black">
    <img src="https://img.shields.io/badge/Code_Style-black-%23c4b9a6?style=for-the-badge&logo=CodeFactor&logoColor=%23b5a790&labelColor=%23312123" alt="Code Formatter"></a>
  <a href="https://creativecommons.org/licenses/by-nc-sa/4.0/">
    <img alt="Static Badge" src="https://img.shields.io/badge/License-CC_BY--NC--SA_4.0-%23c4b9a6?style=for-the-badge&logo=Pinboard&logoColor=%23b5a790&labelColor=%23312123"></a>
</p>

![examples](https://i.ibb.co.com/y0jKqHK/banner.png)

<h3 align="center">📔 Check out the new documentation <a href="https://beatprints.readthedocs.io/en/latest/">here!</a></h3>

## 📦 Installation

You can install BeatPrints via `pip`:

```bash
pip install BeatPrints
```

Or, if you use Poetry:

```bash
poetry add BeatPrints
```

## 🌱 Environment Variables

To get started with BeatPrints, you’ll need a `.env` file with these keys:

```env
SPOTIFY_CLIENT_ID = "<your-client-id>"
SPOTIFY_CLIENT_SECRET = "<your-client-secret>"
```

You can get these from the [Spotify Developer Dashboard](https://developer.spotify.com/dashboard/) by creating a new app with **Web API** as the scope.


## 🚀 Quick Start

Here’s how you can create your first poster:

```python
import os, dotenv
from BeatPrints import lyrics, poster, spotify

dotenv.load_dotenv()

# Spotify credentials
CLIENT_ID = os.getenv("SPOTIFY_CLIENT_ID")
CLIENT_SECRET = os.getenv("SPOTIFY_CLIENT_SECRET")

# Initialize components
ly = lyrics.Lyrics()
ps = poster.Poster("./")
sp = spotify.Spotify(CLIENT_ID, CLIENT_SECRET)

# Search for a track
search = sp.get_track("Saturn SZA", limit=1)

# Get the track's metadata and lyrics
metadata = search[0]
lyrics = ly.get_lyrics(metadata)
highlighted_lyrics = ly.select_lines(lyrics, "5-9")

# Generate the track poster
ps.track(metadata, highlighted_lyrics)
```

## 🥞 CLI Setup

To get started with the BeatPrints CLI, you'll need to set up a configuration file.

### Windows

1. Create a folder named `BeatPrints` in the following directory:

```python
C:\Users\<YourUsername>\AppData\Roaming\BeatPrints\
```

2. Inside this folder, create a file called `config.toml` with the following contents:

```toml
[general]
search_limit = 7
output_directory = "<path-to-save-your-posters>" 

[credentials]
client_id = "your-client-id"
client_secret = "your-client-secret"
```

Replace `<path-to-save-your-posters>` with the path where you'd like to save the generated posters, and fill in the `client_id` and `client_secret` with your Spotify credentials.

### Linux or macOS

1. Create a folder named `BeatPrints` in your `~/.config/` directory:

```python
~/.config/BeatPrints/
```

3. Inside this folder, create a file called `config.toml` with the same contents as mentioned above.

### Running the CLI

Once the config file is set up, you can run the BeatPrints CLI:

1. Open your terminal.
2. Type `beatprints` and press Enter.

Your poster will be saved in the output directory you specified in the `config.toml` file.

## 🖼️ Examples

Here are a few posters created with BeatPrints:

| **Track: Saturn by SZA**                                             | **Album: Charm by Clairo**                                             |
| -------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| ![Track Example](https://i.ibb.co.com/q5v8J9R/saturn-by-sza-1e3.png) | ![Album Example](https://i.ibb.co.com/TcrKKXV/charm-by-clairo-f8a.png) |

For more examples, check out the [examples directory](https://github.com/TrueMyst/BeatPrints/tree/main/examples).


## ✨ Features

- **Polaroid Filter for Covers**: Give your track or album covers a vintage Polaroid look.  
- **Multi-language Support**: Supports English, Hindi, Russian, Japanese, Chinese, and Korean.  
- **Custom Cover Images**: Personalize posters with your own images.  
- **Theme Customization**: Switch between Dark and Light themes.  
- **Track & Album Selection**: Highlight your favorite track or entire album.  
- **Lyrics Highlighting**: Feature impactful lyrics directly on your poster.


## 🤝 Contributors

Thank you to all contributors for making BeatPrints better!

<p align="center">
 <a href="https://github.com/TrueMyst/BeatPrints/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=TrueMyst/BeatPrints" />
 </a>
</p>


## 💡 Why BeatPrints?

I created this project after finding out that people sell these posters on [Etsy](https://www.etsy.com/market/spotify_poster) at high prices, offering only digital downloads instead of shipping actual posters. 

I wanted to make it free for everyone to print themselves, as I believe my posters are simpler, cleaner, and prettier.


## ❤️  Special Thanks

- A big thanks to [Spotify Poster Generator](https://github.com/AnveshakR/poster-generator/) by [@AnveshakR](https://github.com/AnveshakR) for inspiring BeatPrints with amazing ideas!  
- Shoutout to [@Magniquick](https://github.com/Magniquick), [@Krishna-Gunjan](https://github.com/Krishna-Gunjan), and [@itsnotrin](https://github.com/itsnotrin) for their awesome contributions!  
- Thanks to [@T-Dynamos](https://github.com/T-Dynamos) and [@cherriae](https://github.com/cherriae) for their great improvements and tweaks.  
- A special nod to [@itsnotrin](https://github.com/itsnotrin) for helping make album poster generation possible!  


## 📜 License

BeatPrints is distributed under the **Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License**:

- **Use**: Free to share and adapt.  
- **Attribution**: Provide credit and a link to the license.  
- **NonCommercial**: Not for commercial use.  
- **ShareAlike**: Adaptations must follow the same license.  

Read the full license [here](https://github.com/TrueMyst/BeatPrints/blob/main/LICENSE).  


<p align="center">
Made with 💜 <br>
elysianmyst, 2024
</p>
