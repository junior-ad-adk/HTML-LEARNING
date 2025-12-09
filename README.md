# 🌟 Wellness App - Mental Health & Self-Care Application

A beautiful, feature-rich Flutter app designed to support mental wellness, personal growth, and daily self-care routines.

## ✨ Features

### 1. **Home Screen**
- Clean, minimal UI with soft pastel colors
- 9 quick-access buttons for all features
- Personalized welcome message
- Modern Flutter Material 3 design

### 2. **Breathing Exercise**
- 1, 3, and 5-minute timer options
- Animated expanding/contracting circle
- Real-time breathing instructions: "Breathe In", "Hold", "Breathe Out"
- Start, Stop, and Reset controls
- Completion feedback

### 3. **Mood Meter**
- 5 emoji-based mood selections (🙂 😐 ☹️ 😖 ❤️)
- Weekly mood tracking graph
- Mood history and statistics
- Local storage with SharedPreferences
- Visual trend analysis

### 4. **Future Planner**
- Daily, Weekly, and Long-term goal management
- Editable checklist UI
- Progress tracking bar
- Add, edit, and delete goals
- Persistent local storage

### 5. **Positive Affirmations**
- Random daily affirmation display
- 12 built-in affirmations
- Add custom affirmations
- Manage custom affirmations with delete option
- Beautiful card-based UI

### 6. **Journal & Notes**
- Private note-taking with PIN lock security
- Add, edit, and delete entries
- Timestamps for all entries
- Sorted by latest first
- 4-digit PIN protection

### 7. **Relaxing Sounds**
- 5 built-in ambient sounds:
  - 🌧️ Rain
  - 🌊 Ocean Waves
  - 🌲 Forest Birds
  - 🎹 Soft Piano
  - 🔊 White Noise
- Loop mode toggle
- Play/Pause controls
- Visual feedback for currently playing sound

### 8. **Voice Messages**
- 5 pre-recorded voice guidance messages:
  - 🌅 Morning Motivation
  - 🧘 Calming Voice
  - 😴 Bedtime Story
  - ✨ Affirmation Recording
  - 🙏 Gratitude Practice
- Progress bar with time tracking
- Play/Pause controls
- Message descriptions

### 9. **Playlist & Message BF**
- **Playlist**: Quick link to Spotify or any music platform (customizable URL)
- **Message BF**: Direct WhatsApp shortcut (customizable phone number)
- URL launcher integration

---

## 🛠️ Installation & Setup

### Prerequisites
- Flutter SDK (3.0.0 or later)
- Dart SDK
- Android Studio / Xcode
- Physical device or emulator

### Step 1: Clone & Setup
```bash
# Clone or download this project
cd wellness_app

# Get all dependencies
flutter pub get
```

### Step 2: Configure External Links
Edit `lib/utils/external_links.dart`:

```dart
// Replace with your Spotify playlist URL
static const String playlistUrl = 'https://open.spotify.com/playlist/YOUR_PLAYLIST_ID';

// Replace with your phone number (country code included, no spaces)
// Example: +919876543210
static const String whatsappNumber = '+91XXXXXXXXXX';
```

### Step 3: Add Audio Files
Create these directories and add audio files:
- `assets/audio/rain.mp3`
- `assets/audio/ocean.mp3`
- `assets/audio/forest.mp3`
- `assets/audio/piano.mp3`
- `assets/audio/whitenoise.mp3`
- `assets/voice/motivation.mp3`
- `assets/voice/meditation.mp3`
- `assets/voice/bedtime.mp3`
- `assets/voice/affirmations.mp3`
- `assets/voice/gratitude.mp3`

You can find royalty-free audio from:
- [Freesound](https://freesound.org/)
- [YouTube Audio Library](https://www.youtube.com/audiolibrary)
- [Pixabay](https://pixabay.com/music/)

### Step 4: Run the App
```bash
# Run on connected device or emulator
flutter run

# Run with verbose logging
flutter run -v
```

---

## 📦 Dependencies

```yaml
# UI & Navigation
flutter: sdk
cupertino_icons: ^1.0.2
animations: ^2.0.11

# Local Storage
shared_preferences: ^2.2.2
hive: ^2.2.3
hive_flutter: ^1.1.0

# Audio
just_audio: ^0.9.34

# Utilities
intl: ^0.19.0
url_launcher: ^6.2.1

# Charts
fl_chart: ^0.65.0

# Device Features
vibration: ^1.8.4
```

---

## 🎨 UI/UX Design

### Color Palette
- **Primary Purple**: `#D4A5D8` - Main accent color
- **Dark Purple**: `#7B68A6` - Text and UI elements
- **Light Purple**: `#E8D5F0` - Backgrounds
- **Soft Beige**: `#FAF7F2` - Main background
- **Accent Colors**: Orange, Blue, Green, Pink for variety

### Key Design Principles
- Soft, calming color scheme
- Rounded corners for a friendly feel
- Consistent spacing and typography
- Accessibility-first approach
- Minimalist, clutter-free UI

---

## 📁 Project Structure

```
lib/
├── main.dart                          # App entry point
├── screens/
│   ├── home_screen.dart              # Main home page
│   ├── breathing_screen.dart         # Breathing exercises
│   ├── mood_meter_screen.dart        # Mood tracking
│   ├── future_planner_screen.dart    # Goals management
│   ├── affirmations_screen.dart      # Affirmations
│   ├── journal_screen.dart           # Journal/Notes
│   ├── relaxing_sounds_screen.dart   # Ambient sounds
│   └── voice_messages_screen.dart    # Voice messages
├── utils/
│   ├── external_links.dart           # URL launcher utilities
│   └── theme.dart                    # Colors & typography
├── pubspec.yaml                       # Dependencies
└── assets/                            # Audio files

android/
ios/
```

---

## 🔐 Security

### Journal PIN Lock
- 4-digit PIN protection
- Stored in SharedPreferences
- Set during first access
- Unlock with PIN to view/add entries

### Best Practices
- User data stored locally on device
- No cloud sync (privacy-first)
- Clear separation of concerns
- Input validation on all forms

---

## 📝 Customization Guide

### Change Colors
Edit `lib/utils/theme.dart` or modify values in each screen's `Color()` constructor.

### Add More Affirmations
In `lib/screens/affirmations_screen.dart`, add to `_defaultAffirmations` list:
```dart
_defaultAffirmations = [
  'Existing affirmations...',
  'Your new affirmation here', // Add new ones
];
```

### Change Breathing Cycle Duration
In `lib/screens/breathing_screen.dart`, modify:
```dart
// Change 12 to your preferred cycle length (in seconds)
duration: const Duration(seconds: 12),
```

### Add More Goals Categories
Edit `future_planner_screen.dart` to add a new goal type beyond Daily/Weekly/Long-term.

### Extend Voice Messages
In `lib/screens/voice_messages_screen.dart`, add to `_messages` list:
```dart
VoiceMessage(
  id: '6',
  title: 'Your Message',
  description: 'Description',
  emoji: '📱',
  assetPath: 'assets/voice/your_file.mp3',
),
```

---

## 🚀 Performance Optimization

- Lazy loading of screens
- Efficient audio player with resource cleanup
- Optimized SharedPreferences caching
- Minimal widget rebuilds
- Proper disposal of controllers

---

## 📱 Device Requirements

- **Android**: API 21 and above
- **iOS**: iOS 11.0 and above
- **RAM**: 2GB minimum
- **Storage**: 50MB minimum

---

## 🐛 Troubleshooting

### Audio Files Not Playing
- Ensure files are in correct `assets/` directory
- Check `pubspec.yaml` has correct asset paths
- Run `flutter clean` and rebuild

### SharedPreferences Not Persisting
- Ensure app isn't being uninstalled between sessions
- Check device storage space
- Try running `flutter clean`

### URL Launcher Issues
- Ensure URLs are properly formatted
- Check internet connectivity
- Verify apps (Spotify, WhatsApp) are installed

---

## 🎯 Future Enhancements

- Cloud backup for user data
- Social sharing features
- Push notifications for reminders
- Dark mode support
- Multi-language support
- Customizable app themes
- Widget integration
- Health app integration
- Export journal as PDF

---

## 📄 License

This project is provided as-is for personal use and mental wellness support.

---

## 💝 About

Created with ❤️ to support mental health and personal wellbeing. Take care of yourself, one moment at a time.

---

## ✉️ Support

For issues, suggestions, or customizations, feel free to modify the code according to your needs!

**Remember**: This app is a companion to professional mental health care, not a replacement. Always seek professional help if needed.

---

**Happy Wellness Journey! 🌟**
