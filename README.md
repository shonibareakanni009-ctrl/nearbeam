# Nearbeam

**Share your phone’s screen (and sound) to a Chromebook over Wi‑Fi.**

Nearbeam is a lightweight local cast stack for devices that can’t run modern casting protocols well — especially older Chromebooks (e.g. Samsung XE303C12 on Chrome 75).

| Piece | What it is |
|-------|------------|
| **Nearbeam Receiver** | Chrome App on the Chromebook |
| **Nearbeam Share** | Android app on the phone |

No cloud. Same Wi‑Fi network only.

---

## Why Nearbeam?

Classic Bluetooth speaker mode (phone → Chromebook as A2DP sink) is an **OS** feature. A Chrome App cannot turn the Chromebook into a real Bluetooth speaker. Nearbeam uses **Wi‑Fi** for screen frames + optional app audio instead.

---

## Quick start

### Chromebook (Receiver)
1. Load `chrome-app/` as an unpacked Chrome App (`chrome://extensions` → Developer mode).
2. Open **Nearbeam** → Power On → **Start Wi‑Fi receiver**.
3. Copy the link shown (e.g. `http://192.168.x.x:8080`).

### Phone (Share)
1. Build/install the Android APK (see below).
2. Paste the Chromebook link → choose quality (use **Low** on old machines) → **Start sharing**.
3. Allow the system screen-capture prompt.

---

## Build the Android APK

**GitHub Actions (easiest online path)**  
Actions tab → **Build Android APK** → Run workflow → download the artifact.

**Android Studio**  
Open the `android/` folder → **Build → Build APK(s)**.

**Other CI**  
[Codemagic](https://codemagic.io/), [Bitrise](https://bitrise.io/) — connect this repo and build the `android` module.

---

## Repo layout

```
nearbeam/
  chrome-app/   # Receiver (Chrome App)
  android/      # Nearbeam Share (Kotlin)
  README.md
```

Source also lives in the earlier draft repos if you need to copy folders over while this brand repo is filled out.

---

## Limits (assignment-honest)

- JPEG frame stream — laggy on 2 GB / 2012 hardware; prefer Low quality
- App audio needs Android 10+; some apps block capture
- Not Chromecast-class smoothness
- iPhone not supported in this version
