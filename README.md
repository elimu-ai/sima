# Sima 🦹🏽‍♀️

Sima is an educational game developed by elimu.ai. This application is part of elimu.ai's mission to build innovative learning software that empowers out-of-school children to teach themselves basic reading📖, writing✍🏽 and math🔢 **within 6 months**.

## Build Instructions

This document provides instructions for building the Sima Android application from source.

### Prerequisites

- JDK 17
- Android SDK (with platform 15 and build-tools 30.0.3)
- Android NDK r16b
- Python 2.7 (required for Cocos2d-x scripts)
- Git
- Apache Ant

### Environment Setup

#### 1. Download and Install JDK 17
Download and install [JDK 17](https://adoptium.net/temurin/releases/?version=17) for your platform.

#### 2. Download and Install Android SDK
- Download [Android Studio](https://developer.android.com/studio) or the [command line tools](https://developer.android.com/studio#command-tools)
- Install required SDK components:
  ```bash
  sdkmanager "platforms;android-15" "build-tools;30.0.3"
