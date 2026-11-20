# VELORIA AI — Android AI Character Chat & Interactive Stories

**VELORIA AI** is a native Android application built with **Kotlin**, **Jetpack Compose (Material 3)**, **Room SQLite**, and **Google Gemini AI** in a dark purple and black theme.

## Included Features
- **AI Character Discovery**: 6 original anime-style characters (Aria Vance, Kaelen Voss, Meera Sen, Renjiro Takahashi, Lyra Thorne, Aarav Kapoor) with custom illustrations, search, and category/gender filters.
- **AI Character Chat**: Real Gemini API conversations with Hindi, English, and Hinglish support, animated typing indicator, persistent history, and character-specific memory.
- **Interactive AI Stories**: 6 branching stories across Romance, Fantasy, Mystery, Comedy, Adventure, and Drama with AI-generated chapters, user choices, saved progress, and multiple endings.
- **Roleplay Mode**: Preset and custom fictional scenarios with PG-13 safety guardrails.
- **Create Your Own Character**: Custom name, preset or gallery image, personality, backstory, conversation style, memory toggle, and voice pitch/speed sliders.
- **Voice Features**: Android `TextToSpeech` playback controls (with multiple voice/locale support) and `SpeechRecognizer` voice-to-text input.
- **Persistent Memory Manager**: View, approve, add, edit, and delete per-character memories.
- **Security**: API keys are stored locally using `EncryptedSharedPreferences` (AES-256) or injected at build time via `local.properties`.

## How to Build the APK

### Option 1: Android Studio (Recommended)
1. Extract `VELORIA_AI_Android.zip`.
2. Open the `VeloriaAI` folder in **Android Studio** (Ladybug or newer, JDK 17).
3. Copy `local.properties.example` to `local.properties` (or let Android Studio generate `local.properties` with your `sdk.dir`) and optionally add:
   ```properties
   GEMINI_API_KEY=your_gemini_api_key_here
   ```
   *(You can also skip this step and enter your API key directly inside the app's **Profile & Settings** screen.)*
4. Let Gradle sync finish.
5. Click **Build > Build Bundle(s) / APK(s) > Build APK(s)** (or Run directly on an emulator/device with Android 8.0+ / API 26+).
6. Locate the APK at `app/build/outputs/apk/debug/app-debug.apk`.

### Option 2: Command Line (Gradle)
```bash
cd VeloriaAI
gradle assembleDebug
```
*(If using the Gradle wrapper, run `gradle wrapper` once in Android Studio or a machine with internet access to generate `gradlew`.)*

## Free-Tier API Setup & Limitations
- Get a free API key from **Google AI Studio**: `https://aistudio.google.com/apikey`.
- **Free-tier limits**: Google Gemini's free tier (`gemini-2.0-flash` / `gemini-1.5-flash`) has per-minute (RPM) and daily (RPD) request quotas. If you exceed them, VELORIA AI displays a friendly rate-limit notice (`HTTP 429`)—simply wait 30–60 seconds before sending the next message.
- **Privacy**: All chat messages, custom characters, memories, and story progress stay on your device in Room SQLite. Your API key is encrypted with `EncryptedSharedPreferences`.

## Open-Source Stack
- **Jetpack Compose & Material 3** (Apache 2.0)
- **AndroidX Room, Navigation, Security-Crypto** (Apache 2.0)
- **OkHttp & Gson** (Apache 2.0)
- **Coil Compose** (Apache 2.0)
