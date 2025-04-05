# Flutter Project Architecture

This document outlines the architecture for a Flutter project, inspired by the `swift-frontend` project structure and the `client-sdk-flutter-main\lib` directory.

## Project Structure

```mermaid
graph LR
  root[Root Directory]
  root --> config["Config (e.g., .dart_tool, analysis_options.yaml)"]
  root --> scripts["Scripts (e.g., delete_app.sh/bat)"]
  root --> lib["lib/ (Main Dart code)"]
  lib --> main_dart[livekit_client.dart (SDK entrypoint)]
  lib --> main_web_dart[livekit_client_web.dart (Web implementation)]
  lib --> src["src/ (SDK source code)"]
  root --> example["example/ (Example Flutter app using the SDK)"]
  root --> test["test/ (Tests)"]
  root --> ios["ios/ (iOS platform code)"]
  root --> android["android/ (Android platform code)"]
  root --> web["web/ (Web platform code)"]
  root --> macos["macos/ (MacOS platform code)"]
  root --> linux["linux/ (Linux platform code)"]
  root --> windows["windows/ (Windows platform code)"]
  root --> integration_test["integration_test/ (Integration Tests)"]
```

## Explanation

*   **Root Directory:** The main project directory.
*   **Config:** Contains configuration files like `.dart_tool`, `analysis_options.yaml`, etc.
*   **Scripts:** Contains scripts for tasks like deleting the app, running tests, etc. (similar to `delete_flutter_app.bat`).
*   **lib/:** Contains the main Dart code for the Flutter SDK.
    *   `livekit_client.dart`: The main entry point for the SDK, exporting all the necessary modules.
    *   `livekit_client_web.dart`: The web-specific implementation of the SDK.
    *   `src/`: Contains the source code, organized into modules like `core`, `participant`, `track`, etc.
*   **example/:** A Flutter application that demonstrates how to use the SDK.
*   **test/:** Unit tests for the SDK.
*   **ios/, android/, web/, macos/, linux/, windows/:** Platform-specific code for each supported platform.
*   **integration_test/:** Integration tests for the SDK.

## Key Components and Considerations

*   **SDK Core (lib/src):** This is where the main logic of the SDK resides. It should be well-structured and modular, with clear separation of concerns.
*   **Platform Implementations:** The `ios/`, `android/`, `web/`, etc. directories contain the platform-specific code required to integrate with each platform.
*   **Example App:** The `example/` app is crucial for demonstrating how to use the SDK and for testing its functionality.
*   **Testing:** Comprehensive unit and integration tests are essential for ensuring the quality and stability of the SDK.
*   **Configuration:** Use configuration files (e.g., `analysis_options.yaml`) to enforce code style and analysis rules.
*   **Scripts:** Use scripts to automate common tasks like building, testing, and deploying the SDK.