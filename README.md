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

#### 3. Download Android NDK r16b

...

#### 4. Install Python 2.7

Most platforms:

```
# Check if already installed
python --version

# If not installed, download from https://www.python.org/downloads/release/python-2718/
```

#### 5. Install Apache Ant

...

### Building the Application

#### 1. Clone the repository

```
git clone https://github.com/elimu-ai/sima.git
cd sima
```

#### 2. Set up Cocos2d-x 3.10

```
# Create frameworks directory for Cocos2d-x
mkdir -p frameworks
cd frameworks

# Clone Cocos2d-x 3.10
git clone --branch cocos2d-x-3.10 https://github.com/cocos2d/cocos2d-x.git cocos2d-x-3.10
cd cocos2d-x-3.10

# Download dependencies
python download-deps.py

# Initialize submodules
git submodule update --init

cd ../..  # Return to project root
```

#### 3. Create local.properties

Create a file `proj.android/local.properties` with the following content:

```
sdk.dir=/path/to/your/android/sdk
ndk.dir=/path/to/your/android-ndk-r16b
```

#### 4. Build native code with NDK

```
# Set NDK_MODULE_PATH environment variable
# On Linux/macOS:
export NDK_MODULE_PATH=/path/to/frameworks/cocos2d-x-3.10:/path/to/frameworks/cocos2d-x-3.10/cocos:/path/to/frameworks/cocos2d-x-3.10/external

# On Windows:
# set NDK_MODULE_PATH=C:\path\to\frameworks\cocos2d-x-3.10;C:\path\to\frameworks\cocos2d-x-3.10\cocos;C:\path\to\frameworks\cocos2d-x-3.10\external

# Build native code
cd proj.android
/path/to/android-ndk-r16b/ndk-build -C jni
```

#### 5. Build the APK with Ant

```
# Still in proj.android directory
ant debug
```

The resulting APK will be located at `proj.android/bin/Kukua-debug.apk`

### Troubleshooting

...
