# EagleEye

Mobile object detection application that identifies specific objects mentioned in chat using ML Kit vision capabilities.

## Overview

EagleEye is an Android application designed to perform real-time object detection and recognition. Users can specify objects through the chat interface, and the app identifies and analyzes only those specific objects in the camera feed using Google ML Kit's vision APIs.

## Features

📸 **Real-Time Object Detection**
- Live camera feed processing
- ML Kit-powered vision analysis
- Smooth performance on mobile devices

💬 **Chat-Based Object Specification**
- Specify objects to detect via chat
- Search for specific item types
- Simple, intuitive user interface

🎯 **Targeted Detection**
- Identifies only specified objects
- Filters irrelevant detections
- Focused recognition results

📱 **Android-Native Implementation**
- Built with Kotlin
- Material Design UI
- Battery-efficient processing

## Project Status

⚠️ **In Development** - This is a work-in-progress project exploring ML Kit integration for specific object detection in mobile applications.

## Prerequisites

- Android 8.0 (API level 26) or higher
- Android Studio Arctic Fox or newer
- Gradle 7.0+
- Google ML Kit dependencies

## Installation

```bash
# Clone the repository
git clone https://github.com/axilyaai/EagleEye.git

# Open in Android Studio
cd EagleEye
# File → Open → Select project directory
```

## Project Structure

```
EagleEye/
├── app/
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/com/axilyaai/eagleeye/
│   │   │   │   ├── ui/
│   │   │   │   ├── detection/
│   │   │   │   ├── chat/
│   │   │   │   └── MainActivity.kt
│   │   │   └── res/
│   │   └── test/
│   └── build.gradle
├── gradle/
├── settings.gradle
└── README.md
```

## Key Technologies

- **ML Kit Vision** - Object detection and image labeling
- **Kotlin** - Primary language
- **Android Camera2 API** - Camera integration
- **CameraX** (optional) - Simplified camera handling
- **Material Design** - UI components
- **LiveData** - Data observation
- **ViewModel** - Architecture component

## Implementation Details

### ML Kit Integration

```kotlin
val detector = MLKitObjectDetector(context)
detector.detectObject(bitmap) { results ->
    // Process detection results
    results.forEach { label ->
        // Identify specific objects
    }
}
```

### Chat-Based Object Specification

Users input object names through the chat interface:
- Example: User types "glasses" → App detects only glasses in camera feed
- Example: User types "phone" → App identifies phones

## Building the Project

```bash
# Debug build
./gradlew assembleDebug

# Release build
./gradlew assembleRelease

# Run on emulator
./gradlew installDebug
./gradlew connectedAndroidTest
```

## Current Limitations

- ⏳ Project is incomplete - exploring ML Kit capabilities
- 🔄 Chat-to-detection pipeline under development
- 📊 Limited object categories at this stage
- 🎯 Accuracy improvements needed

## Future Enhancements

- [ ] Complete chat interface implementation
- [ ] Expand object detection categories
- [ ] Improve accuracy and performance
- [ ] Add object bounding box visualization
- [ ] Implement result caching
- [ ] Add multiple object simultaneous detection
- [ ] Performance optimization for lower-end devices

## Troubleshooting

### Camera Permission Issues
```
Make sure to request CAMERA permission in AndroidManifest.xml
and handle runtime permissions for Android 6.0+
```

### ML Kit Model Loading
```
Ensure Google Play Services is up to date
Check that ML Kit dependencies are correctly added to build.gradle
```

### Performance Issues
```
Reduce camera resolution
Limit detection frequency
Process on background thread
```

## Contributing

We welcome contributions! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## Code Style

- Follow Kotlin conventions
- Use meaningful variable names
- Add comments for complex logic
- Write meaningful commit messages

## Testing

```bash
# Run unit tests
./gradlew test

# Run instrumented tests
./gradlew connectedAndroidTest

# Run specific test class
./gradlew testDebugUnitTest --tests com.axilyaai.eagleeye.detection.*
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Google ML Kit for vision APIs
- Android development community
- Built with assistance from Claude AI
- Inspired by computer vision applications

---

**Made with ❤️ by Ali Sefa AKKAŞ and Claude**

[⬆ Back to top](#eagleeye)
