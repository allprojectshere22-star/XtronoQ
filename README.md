# TV Vault

TV Vault is an offline-first Flutter app for tracking TV shows and movies.
It imports and exports the TV Time JSON formats, stores your library locally
with Drift, and keeps the experience usable without a network connection.

## What it does

TV Vault helps you:

- Import TV Time JSON exports for movies, series, and lists
- Export your library back to TV Time-shaped JSON
- Add, edit, and delete movies and series
- Track watch status, favorites, notes, and ratings
- Browse with global search and filters by status, media type, genre, and favorites
- View your library through Home, Library, Calendar, Statistics, and Settings tabs
- Enrich titles from TMDB when you provide your own API key
- Use a dark-default Material 3 UI with light mode support
- Enjoy glassmorphism-style surfaces and poster-focused browsing

## Key features

### Import and export

- TV Time movies JSON
- TV Time series JSON
- TV Time lists JSON
- Bundled sample library for quick first launch testing
- Round-trip export from the local database back into TV Time-shaped JSON

### Library management

- Add and delete titles
- Edit title metadata, notes, status, rating, and favorite state
- Per-episode watched toggles for series
- Color-coded watch statuses throughout the UI
- Responsive poster grid and list layouts
- TMDB enrichment for posters, backdrops, overview, genres, cast, crew, trailers, and providers

### Browsing and insights

- Global search
- Status filters
- Media-type filters
- Favorite-only filter
- Genre filter
- Home tab for continue-watching, plan-to-watch, and recently added items
- Calendar tab for watched days and watch history
- Statistics tab for status, genre, and monthly trends
- Settings tab for theme, TMDB key, import/export, and app info

## WatchStatus values

Watch statuses are separate from favorite state. Favorites are a heart flag.

| Value | Meaning | Color |
| --- | --- | --- |
| `planToWatch` | Planned to watch | Blue-grey |
| `watching` | Currently watching | Amber |
| `upToDate` | Caught up with a series | Teal |
| `completed` | Finished watching | Green |
| `onHold` | Paused for now | Orange |
| `dropped` | Abandoned | Red |

## Tech stack

- Flutter
- Material 3
- Riverpod
- Drift
- fl_chart
- table_calendar
- google_fonts
- cached_network_image
- file_picker
- share_plus
- path_provider
- shared_preferences

## Project structure

The app follows a clean MVVM-style layout:

- `lib/core/` — theme, constants, and utility helpers
- `lib/domain/` — application entities and shared business concepts
- `lib/data/` — Drift database, import/export, TMDB client, settings, repository
- `lib/presentation/` — providers, screens, widgets, and UI utilities

## How to build and run

1. Fetch dependencies:

   ```bash
   flutter pub get
   ```

2. Generate Drift and other build outputs:

   ```bash
   dart run build_runner build --delete-conflicting-outputs
   ```

3. Run the app:

   ```bash
   flutter run
   ```

4. Build a debug APK:

   ```bash
   flutter build apk --debug
   ```

## TMDB API key

TMDB enrichment is optional and only works after you add your own API key.

To configure it:

1. Open **Settings**
2. Enter your TMDB API key in the TMDB section
3. Save the key

The key is stored locally in shared preferences. TV Vault does not hardcode or
bundle a TMDB key.

## Importing data

### Bundled sample library

If you want to explore the app immediately, use the bundled sample import from
the **Settings** screen. It loads the sample TV Time JSON files included under
`assets/sample/`.

### Your own TV Time export

Use the import buttons in **Settings** to load your own TV Time JSON exports:

- Movies JSON
- Series JSON
- Lists JSON

You can import each file separately. Re-importing updates existing titles and
collections instead of duplicating them.

## Architecture

See `docs/ARCHITECTURE.md` for a short overview of the layering and data flow.

A new Flutter project.

## Getting Started

This project is a starting point for a Flutter application.

A few resources to get you started if this is your first Flutter project:

- [Learn Flutter](https://docs.flutter.dev/get-started/learn-flutter)
- [Write your first Flutter app](https://docs.flutter.dev/get-started/codelab)
- [Flutter learning resources](https://docs.flutter.dev/reference/learning-resources)

For help getting started with Flutter development, view the
[online documentation](https://docs.flutter.dev/), which offers tutorials,
samples, guidance on mobile development, and a full API reference.
