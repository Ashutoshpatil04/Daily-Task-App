# 📱 Daily Tasks App - Complete Build Guide

## Overview
This guide will help you build and install the **Daily Tasks** Android app on your phone. The app stores all data locally - no internet required after installation!

---

## Prerequisites

### 1. Install Android Studio
- Download from: https://developer.android.com/studio
- Run the installer (use default options)
- **Important:** During installation, make sure "Android SDK" is checked

### 2. Install Java JDK (if not included)
- Usually bundled with Android Studio
- If needed: https://adoptium.net/temurin/releases/

---

## Step-by-Step Build Instructions

### Step 1: Open the Project

**Option A - Command Line:**
```bash
cd "D:\machine learning\projects\TaskManagerApp"
npx cap open android
```

**Option B - Manual:**
1. Open Android Studio
2. Click **File → Open**
3. Navigate to: `D:\machine learning\projects\TaskManagerApp\android`
4. Click **OK**

---

### Step 2: Configure Android SDK (First Time Only)

If you see "SDK not found" or "Invalid SDK path":

1. Go to **Tools → SDK Manager** (or ⚙️ icon → SDK Manager)
2. Note the "Android SDK Location" at the top - this is your SDK path
3. If empty, click **Edit** and choose a location like:
   ```
   C:\Users\YourUsername\AppData\Local\Android\Sdk
   ```

4. In **SDK Platforms** tab, check:
   - ✅ Android 14.0 (API 34) - or latest available

5. In **SDK Tools** tab, check:
   - ✅ Android SDK Build-Tools
   - ✅ Android SDK Platform-Tools
   - ✅ Android SDK Command-line Tools

6. Click **Apply** → Accept licenses → **OK**
7. Wait for download to complete (500MB - 1GB)

---

### Step 3: Wait for Gradle Sync

After opening the project:
1. Look at the bottom status bar
2. Wait for "Gradle sync" to complete (2-5 minutes first time)
3. If sync fails, click **File → Sync Project with Gradle Files**

---

### Step 4: Build the APK

1. Go to menu: **Build → Build Bundle(s) / APK(s) → Build APK(s)**
2. Wait for build to complete (1-2 minutes)
3. A notification will appear: "Build completed successfully"
4. Click **locate** in the notification to find the APK

**APK Location:**
```
D:\machine learning\projects\TaskManagerApp\android\app\build\outputs\apk\debug\app-debug.apk
```

---

### Step 5: Install on Your Phone

#### Method 1: USB Cable
1. Connect phone to PC via USB
2. Enable "File Transfer" mode on phone
3. Copy `app-debug.apk` to your phone's Download folder
4. On phone, open Files app → Downloads → tap the APK
5. Tap **Install** (enable "Install from unknown sources" if prompted)

#### Method 2: Email/Cloud
1. Email the APK to yourself, OR
2. Upload to Google Drive/OneDrive
3. Download on your phone
4. Tap to install

#### Method 3: Direct Install via ADB
```bash
adb install app-debug.apk
```

---

## Troubleshooting

### "SDK not found"
- Open SDK Manager and download SDK components (see Step 2)

### "Gradle sync failed"
- Check internet connection
- Click **File → Invalidate Caches → Invalidate and Restart**
- Try **File → Sync Project with Gradle Files**

### "Build failed"
- Check Build output window for errors
- Usually missing SDK - install via SDK Manager
- Try **Build → Clean Project**, then **Build → Rebuild Project**

### "App not installed" on phone
- Enable "Install from unknown sources" in phone Settings
- Settings → Security → Unknown sources → Enable

### Can't find APK file
Navigate manually to:
```
D:\machine learning\projects\TaskManagerApp\android\app\build\outputs\apk\debug\
```

---

## Project Structure

```
TaskManagerApp/
├── android/           ← Android native project
│   └── app/
│       └── build/outputs/apk/debug/
│           └── app-debug.apk    ← Your installable APK!
├── www/               ← Web app files
│   └── index.html     ← The task manager app
├── capacitor.config.json
├── package.json
└── BUILD_GUIDE.md     ← This file
```

---

## App Features

✅ Add, edit, delete tasks
✅ Mark tasks complete/pending
✅ Priority levels (High/Medium/Low)
✅ Categories (Personal/Work/Health/Shopping)
✅ Due dates
✅ Search & filter tasks
✅ Progress tracking
✅ Dark/Light mode
✅ **All data stored locally on your device**

---

## Quick Commands Reference

```bash
# Navigate to project
cd "D:\machine learning\projects\TaskManagerApp"

# Open in Android Studio
npx cap open android

# Sync web files to Android
npx cap sync android

# Build via command line (requires Gradle)
cd android
gradlew assembleDebug
```

---

## Need Help?

If you encounter issues:
1. Make sure Android Studio is fully updated
2. Ensure SDK is properly installed via SDK Manager
3. Check that Java JDK 17+ is installed
4. Restart Android Studio and try again

---

*Generated for Daily Tasks App v1.0*
