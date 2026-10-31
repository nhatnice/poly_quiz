# Bee Hero - Poly Quiz 🐝

> **A cross-platform gamified quiz application crafted for FPT Polytechnic students.**

[![Flutter](https://img.shields.io/badge/Flutter-%2302569B.svg?style=for-the-badge&logo=Flutter&logoColor=white)](https://flutter.dev)
[![Dart](https://img.shields.io/badge/Dart-%230175C2.svg?style=for-the-badge&logo=dart&logoColor=white)](https://dart.dev)
[![Platform](https://img.shields.io/badge/Platform-Android%20%7C%20iOS%20%7C%20Web%20%7C%20Desktop-lightgrey?style=for-the-badge)](https://flutter.dev/multi-platform)
[![License](https://img.shields.io/badge/License-Proprietary-blue.svg?style=for-the-badge)](LICENSE)

---

## 📱 Overview

**Bee Hero (Poly Quiz)** is an interactive, gamified quiz platform developed to enhance learning, revision, and knowledge testing for students at FPT Polytechnic. Designed with a clean, modern aesthetic and fluid animations, Bee Hero transforms standard academic quizzes into an engaging gaming experience.

### ✨ Key Features
- 🎓 **School-Exclusive Authentication:** Validates FPT Polytechnic student credentials (`@fpt.edu.vn` domain validation) to ensure authorized community participation.
- 💡 **Curated Quiz Library & "Quiz of the Day":** Categorized question sets highlighted with dynamic themed cards and vibrant banners.
- ⏱️ **Interactive Real-Time Gameplay:** Live countdown timers for each question, visual progress indicators, instant answer verification, and dynamic feedback.
- 💎 **Gamification & Reward System:** Earn Gems through correct answers and progress through competitive ranking badge tiers:
  - 💎 **Diamond Rank**
  - ❇️ **Emerald Rank**
  - 🔴 **Ruby Rank**
  - 🟡 **Gold Rank**
  - 🔷 **Sapphire Rank**
- 🎨 **Custom Lavenes UI Design System:** Google Sans Plus multi-weight typography, vector SVG badges, smooth numerical animations, and fully responsive layouts adapting seamlessly to Mobile, Tablet, and Desktop screens.

---

## 📸 Screenshots

<table border="0" cellspacing="0" cellpadding="0" align="center">
	<tr>
		<td align="center">
			<img src="https://i.imgur.com/Do6gVAq.jpeg" width="260" alt="Login & Authentication Screen" />
			<br /><em>Student Authentication</em>
		</td>
		<td align="center">
			<img src="https://i.imgur.com/XcVLeKB.jpeg" width="260" alt="Home Dashboard & Ranking" />
			<br /><em>Dashboard, Ranks & Quizzes</em>
		</td>
		<td align="center">
			<img src="https://i.imgur.com/fcTD9Dc.jpeg" width="260" alt="Quiz Gameplay & Countdown" />
			<br /><em>Interactive Countdown Gameplay</em>
		</td>
	</tr>
</table>

---

## 🛠️ Tech Stack

| Layer | Technology / Library | Purpose |
| :--- | :--- | :--- |
| **Framework** | [Flutter](https://flutter.dev) (SDK `>=2.16.1 <3.0.0`) | Cross-platform UI toolkit |
| **Language** | [Dart](https://dart.dev) | Primary programming language |
| **Networking** | `http: ^0.13.4` | RESTful API client communications |
| **Configuration** | `flutter_dotenv: ^5.0.2` | Runtime environment variable management |
| **Local Persistence** | `shared_preferences: ^2.0.13` | Session persistence and local caching |
| **Vector Graphics** | `flutter_svg: ^1.0.3` | SVG asset rendering for badges & energy icons |
| **Typography** | `GoogleSansPlus` | Premium custom font family across multiple weights |
| **Utilities** | `intl: ^0.17.0`, `url_launcher: ^6.0.20` | Internationalization & external browser dispatch |
| **Target Platforms** | Android, iOS, Web, macOS, Windows | Unified cross-platform deployment |

---

## 📂 Project Structure

```text
poly_quiz/
├── android/                    # Android native configuration and build scripts
├── assets/                     # Application visual assets
│   ├── avatars/                # Profile avatar choices (a1.png - a38.png)
│   ├── icons/                  # Rank badge SVGs (Diamond, Emerald, Ruby, Gold, Sapphire, Gems)
│   └── quiz/                   # Quiz visual vectors
├── fonts/                      # Typography assets (Google Sans Plus)
│   └── GoogleSansPlus/
├── ios/                        # iOS native configuration and schemes
├── lib/                        # Flutter core application codebase
│   ├── components/             # Reusable UI component library (Lavenes UI)
│   │   ├── animatedCount/      # Smooth number roller / rolling counter
│   │   ├── button/             # Custom styled CTA buttons
│   │   ├── cards/              # Quiz display cards (FeatureCard, DetailCard)
│   │   ├── footer/             # Copyright footer component
│   │   ├── pageTransition/     # Custom page transition routes
│   │   ├── progressBar/        # Animated question progress bar
│   │   ├── selectBox/          # Interactive multiple-choice selection box
│   │   └── textbox/            # Form input text fields
│   ├── global/                 # Global services, helper utilities & API client
│   │   ├── api.dart            # REST API client & endpoint service definitions
│   │   ├── func.dart           # Helper utilities (array shuffle, responsive helpers)
│   │   └── global.dart         # Global constants, badge calculator & ranks
│   ├── screens/                # Core application views
│   │   ├── auth/               # Sign-in & Sign-up authentication views
│   │   ├── home/               # Dashboard view (rank, gems, featured quizzes)
│   │   └── quiz/               # Quiz play view, countdown question view & result modal
│   ├── lavenes.dart            # Centralized UI component export
│   └── main.dart               # Application entry point & router configuration
├── macos/                      # macOS desktop native files
├── web/                        # Web support, PWA manifests and service worker
├── windows/                    # Windows desktop native C++ runner
├── .env.example                # Sample environment configuration template
├── .gitignore                  # Git ignore definitions
├── pubspec.yaml                # Package manifest and asset registry
└── README.md                   # Project documentation
```

---

## 🚀 Setup & Installation

### 1. Prerequisites
- [Flutter SDK](https://docs.flutter.dev/get-started/install) installed and configured in your shell path.
- Code Editor: [VS Code](https://code.visualstudio.com/) or [Android Studio](https://developer.android.com/studio) with the official Flutter & Dart extensions.
- Testing device: Android/iOS physical device, emulator, simulator, or Google Chrome.

### 2. Environment Configuration (.env)
The project utilizes `flutter_dotenv` to securely inject backend endpoints and credentials at runtime. Create a `.env` file from the provided template:

```bash
cp .env.example .env
```

Configure the environment variables in `.env`:
```env
# Backend REST API endpoint (default: http://localhost:8080)
API_URL=http://localhost:8080

# API credentials / headers
W_API_KEY=your_api_key_here
APP_ID=your_app_id_here
```

> [!IMPORTANT]
> The `.env` file is strictly ignored by version control. Never commit live production secrets or authentication keys to public repositories.

### 3. Install Dependencies
```bash
flutter pub get
```

### 4. Running the Application

#### On a connected Mobile device or Emulator:
```bash
flutter run
```

#### On Google Chrome (Web):
```bash
flutter run -d chrome
```

#### Running on legacy Flutter SDKs (no sound null-safety):
```bash
flutter run --no-sound-null-safety
```

### 5. Production Build

- **Android (APK):**
  ```bash
  flutter build apk --release
  ```
- **Web App (PWA):**
  ```bash
  flutter build web --release
  ```

---

## 📖 Usage Guide

1. **Sign Up / Sign In:**
   - Launch the application and enter your student name, password, and institutional email (`@fpt.edu.vn`).
   - The system validates student identity, creates an account, assigns a starter avatar, and initializes Gems.
2. **Dashboard Navigation:**
   - Review your current **Gems balance** and **Rank Badge** on the top header.
   - Explore daily featured packages under **"Quiz of the day"** and **"Feature Quizzes"**.
3. **Starting a Quiz:**
   - Tap any quiz card to review its details and description.
   - Tap **Play** to initiate the quiz session.
4. **Answering Questions:**
   - A live countdown timer is displayed for each question.
   - Select an answer option before time expires. Visual cues provide instant confirmation for correct or incorrect responses.
5. **Score & Reward Summary:**
   - Upon completing the quiz, the congratulations view tallies your performance, awards additional Gems, and updates your rank.

---

## 🔒 Security Audit & Hardening (2026)

> [!NOTE]
> Originally developed in **2022**, this repository underwent a comprehensive security review in **2026**:

- ✅ **Eliminated Hardcoded Secrets:** Stripped all legacy API keys, App IDs, and hardcoded private network IP addresses from `lib/global/api.dart`.
- ✅ **Dynamic Runtime Configuration:** Converted API URLs and authentication headers to dynamic getters backed by `flutter_dotenv` with safe fallbacks to prevent runtime null-assertion crashes.
- ✅ **Keystore & Certificate Protection:** Hardened `.gitignore` to prevent accidental commits of SSL certificates (`*.pem`, `*.key`, `*.crt`), Android keystore files (`key.properties`, `*.keystore`, `*.jks`), and local environment variables.
- ✅ **Resilient Startup Handling:** Implemented safe `try-catch` initialization in `main.dart` with `WidgetsFlutterBinding.ensureInitialized()` so the app can launch gracefully even if `.env` has not yet been populated.

---

## 👥 Credits & Contact

- **Lead Developer & Designer:** [NHΛTTRΛN](https://nhattran.dev)
- **Website:** [nhattran.dev](https://nhattran.dev)
- **Email:** [contact@nhattran.dev](mailto:contact@nhattran.dev)
- **Target Organization:** Dedicated to the **FPT Polytechnic** community
- **Copyright & License:** © 2022 Lavenes. All rights reserved.
