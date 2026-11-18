# My Offline Clothing Assistant

A C++17 terminal application that helps you manage your wardrobe, plan outfits, prepare for trips, and make more informed clothing decisions. It works offline and stores personal records in local TXT files—no database or cloud account required.

## Features

- **Personal profile & preferences:** body measurements, preferred fit, colours, style, occasion, and season.
- **Digital wardrobe:** add and manage owned clothes, including clean/laundry status.
- **Outfit recommendations:** style inspiration and wardrobe-based combinations using occasion, weather, and colour compatibility.
- **Outfit planner & history:** schedule outfits and record what you have worn.
- **Travel packing planner:** create trip checklists and track packed items.
- **Favorites & purchase wishlist:** save favourite clothes, estimate planned purchases, and add purchased items to your wardrobe.
- **Clothing care assistant:** fabric care, stain-removal, and maintenance guidance.
- **Color harmony explorer:** browse colour combinations.
- **AI virtual try-on prompt generator:** create detailed prompts for an external image-generation or virtual try-on tool. The external tool performs image generation.
- **Wardrobe insights:** review wardrobe, category, colour, and laundry summaries.
- **Clothing size advisor:** estimate clothing and shoe sizes from measurements. Results are approximate; check brand size charts.
- **Outfit rating (1–10):** rate fit, comfort, occasion, weather, colour coordination, and footwear matching, then receive a weighted score and suggestions.

## Technology

- C++17
- CMake
- Plain-text TXT storage
- GitHub Actions build workflow

## Project structure

```text
.
├── .github/workflows/       # Continuous integration
├── include/                 # Header files and data structures
├── resources/               # Sample wardrobe and care-reference data
├── src/                     # Application modules
├── CMakeLists.txt
└── README.md
```

## Build and run

Run commands from the repository root.

### Windows (PowerShell)

```powershell
cmake -S . -B build
cmake --build build
.\build\clothing_assistant.exe
```

### Linux / macOS

```bash
cmake -S . -B build
cmake --build build
./build/clothing_assistant
```

### Compile directly with g++

Windows PowerShell:

```powershell
g++ -std=c++17 -Wall -Wextra -pedantic -Iinclude src/*.cpp -o clothing_assistant.exe
.\clothing_assistant.exe
```

Linux / macOS:

```bash
g++ -std=c++17 -Wall -Wextra -pedantic -Iinclude src/*.cpp -o clothing_assistant
./clothing_assistant
```

## Local data and privacy

The application creates and updates TXT files in the project root as features are used (such as profile, wardrobe, history, planner, travel, favorites, and wishlist records). These runtime files are excluded from Git through `.gitignore`. Sample catalogue and reference data are stored in `resources/`.

**Back up your local TXT files before changing branches or moving the project.** The application uses the pipe character (`|`) as a field separator; avoid entering it inside values.

## Notes

- Outfit suggestions and size estimates are rule-based, not live AI predictions.
- The prompt generator creates prompt text only; an external AI image tool is needed for image generation or virtual try-on.
- Travel packing quantities are starting estimates and should be adjusted to the trip.
- Follow each garment's care label first.
- This is a local, single-user terminal application.

## Author

Created by [Kashif Reza](https://github.com/kashif-reza).
