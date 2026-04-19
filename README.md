# sanjugeci-db
A dedicated multi-layered lyric database for the sanjugeci application.

## 📁 Directory Structure
The repository is strictly organized by the first letter of the artist's name to ensure fast retrieval:

```text
sanjugeci-db/
├── A/                             # First letter of the artist's name
│   └── ArtistName/                # Full artist name
│       └── Song Title/            # Specific song folder
│           ├── README.md          # Lyric documentation & metadata
│           ├── Artwork.png        # Song cover art
│           ├── Song Title.json    # The core file parsed by sanjugeci
│           ├── Song Title.lrc     # Original timed lyrics
│           └── Song Title.txt     # Raw plaintext lyrics
```

## 📄 JSON Data Structure
The .json file is the primary format used by the application. It provides synchronized multi-layered text. It must follow this strict structure:

```JSON
{
  "lyrics": [
    {
      "time": 12345,
      "text": "Original lyric text here",
      "romanization": "Romanization here (optional)",
      "translate": "Translation text here (optional)"
    }
  ]
}
```
- time: Milliseconds elapsed from the start of the song.
- text: The original lyric line.
- romanization: Romanized pronunciation (can be left empty "").
- translate: Translated line (can be left empty "").

## ✨ Features
Unlike standard databases, sanjugeci-db provides rich lyrics including:

- Original Characters: High-quality native characters (Hanzi, Hangul, Kana, etc.).
- Romanization: Romanization support (Pinyin, Romaji, etc.) for non-native readers.
- Translations: Translated lines synced perfectly with the audio track.

## ⚙️ Lyric Creation Workflow
The timing and extraction process follows these steps:

1. Initial Search: Look for an existing, accurate .lrc file from public databases. If unavailable, proceed to manual creation:
    - Lyric Extraction: The audio file is processed through AI models to extract the raw plaintext.
    - Manual Synchronization: I use [DistroKid Potato](https://distrokid.com/potato/) to manually time-sync the lyrics for millisecond accuracy.
2. Enrichment: AI models are utilized to generate clear, context-aware romanization and translations based on the raw text.

## ⚠️ Copyright & Disclaimer
All copyrights, lyrics, artwork, and related assets belong to their respective owners. This repository is intended for personal database use and archiving purposes only. **No copyright infringement is intended.**