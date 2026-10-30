# Plan2Learn – Smart Study Buddy 🎓⚡

A modern Android application built with **Kotlin** and **Jetpack Compose**, translating the **Plan2Learn Obsidian Kinetic** design language into a functional study productivity tool.

---

## 📱 Features & Implemented Screens

1. **Home Dashboard**
   - **Daily Velocity Widget**: Circular progress ring (71% DONE) with electric gradient, live study duration (`3.2 / 4.5h`), task completion (`4 of 6`), and quiz accuracy (`85%`).
   - **Quick Action Bar**: `+ Subject`, `Focus Mode`, and `AI Quiz` (with "NEW" badge).
   - **Smart Recommendation Banner**: Ambient glowing bulb with personalized revision suggestion ("ML Midterm in 5 days") and one-tap quick quiz launcher.
   - **Today's Schedule**: Interactive session cards with completion checkboxes, priority chips (`HIGH PRIORITY`, `MEDIUM`, `REVIEW`), and lecture/time metadata.
   - **Motivational Quote**: James Clear (*Atomic Habits*) card.

2. **Course Subjects Management**
   - Add, edit, and delete enrolled subjects with custom color palettes (`#4D8EFF`, `#FFB4AB`, `#4EDEA3`, `#D0BCFF`, `#F59E0B`, `#00BCD4`).
   - Track weekly study hours target vs. total hours studied with progress bars.
   - Milestone and exam date countdown tracking.
   - Quick "Focus" and "Quiz" shortcuts per subject.

3. **Study Planner**
   - Interactive calendar week date strip (Mon - Sun).
   - Filter scheduled sessions by **All**, **Upcoming**, and **Completed**.
   - Schedule new study sessions with subject picker, start/end times, duration, session type, and priority level.
   - One-tap "Start Focus" launcher for any session.

4. **Focus Timer (Pomodoro)**
   - Functional interval countdown timer with **Focus Sprint (25m)**, **Short Break (5m)**, and **Long Break (15m)** modes.
   - Circular animated progress ring with glowing neon highlights.
   - Large digital countdown (`25:00`).
   - Start, Pause, Reset, and Skip controls.
   - Deep work cycle tracking ("Sprint 1 of 4").
   - Automatically credits study minutes to the database, updates the daily velocity, and celebrates with an interval completion dialog.

5. **AI Quiz Generator**
   - Built-in AI question generation engine.
   - Pre-loaded with topics like **Attention Layers & Transformers**, **Raft Consensus**, **LL(1) Parsers**, and procedural generation for custom topics.
   - Configurable question counts (5 or 10) and difficulty levels (Beginner, Intermediate, Advanced).
   - Live multiple-choice exam interface with instant feedback and answer explanations.
   - Detailed score card with XP rewards, review explanations, and persistent analytics history.

6. **Study Analytics & Progress Charts**
   - KPI metrics: Today's study time, active streak, and overall quiz accuracy.
   - **Weekly Study Velocity Bar Chart**: Native Jetpack Compose Canvas chart comparing daily study hours with the target baseline.
   - **14-Day Streak Heatmap**: Visual streak activity dots with flame indicators.
   - **Subject Distribution**: Color-coded progress bars tracking time spent across courses.
   - **Quiz History Log**: Log of previous quiz scores and accuracy.

7. **Student Profile & Study Goals**
   - User profile: Alex Chen, CS Semester 7.
   - Customizable daily target hours (e.g., 4.5h) and weekly study targets (e.g., 25h).
   - Pomodoro interval duration preferences (Focus, Short Break, Long Break).
   - Achievement Badges ("Streak Flame", "Deep Worker", "Quiz Master").
   - Data reset and sample student data restoration.

---

## 🛠️ Tech Stack & Architecture

- **Language**: Kotlin 2.2+
- **UI Toolkit**: Jetpack Compose (Material 3)
- **Navigation**: Navigation Compose
- **Design System**: Obsidian Kinetic (`#0B0C10` Canvas, `#121317` Surface, `#1F1F24` Containers, `#2A2C3F` Hairline Borders, `#4D8EFF` Electric Blue, `#4EDEA3` Emerald Green, `#D0BCFF` Soft Lavender)
- **Typography**: Clean Geometric Sans Headers + Monospaced technical labels (`FontFamily.Monospace`)
- **Architecture Pattern**: MVVM + Repository pattern with reactive `StateFlow`
- **Data Persistence**: SQLite Database via `Plan2LearnDatabaseHelper` with ACID tables for subjects, sessions, quizzes, and user profiles.

---

## 🚀 How to Run the Project in Android Studio

### Option 1: Open existing project in Android Studio
1. Launch **Android Studio**.
2. Select **Open** and choose either:
   - `e:\stitch_plan2learn_smart_study_planner\Plan2Learn`
   - or `C:\Users\Dell\AndroidStudioProjects\Plan2Learn`
3. Wait for Android Studio to sync Gradle (Gradle 9.6 + AGP 9.4.1).
4. Select your connected Android device or Emulator (Android 7.0+ / API 24+).
5. Click **Run** (`Shift + F10` or the green Play button).

### Option 2: Build and Generate APK via Command Line
Run the included Gradle wrapper from the terminal:

```powershell
# Set Java to Android Studio JBR
$env:JAVA_HOME = "C:\Program Files\Android\Android Studio\jbr"

# Navigate to project directory
cd "e:\stitch_plan2learn_smart_study_planner\Plan2Learn"

# Assemble Debug APK
.\gradlew.bat :app:assembleDebug
```

The compiled APK will be located at:
`app\build\outputs\apk\debug\app-debug.apk`

---

## 📦 Ready-to-Install APK

A compiled debug APK is ready for installation:
- Root workspace: `e:\stitch_plan2learn_smart_study_planner\app-debug.apk`
- Project folder: `e:\stitch_plan2learn_smart_study_planner\Plan2Learn\app-debug.apk`

To install on a device via ADB:
```powershell
adb install -r "e:\stitch_plan2learn_smart_study_planner\app-debug.apk"
```
