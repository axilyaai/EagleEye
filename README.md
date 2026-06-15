# EagleEye

> ⚠️ **This project is discontinued.**
> EagleEye was an early experiment in on-device object detection for Android.
> Development stopped when ML Kit proved too limited for the intended use case.
> The project evolved into **[IronVision](https://github.com/axilyaai/IronVision)**,
> which takes a different approach (server-side YOLOv8 instead of on-device ML Kit).
>
> The code is kept here as a reference and as part of the development history.

---

## What it was

EagleEye was an Android app that combined a live camera feed with object detection and a voice/text command interface. The goal: point your phone at a scene, type or say something like *"find the notebook"*, and have the app highlight matching objects on screen — entirely offline, no server required.

## What got built

- **Live camera preview** with CameraX
- **On-device object detection** via Google ML Kit
- **Voice input** using Android's built-in `SpeechRecognizer`
- **Offline keyword parser** (`KeywordParser`) — maps natural language phrases to COCO object categories without any LLM or internet connection
- **Detection overlay** drawing bounding boxes with corner markers around recognized objects
- MVVM architecture with Hilt for dependency injection

## Why it stopped

ML Kit's on-device object detector returns only broad category labels like *"Home good"* or *"Fashion good"* — not specific object names. This made the core feature (finding a specific object by name) impractical. Rather than integrating a heavier on-device model, the project was redirected toward a PC-assisted approach where a proper YOLOv8 model runs on the computer and streams results to the phone. That became IronVision.

## Tech stack

| Layer | Technology |
|---|---|
| Language | Kotlin |
| UI | Jetpack Compose, Material 3 |
| Camera | CameraX |
| Detection | Google ML Kit (Object Detection) |
| Voice input | Android SpeechRecognizer |
| DI | Hilt |
| Architecture | MVVM |

## Building it

```bash
git clone https://github.com/axilyaai/EagleEye.git
cd EagleEye
./gradlew assembleDebug
```

Open in Android Studio and run on a device with Android 8.0+ (API 26).
Grant camera and microphone permissions on first launch.

---

