# mobile-qa-framework
Framework for native application testing for andriod using Espresso and iOS XCUITest

This repository is a **cross-platform mobile automation framework** designed for both Android (Espresso) and iOS (XCUITest) testing. It provides a unified structure for executing mobile tests, integrating them into CI/CD pipelines, and generating test reports.

## Table of Contents
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Project Structure](#project-structure)
- [How to Run Tests Locally](#how-to-run-tests-locally)
- [CI/CD with GitHub Actions](#cicd-with-github-actions)
- [Contribution Guidelines](#contribution-guidelines)
- [License](#license)

---

## Prerequisites

### For Android Tests:
- Android Studio (latest stable)
- Android SDK & Emulator (API level 30+ recommended)
- JDK 17+
- Gradle (wrapper included)

### For iOS Tests:
- macOS with Xcode 15+
- iOS Simulator (e.g., iPhone 14)
- CocoaPods (if dependencies are used)

### Common Tools:
- Git
- GitHub account
- Shell/bash for scripts

---

## Installation

### 1. Clone the repository:
```bash
git clone https://github.com/adhikarinabin349/mobile-qa-framework.git
cd mobile-qa-framework
```

### 2. Android Setup:
```bash
cd android-tests
./gradlew clean build
```
- Make sure your Android Emulator is running.
- You can configure device details in your `build.gradle`.

### 3. iOS Setup:
```bash
cd ios-tests
open MyAppUITests.xcodeproj
```
- Select your testing scheme and simulator in Xcode.
- If using CocoaPods, run `pod install`.

### 4. Make Shell Scripts Executable:
```bash
cd scripts
chmod +x run_tests.sh
```

---

## Project Structure
```
mobile-qa-framework/
├── android-tests/           # Android Espresso tests
├── ios-tests/               # iOS XCUITest cases
├── scripts/                 # Automation scripts
├── .github/workflows/       # GitHub Actions CI pipeline
├── README.md
```

---

## How to Run Tests Locally

### Run Android Espresso tests:
```bash
cd android-tests
./gradlew connectedAndroidTest
```

### Run iOS XCUITests:
```bash
cd ios-tests
xcodebuild test -scheme MyAppUITests -destination 'platform=iOS Simulator,name=iPhone 14'
```

### Run Both Tests Together:
```bash
cd scripts
./run_tests.sh
```

---

## CI/CD with GitHub Actions

This project includes a GitHub Actions workflow located in `.github/workflows/ci.yml`.

The workflow automatically:
- Runs on every `push` or `pull request`
- Executes Android Espresso tests
- Executes iOS XCUITests

### Trigger CI pipeline:
```bash
git push origin main
```
Monitor the CI job in your GitHub repository under the **Actions** tab.

---

## Contribution Guidelines

1. Fork the repository.
2. Create a new branch (`git checkout -b feature/my-feature`).
3. Make your changes.
4. Commit (`git commit -m 'Add new feature'`).
5. Push (`git push origin feature/my-feature`).
6. Create a Pull Request.

---

## License

This project is licensed under the MIT License.

---

### Notes:
- Make sure your simulators or emulators are up and running before executing the tests.
- For iOS testing on real devices, update your `xcodebuild` destination.
- Android tests assume default emulator settings but can be updated inside `build.gradle` or CI script.

---

Happy Testing! 🚀

