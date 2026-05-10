# 🎵 MyAudio – Music & Library Management System

A text-based Java application simulating a music platform (think Spotify or Apple Music) — browse an online store, download songs and audiobooks to your personal library, manage playlists, and search by title, artist, genre, or partial keyword.

---

## 📌 Overview

MyAudio models a real-world audio content ecosystem using core OOP principles: inheritance, polymorphism, abstract classes, and custom exceptions. Users interact via a command-line interface to manage their personal audio library.

---

## 🗂️ Project Structure

| Class | Role |
|---|---|
| `AudioContent` | Abstract base class for all audio types — holds title, year, ID, length |
| `Song` | Extends `AudioContent` — adds artist, composer, genre, lyrics |
| `AudioBook` | Extends `AudioContent` — adds author, narrator, chapters |
| `Playlist` | Manages a named collection of mixed audio content |
| `Library` | Core logic — stores songs, audiobooks, playlists; handles download, sort, play, delete |
| `AudioContentStore` | Simulates an online store; reads from `store.txt`; supports search by title/artist/genre |
| `MyAudioUI` | Entry point — reads keyboard commands and delegates to Library/Store |

---

## ⚙️ Features

**Library Management**
- Download songs and audiobooks from the store (single or range)
- Delete songs from the library and any playlists they belong to
- List all songs, audiobooks, artists, or playlists

**Playback**
- Play a song by library index
- Play a specific chapter of an audiobook
- Play one item or all items in a playlist

**Playlists**
- Create playlists, add/remove content, print contents

**Search (Store)**
- `SEARCH` — exact title match
- `SEARCHA` — by artist name
- `SEARCHG` — by genre (POP, ROCK, JAZZ, HIPHOP, RAP, CLASSICAL)
- `SEARCHP` — partial keyword match across title, artist, composer, lyrics

**Bulk Download**
- `DOWNLOADA` — download all content by a specific artist
- `DOWNLOADG` — download all songs of a specific genre

**Sorting**
- Sort library songs by year, name (alphabetical), or length

---

## 🧠 Key Concepts Used

- **Inheritance & Polymorphism** — `Song` and `AudioBook` extend `AudioContent`
- **Abstract Classes** — `AudioContent` defines the contract for subtypes
- **Comparable & Comparator** — used for sorting songs
- **Custom Exceptions** — `AlreadyDownloaded`, `AlreadyExists`, `NotFound`, `NoMatchesException`
- **HashMaps** — for O(1) lookup by title, artist, and genre
- **File I/O** — store content loaded dynamically from `store.txt`

---

## ▶️ How to Run

**1. Compile**
```bash
javac MyAudioUI.java
```

**2. Run**
```bash
java MyAudioUI
```

> Make sure `store.txt` is in the same directory before running.

**3. Example Commands**
```
STORE        → list all content in the store
DOWNLOAD     → download by index range
SONGS        → list your library songs
PLAYSONG     → play a song by index
MAKEPL       → create a playlist
ADDTOPL      → add content to a playlist
SEARCH       → search store by title
SEARCHA      → search by artist
SEARCHG      → search by genre
SORTBYNAME   → sort songs alphabetically
Q            → quit
```

---

## 🛠️ Tech Stack

- Java
- OOP (Inheritance, Polymorphism, Abstract Classes)
- Java Collections (ArrayList, HashMap)
- Java File I/O (Scanner + File)
