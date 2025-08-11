# 🍏 macOS මත Flutter SDK Install කිරීම – පියවරෙන් පියවර Guide

> **සිංහල** භාෂාවෙන් සම්පූර්ණ Flutter development environment setup කිරීමේ සරල මගපෙන්වීම

## 📌 හැඳින්වීම

මෙම මගපෙන්වීමෙන් ඔබට **macOS** මත **Flutter SDK** install කර iOS සහ Android සඳහා apps development ආරම්භ කිරීමේ සියලුම පියවරන් සරලව සහ පැහැදිලිව ලබා ගන්න පුළුවන්.

---

## 📋 අවශ්‍ය Requirements

- macOS 10.14 (Mojave) හෝ නවතම version
- අවම වශයෙන් 2.8 GB disk space
- Git සහ cURL tools (සාමාන්‍යයෙන් macOS එකේ built-in)
- Internet connection

---

## 🚀 Installation Steps

### 1️⃣ Homebrew Install කිරීම

Homebrew යනු macOS මත software packages ඉක්මනින් install කිරීමේ CLI package manager එකකි.

**Terminal** එකේ මෙම command එක run කරන්න:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

> **සටහන:** Installation අවසානයේ PATH එක manually add කරන්න කියලා instructions පෙන්වයි. ඒවා follow කරන්න.

---

### 2️⃣ Git Install කිරීම

Flutter SDK download කිරීම සඳහා Git අවශ්‍යයි:

```bash
brew install git
```

Git version check කිරීම:
```bash
git --version
```

---

### 3️⃣ Flutter SDK Install කිරීම

#### 🎯 විකල්ප 1: Homebrew මගින් (Recommended - Easy Method)

```bash
brew install flutter
```

> **වාසි:** 
> - PATH එක automatically configure වෙයි
> - Updates ඉක්මනයි
> - Dependencies කළමනාකරණය වෙයි

#### 🎯 විකල්ප 2: Manual Download (Official Site)

1. [Flutter SDK for macOS](https://docs.flutter.dev/get-started/install/macos) වෙත යන්න
2. ZIP file එක download කරන්න
3. Extract කර `/Users/YourName/development/flutter` වැනි folder එකකට move කරන්න

```bash
# Development folder එකක් හදන්න
mkdir -p ~/development
cd ~/development

# ZIP file එක extract කරන්න (downloads folder එකේ තියෙනවා නම්)
unzip ~/Downloads/flutter_macos_*.zip
```

---

### 4️⃣ PATH එක Set කිරීම (Manual Install කරන විට පමණයි)

#### Flutter SDK path සොයා ගැනීම:
```bash
cd ~/development/flutter
pwd
```

#### PATH එක temporarily set කිරීම:
```bash
export PATH="$PATH:$HOME/development/flutter/bin"
```

#### Permanent PATH setup (zsh shell සඳහා):
```bash
# .zshrc file එක edit කරන්න
nano ~/.zshrc
```

File එකේ අවසානයට add කරන්න:
```bash
# Flutter PATH
export PATH="$PATH:$HOME/development/flutter/bin"
```

Changes save කර terminal එක restart කරන්න:
```bash
source ~/.zshrc
```

---

### 5️⃣ iOS Development Environment Setup

#### Xcode Command Line Tools Install කිරීම:
```bash
xcode-select --install
```

#### Xcode Install කිරීම:
1. App Store මගින් **Xcode** download කර install කරන්න
2. Xcode එක open කර license agreement එක accept කරන්න

#### Xcode Configure කිරීම:
```bash
sudo xcode-select --switch /Applications/Xcode.app/Contents/Developer
sudo xcodebuild -runFirstLaunch
```

#### iOS Simulator Setup:
```bash
# Simulator open කරන්න
open -a Simulator
```

---

### 6️⃣ Android Development Environment Setup

#### Android Studio Install කිරීම:
1. [Android Studio](https://developer.android.com/studio) download කරන්න
2. Install කර open කරන්න
3. Setup wizard එක follow කරන්න

#### Required Components Install කිරීම:
- Android SDK
- Android SDK Command-line Tools
- Android SDK Build-Tools
- Android SDK Platform-Tools
- Android Virtual Device (AVD)

#### Android SDK Path Setup (if needed):
```bash
# .zshrc file එකේ add කරන්න
export ANDROID_SDK_ROOT=$HOME/Library/Android/sdk
export PATH=$PATH:$ANDROID_SDK_ROOT/tools
export PATH=$PATH:$ANDROID_SDK_ROOT/platform-tools
```

---

### 7️⃣ Flutter Doctor මගින් Setup Verification

```bash
flutter doctor
```

මෙම command එක run කරන විට:
- ✅ Green checkmarks - හරිම configuration
- ❌ Red crosses - fix කරන්න ඕනේ issues
- ⚠️ Yellow warnings - optional issues

#### Common Issues සහ Solutions:

```bash
# Flutter doctor සියලුම details සමඟ
flutter doctor -v

# Android licenses accept කිරීම
flutter doctor --android-licenses
```

---

### 8️⃣ Test Project එකක් Create කර Run කිරීම

#### New Flutter Project Create කිරීම:
```bash
# New project create කරන්න
flutter create my_first_app

# Project folder එකට යන්න
cd my_first_app
```

#### Project Run කිරීම:

**iOS Simulator එකේ:**
```bash
flutter run
```

**Android Emulator එකේ:**
```bash
# Available devices බලන්න
flutter devices

# Specific device එකේ run කරන්න
flutter run -d "device_id"
```

**Chrome Browser එකේ (Web):**
```bash
flutter run -d chrome
```

---

## 🔍 Verification සහ Troubleshooting

### Flutter Installation Verify කිරීම:

```bash
# Flutter version check
flutter --version

# Flutter path check
which flutter
```

**Homebrew install කරන්න නම්:**
- Output: `/opt/homebrew/bin/flutter` (M1/M2 Macs)
- Output: `/usr/local/bin/flutter` (Intel Macs)

**Manual install කරන්න නම්:**
- Output: `~/development/flutter/bin/flutter`

### Common Commands:

```bash
# Flutter update කිරීම
flutter upgrade

# Available devices list කිරීම
flutter devices

# Flutter help
flutter help

# Project dependencies install කිරීම
flutter pub get

# Project clean කිරීම
flutter clean
```

---

## 📱 Development Tips

### VS Code Extensions (Recommended):
- **Flutter** - Official Flutter extension
- **Dart** - Dart language support
- **Flutter Widget Snippets** - Code snippets
- **Awesome Flutter Snippets** - Additional snippets

### Android Studio Plugins:
- **Flutter Plugin**
- **Dart Plugin**

### Useful Flutter Commands:
```bash
# Hot reload enable කිරීම (development අතරතුර)
# r key press කරන්න app run වෙන විට

# Hot restart
# R key (shift + r) press කරන්න

# Build APK (Android)
flutter build apk

# Build iOS app
flutter build ios
```

---

## 🎯 Next Steps

1. **Flutter Documentation** පড්ධතිගතව කියවන්න
2. **Dart Programming Language** basics ඉගෙන ගන්න
3. **Flutter Widgets** tutorials follow කරන්න
4. Simple apps build කරන්න practice සඳහා
5. **State Management** concepts ඉගෙන ගන්න

---

## 📞 Additional Resources

- [Flutter Official Documentation](https://docs.flutter.dev/)
- [Dart Language Tour](https://dart.dev/guides/language/language-tour)
- [Flutter YouTube Channel](https://www.youtube.com/c/flutterdev)
- [Flutter Community](https://flutter.dev/community)

---

## ⚠️ Troubleshooting

### Issues සහ Solutions:

**Issue 1:** `flutter: command not found`
```bash
# PATH එක properly set කරලා ද check කරන්න
echo $PATH | grep flutter
```

**Issue 2:** Xcode issues
```bash
# Xcode path reset කිරීම
sudo xcode-select --reset
```

**Issue 3:** Android SDK path issues
```bash
# SDK path manually set කරන්න
flutter config --android-sdk ~/Library/Android/sdk
```

---

**🎉 සියලු දේ සාර්ථකව install වුණාම ඔබට Flutter මගින් cross-platform mobile apps develop කරන්න පුළුවන්!**

> **සටහන:** මෙම guide එක නිතරම update කරන්න. Flutter ecosystem එක නිතර වෙනස් වෙනවා.