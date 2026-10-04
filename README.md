# 🎮 Controller for Ludo King

**A free Bluetooth controller companion for Ludo King**

Control the dice of individual Ludo players from a second Android phone using a direct Bluetooth connection.

This project is intended to provide a **free and transparent alternative to unofficial paid copies** that may be distributed through unknown sources. The source code is publicly available so users can inspect it, build it themselves, report issues, and contribute improvements.

---

## ✨ Features

### 📱 Bluetooth Controller

Use a second Android phone as a dedicated controller for the Ludo game.

- Bluetooth device discovery/selection
- Bluetooth pairing support
- Direct device-to-device communication
- Connection status
- Connect/disconnect controls
- No internet connection required for controller communication

---

### 🎲 Dice Control

The controller can determine the next dice value for a player.

Available values:

```text
1  2  3  4  5  6
```

The selected value is sent to the main Ludo King application over Bluetooth.

---

### 🎯 Individual Player Control

The controller can select which Ludo player should receive the controlled dice value.

Supported colours:

🔴 **RED**

🟢 **GREEN**

🔵 **BLUE**

🟡 **YELLOW**

For example:

```text
RED    → 6
GREEN  → 2
BLUE   → 5
YELLOW → 1
```

Values can be queued independently for different colours.

---

### 🔄 Pass & Play Integration

The controller is designed specifically around the **Pass & Play** mode.

The normal Pass & Play experience remains available on the main device.

The controller simply adds an optional Bluetooth-controlled dice mechanism.

If no controlled value is available for a player, the normal game dice behaviour continues.

This means the Bluetooth controller does not need to replace the existing Pass & Play system.

---

### 📡 Local Bluetooth Communication

The controller communicates directly with the main application through Bluetooth.

The basic architecture is:

```text
┌─────────────────────────┐
│   Main Ludo Device      │
│                         │
│      Ludo King          │
│   Bluetooth Host        │
└────────────┬────────────┘
             │
             │ Bluetooth
             │
┌────────────▼────────────┐
│    Controller Device    │
│                         │
│ Controller for          │
│ Ludo King               │
└─────────────────────────┘
```

No cloud server is required for the controller connection.

---

## 🕹️ How It Works

The system consists of two applications.

### 1. Ludo King

The main Ludo game runs on one Android device.

It handles:

- Game board
- Players
- Tokens
- Turns
- Dice
- Movement
- Existing Pass & Play functionality
- Bluetooth commands from the controller

### 2. Controller for Ludo King

The controller runs on a second Android device.

It provides:

- Bluetooth connection
- Player-colour selection
- Dice-number selection
- Command transmission
- Connection status

---

## 🎲 Example

Suppose the controller user selects:

```text
Player: RED
Dice: 6
```

The controller sends a command representing:

```text
DICE|RED|6
```

The main application receives the command and associates the value with the selected player.

When that player's controlled dice roll occurs, the queued value can be used.

If no value has been queued, the normal dice system continues.

---

# 📱 Controller UI

The controller application includes a dedicated interface for quickly controlling the game.

### Main sections

- 🎮 Application branding
- 🔗 Bluetooth connection
- 📊 Connection status
- 🔴🟢🔵🟡 Player selection
- 🎲 Dice selection
- 🔌 Disconnect control
- ℹ️ Controller/game status

The UI is designed for quick operation while the main Ludo game is running on another phone.

---

# 🔗 Getting Started

## Requirements

### Main device

- Android device
- Bluetooth support
- Compatible Ludo King application

### Controller device

- Android device
- Bluetooth support
- Controller for Ludo King

Both devices need to support Bluetooth communication.

---

## 1. Pair the Devices

Enable Bluetooth on both Android devices.

Use the Android Bluetooth settings to pair the two phones.

---

## 2. Open the Main Game

Launch **Ludo King** on the main device.

Start a compatible Pass & Play game.

---

## 3. Open the Controller

Launch:

**Controller for Ludo King**

on the second device.

---

## 4. Connect

Select the paired main-game device from the controller.

Connect to it.

The controller should indicate the connection status.

---

## 5. Control the Dice

Select a colour:

```text
🔴 RED
🟢 GREEN
🔵 BLUE
🟡 YELLOW
```

Then select a dice value:

```text
1  2  3
4  5  6
```

The selected value is transmitted to the main application.

---

# 🛠️ Building From Source

This project is an Android Studio project written in Java.

### Recommended development environment

```text
Android Studio
JDK 17
Gradle 7.5.1
Android Gradle Plugin 7.4.2
```

> **Important:** Use JDK 17 for the current project configuration.

---

## Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/Controller-for-Ludo-King.git
```

Open the project in Android Studio.

Allow Gradle to synchronize.

Make sure the Gradle JDK is configured to **JDK 17**.

Then build the project.

---

# 📂 Project Structure

```text
Controller-for-Ludo-King/
│
├── app/
│   └── src/
│       └── main/
│           ├── java/
│           ├── res/
│           └── AndroidManifest.xml
│
├── gradle/
│   └── wrapper/
│
├── build.gradle
├── settings.gradle
├── gradle.properties
└── README.md
```

---

# 🔐 Privacy

The controller is designed for local Bluetooth communication.

The controller does not require a cloud server to communicate with the main game.

The project does not require:

- ❌ User accounts
- ❌ Cloud gaming servers
- ❌ Remote control servers
- ❌ Paid subscriptions
- ❌ Internet access for the Bluetooth connection

Users can inspect the source code themselves.

---

# 🛡️ Why Is This Project Free?

There are unofficial applications and modified copies of similar functionality distributed through various sources.

Users may encounter APKs that are:

- Modified without transparency
- Distributed without source code
- Offered for money
- Hosted on unknown websites
- Difficult for users to verify

This project is being published openly so that users can access the source code and obtain the software from the project's official GitHub repository.

### Our goal

> **Free software should be transparent and accessible.**

Instead of paying an unofficial seller for an unknown APK, users can inspect the source code and build the application themselves.

---

# 🔍 Security

Because this is an open-source project, users can inspect the source code before building it.

For maximum security, users are encouraged to:

1. Clone the official repository.
2. Review the source code.
3. Build the application themselves.
4. Install the APK generated from their own build.

Do not assume that an APK downloaded from an unrelated third-party website is an official release of this project.

---

# 🐛 Reporting Bugs

If you find a problem, please open a GitHub Issue.

Include:

```text
Device:
Android Version:
Controller Version:

Problem:

Steps to reproduce:

Expected behaviour:

Actual behaviour:
```

Screenshots and relevant logs are also helpful.

---

# 💡 Feature Requests

Feature suggestions are welcome.

Before requesting a feature, please check the existing Issues to see whether it has already been proposed.

---

# 🤝 Contributing

Contributions are welcome.

You can contribute by:

- 🐛 Reporting bugs
- 💡 Suggesting features
- 🔧 Fixing issues
- 📱 Testing on different Android devices
- 🎨 Improving the UI
- 📖 Improving documentation
- 🔐 Reviewing the security of the project

Pull requests are welcome.

---

# 🙏 Special Thanks

A very special thank you to **[Vinaykpro](https://github.com/Vinaykpro)** for creating and publicly sharing the original **[Ludo_King_Clone](https://github.com/Vinaykpro/Ludo_King_Clone)** Android project.

The original project provided the **Ludo game foundation** used as the starting point for developing the Bluetooth controller functionality.

The original repository describes the project as an Android Studio/Java Ludo King clone and includes gameplay, multiplayer, customization, responsive UI, and a remote-control preview.

Please visit the original project and give credit to the original author:

👉 **https://github.com/Vinaykpro/Ludo_King_Clone**

We appreciate Vinaykpro for making the project publicly available for developers to learn from and build upon.

---

# 📜 License

Please check the repository's `LICENSE` file for the exact licensing terms.

If this project contains code or assets derived from another project, their original license and attribution requirements remain applicable.

---

# ⚠️ Disclaimer

This project is provided for educational, experimental, and interoperability purposes.

It is a Bluetooth controller companion project and does not provide an online gaming service.

Users are responsible for complying with the applicable terms, licenses, and policies of any third-party software they use this project with.

---

# ⭐ Support the Project

If this project is useful to you:

⭐ Star the repository

🐛 Report bugs

💡 Suggest improvements

🔧 Contribute code

📖 Improve the documentation

📢 Share the official repository

Most importantly, share the **official GitHub repository** rather than unofficial APK mirrors so users know where the project comes from.

---

# 🎮 Project Summary

| Feature | Status |
|---|---|
| Bluetooth Controller | ✅ |
| Bluetooth Pairing | ✅ |
| Direct Device Communication | ✅ |
| Dice Control | ✅ |
| Dice 1–6 | ✅ |
| Red Player Control | ✅ |
| Green Player Control | ✅ |
| Blue Player Control | ✅ |
| Yellow Player Control | ✅ |
| Pass & Play Integration | ✅ |
| Multiple Colour Queues | ✅ |
| Connection Status | ✅ |
| Connect / Disconnect | ✅ |
| Internet Required for Controller | ❌ |
| Cloud Server Required | ❌ |
| Free Source Code | ✅ |
| Open Development | ✅ |

---

## ❤️ Thank You

Thank you for checking out **Controller for Ludo King**.

If you find the project useful, consider giving the repository a ⭐ and contributing to its development.

**Free • Transparent • Community Driven • Bluetooth Powered**
