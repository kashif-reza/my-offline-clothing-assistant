# My Offline Clothing Assistant

A C++17, terminal-based personal clothing and wardrobe assistant. It runs locally, works offline, and stores personal information in plain-text files—no database or cloud account required.

## Features

- **Personal profile & preferences** — save body measurements, preferred fit, colours, style, occasion, and season.
- **Digital wardrobe** — add and manage owned clothing, including laundry/availability status.
- **Outfit recommendations** — get style inspiration and combinations based on your wardrobe, occasion, weather, and colour compatibility.
- **Outfit planner & history** — schedule outfits and keep a record of what you have worn.
- **Travel packing planner** — create trip checklists and track packed items.
- **Favorites & purchase wishlist** — save favourite clothes, estimate planned purchases, and move purchased items into your wardrobe.
- **Clothing care assistant** — browse fabric care, stain-removal, and maintenance guidance.
- **Color harmony explorer** — review colour combinations.
- **AI virtual try-on prompt generator** — create detailed prompts for an external image-generation or virtual try-on tool. Image generation itself is performed by that external tool.
- **Wardrobe insights** — review wardrobe, category, colour, and laundry summaries.
- **Clothing size advisor** — estimate clothing and shoe sizes from measurements. Estimates are approximate and should be checked against brand size charts.
- **Outfit rating (1–10)** — rate an outfit across fit, comfort, occasion, weather, colour coordination, and footwear matching, then receive a weighted score and feedback.

## Tech stack

- C++17
- CMake
- Plain-text TXT file storage
- GitHub Actions for build checks

## Project structure

```text
.
├── .github/workflows/       # CI build workflow
├── include/                 # Header files and data structures
├── resources/               # Sample wardrobe and clothing-care reference data
├── src/                     # Application modules
├── CMakeLists.txt
└── README.md
```

## Build and run

Run all commands from the repository root. CMake is recommended.

### Windows (PowerShell)

```powershell
cmake -S . -B build
cmake --build build
.\build\wearwise.exe
```

### Linux / macOS

```bash
cmake -S . -B build
cmake --build build
./build/wearwise
```

### Compile directly with g++

```bash
g++ -std=c++17 -Wall -Wextra -pedantic -Iinclude src/*.cpp -o clothing-assistant
```

Then run `.\clothing-assistant.exe` on Windows or `./clothing-assistant` on Linux/macOS.

## Local data and privacy

The application creates and updates TXT files in the project root as features are used (for example, profile, wardrobe, history, planner, travel, favorites, and wishlist files). These are local runtime records and are excluded from Git through `.gitignore`. The sample catalogue and reference guides are kept in `resources/`.

**Back up your local TXT data before changing branches or moving the project.** The application uses the pipe character (`|`) as a field separator; avoid entering it inside values.

## Important notes

- Outfit suggestions and size estimates are rule-based, not live AI predictions.
- The prompt generator prepares text only; an external AI image tool is needed for image generation or virtual try-on.
- Travel packing quantities are starting suggestions and should be adjusted for the trip.
- Follow each garment's care label first.
- This is a local, single-user terminal application.

## Author

Created by [Kashif Reza](https://github.com/kashif-reza).
