# 🚀 Quick Start Guide - Wellness App

## 5-Minute Setup

### 1. **Clone/Extract Project**
```bash
cd wellness_app
flutter pub get
```

### 2. **Update External Links** (IMPORTANT!)
Edit `lib/utils/external_links.dart`:

```dart
// Line 8 - Replace with your Spotify playlist URL
static const String playlistUrl = 'https://open.spotify.com/playlist/3aBiTtVEp5E8qHXQDgYS5k';

// Line 11 - Replace with your phone number
static const String whatsappNumber = '+919876543210';
```

**Phone Number Format**: 
- Include country code
- No spaces, dashes, or special characters
- Example: India (+91), USA (+1), UK (+44)

### 3. **Add Audio Files** (Optional - App works without them)

Create these folders if they don't exist:
```
assets/
├── audio/
│   ├── rain.mp3
│   ├── ocean.mp3
│   ├── forest.mp3
│   ├── piano.mp3
│   └── whitenoise.mp3
└── voice/
    ├── motivation.mp3
    ├── meditation.mp3
    ├── bedtime.mp3
    ├── affirmations.mp3
    └── gratitude.mp3
```

**Free Audio Sources**:
- [Freesound.org](https://freesound.org/)
- [Pexels Music](https://www.pexels.com/search/music/)
- [YouTube Audio Library](https://www.youtube.com/audiolibrary)

### 4. **Run the App**
```bash
flutter run
```

Or run on specific device:
```bash
flutter run -d <device_id>
```

---

## 🎯 Features Quick Reference

| Feature | Location | Function |
|---------|----------|----------|
| 🫁 Breathing | Tap "Breathing Exercise" | 1/3/5 min timers with animation |
| 😊 Mood | Tap "Mood Meter" | Track mood with emojis & graph |
| 📋 Goals | Tap "Future Planner" | Manage daily/weekly/long-term goals |
| ✨ Affirmations | Tap "Positive Affirmations" | Get random affirmation or add custom |
| 📔 Journal | Tap "Journal & Notes" | Write private notes (PIN protected) |
| 🎵 Sounds | Tap "Relaxing Sounds" | 5 ambient sounds with loop |
| 🎧 Playlist | Tap "Playlist" | Opens your Spotify playlist |
| 💬 Message BF | Tap "Message BF" | Opens WhatsApp chat |
| 🎤 Voice | Tap "Voice Messages" | Listen to recorded messages |

---

## 🔑 Key Settings

### Journal PIN Setup
1. Tap "Journal & Notes"
2. Tap the lock icon (🔒) in top right
3. Enter 4-digit PIN
4. Use PIN to unlock journal next time

### Customize Affirmations
Edit `lib/screens/affirmations_screen.dart`:
```dart
List<String> _defaultAffirmations = [
  'Your affirmation here',
  // Add more...
];
```

### Change Color Theme
Edit `lib/utils/theme.dart` or individual screen colors.

### Update Voice Messages
Edit `lib/screens/voice_messages_screen.dart` `_messages` list.

---

## 📱 Testing Checklist

- [ ] App launches without errors
- [ ] Home screen shows all 9 buttons
- [ ] Breathing timer animates smoothly
- [ ] Mood can be saved and graph updates
- [ ] Goals can be added/deleted
- [ ] Journal saves with PIN lock
- [ ] WhatsApp button opens chat
- [ ] Playlist button opens URL

---

## ⚠️ Common Issues

**Issue**: Audio files not found
- **Fix**: Ensure files are in `assets/audio/` and `assets/voice/` folders
- **Note**: App works without audio files (buttons just won't play sound)

**Issue**: WhatsApp button doesn't work
- **Fix**: WhatsApp must be installed, phone number must be valid
- **Format**: `+919876543210` (no spaces)

**Issue**: Journal PIN forgotten
- **Fix**: Uninstall and reinstall app (clears all data)
- **Alternative**: Manually delete SharedPreferences via ADB

**Issue**: "assets not found" error
- **Fix**: Run `flutter pub get` again
- **Alternative**: Delete `pubspec.lock` and `flutter pub get`

---

## 🎨 Customization Examples

### Change Primary Color
In `lib/main.dart`:
```dart
seedColor: const Color(0xFF7B68A6), // Change this
```

### Change Welcome Text
In `lib/screens/home_screen.dart`:
```dart
Text('Welcome, Bhumi!', // Change name here
```

### Add New Goal Type
In `lib/screens/future_planner_screen.dart`, modify `_selectedTab` logic.

---

## 📞 Support Quick Fixes

### Reset All Data
Uninstall → Delete app cache → Reinstall:
```bash
flutter clean
flutter pub get
flutter run
```

### Update Dependencies
```bash
flutter pub upgrade
flutter pub get
```

### Check Dart/Flutter Version
```bash
flutter --version
dart --version
```

---

## 🎯 Next Steps

1. **Personalize**: Update phone number, playlist link, colors
2. **Add Audio**: Find and add your favorite relaxing sounds
3. **Customize**: Change affirmations, messages, colors
4. **Test**: Run through all features
5. **Deploy**: Share with friends or deploy to app stores

---

## 📚 File Reference

| File | Purpose |
|------|---------|
| `main.dart` | App startup & theme |
| `home_screen.dart` | Main navigation hub |
| `external_links.dart` | WhatsApp & Spotify links |
| `theme.dart` | Colors & typography |
| `breathing_screen.dart` | Breathing exercise logic |
| `mood_meter_screen.dart` | Mood tracking & graph |
| `future_planner_screen.dart` | Goals management |
| `affirmations_screen.dart` | Affirmation display |
| `journal_screen.dart` | Notes with PIN lock |
| `relaxing_sounds_screen.dart` | Audio player |
| `voice_messages_screen.dart` | Voice guide player |

---

## ✅ You're Ready!

The app is ready to use. Start with updating your phone number and playlist link, then customize to your preferences!

**Enjoy your wellness journey! 🌟**

---

*For detailed documentation, see README.md*
