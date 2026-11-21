# New York Weather

A small Android weather app built with Jetpack Compose. It shows the current
conditions and a short forecast for New York City using the
[OpenWeatherMap](https://openweathermap.org/api) API.

## Features

- Current temperature, condition, humidity and wind for New York City
- Weather icon loaded over the network (Glide)
- Loading, empty and error states, including missing/invalid API key messages
- Material 3 theming

## Tech stack

| Layer | Library |
|-------|---------|
| UI | Jetpack Compose + Material 3 |
| State | ViewModel + `StateFlow` |
| Networking | Retrofit + Moshi + OkHttp |
| Images | Glide |
| Build | Gradle (Kotlin DSL), AGP 9.5, Kotlin 2.2 |

`minSdk` 24, `targetSdk` 37.

## Getting started

### 1. Clone the repository

```bash
git clone https://github.com/Asutilla/Weather-App.git
cd Weather-App
```

### 2. Requirements

- Android Studio (latest stable) with JDK 17+
- An OpenWeatherMap API key ([get one free](https://home.openweathermap.org/api_keys))

### 3. Configure the API key

The key is never committed. Add it to `local.properties` in the project root:

```properties
sdk.dir=C\:\\Users\\<you>\\AppData\\Local\\Android\\Sdk
OPENWEATHER_API_KEY=your-key-here
```

`local.properties` is listed in `.gitignore` and must stay out of version
control. Alternatively export `OPENWEATHER_API_KEY` as an environment variable
before building.

### 4. Build and run

```bash
# Windows
gradlew.bat assembleDebug

# macOS / Linux
./gradlew assembleDebug
```

Or open the project in Android Studio and press **Run**.

### 5. Tests

```bash
gradlew.bat test
```

## Project layout

```
app/src/main/java/com/example/newyorkweather/
├── MainActivity.kt
├── data/          # Retrofit service and response models
└── ui/            # Compose screen, theme, ViewModel and UI state
```

## Security

- API keys live in `local.properties` or the `OPENWEATHER_API_KEY` environment
  variable, never in source or in the repository.
- Never commit `local.properties`, `.env*`, or signing material — they are
  listed in `.gitignore`.
- If a key is exposed, revoke it at
  [home.openweathermap.org/api_keys](https://home.openweathermap.org/api_keys)
  and issue a new one; removing the file is not enough.

See [SECURITY.md](SECURITY.md) for the full policy, the key-rotation procedure,
and the recommended GitHub secret-scanning settings.
