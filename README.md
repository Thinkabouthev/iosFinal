# TV-show Tracker (iOS Final)

iOS app to track TV shows: library, show details, episodes list, episode notes, watched status and AI episode summary.

## Requirements
- Xcode 15+ (or your course version)
- iOS 16+
- Swift 5+
- Internet connection (TMDB)
- (Optional) Python 3.12+ for backend AI summary

## Dependencies
- Kingfisher (SPM) for images

## Setup (iOS)
1. Open `Final.xcodeproj`
2. Install Swift Package dependencies (Xcode will prompt автоматически)
3. Add your TMDB API key in `Secrets.swift` (or `Secrets` file)
4. Run on iOS Simulator

## Setup (Backend AI Summary) – optional but recommended
Backend is in `/Back`.

1. Create `.env` in `Back/`:
   OPENAI_API_KEY=YOUR_OPENAI_KEY
   OPENAI_MODEL=gpt-4o-mini

2. Install and run:
   cd Back
   python3.12 -m venv .venv
   source .venv/bin/activate
   pip install -r requirements.txt
   uvicorn main:app --reload --port 8000

3. iOS uses:
   POST http://127.0.0.1:8000/ai/summary
   If you run app on a real device, replace 127.0.0.1 with your Mac local IP (e.g. http://192.168.x.x:8000).

## Features
- Library screen with search + status filter
- Show details (poster, genres/year/rating) + season selector
- Episodes list for selected season
- Episode details: Notes + Watched toggle + AI Summary
- Local storage (UserDefaults) for notes and watched flags
