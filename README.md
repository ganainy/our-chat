# Our Chat

A modern Android chat application with real-time messaging, push notifications, and support for audio messages, image sharing, and file sharing. Built with Kotlin and following MVVM architecture patterns.

## Setup Instructions

### Prerequisites
- Android Studio Hedgehog (2023.1.1) or later
- JDK 17 or later
- Android SDK 34
- Firebase project
- Facebook Developer account (for Facebook login)

### Configuration

#### 1. Firebase Setup
1. Create a Firebase project at [Firebase Console](https://console.firebase.google.com/)
2. Add an Android app to your Firebase project
3. Download the `google-services.json` file
4. Place `google-services.json` in the `app/` directory
5. **Configure Firestore Security Rules**:
   - Go to Firebase Console > Firestore Database > Rules
   - Deploy the security rules from `firestore.rules` file in this project
   - The rules allow authenticated users to:
     - Read any user document
     - Create/update/delete their own user document
     - Read/create/update/delete messages they are part of
   - **Important**: Without proper security rules, the app will crash with permission errors

#### 2. Facebook Login Setup
1. Create a Facebook app at [Facebook Developers](https://developers.facebook.com/)
2. Add Facebook Login product
3. Update the following in `app/src/main/res/values/strings.xml`:
   - `facebook_app_id` - Your Facebook App ID
   - `facebook_client_token` - Your Facebook Client Token
   - `fb_login_protocol_scheme` - Format: `fb{YOUR_APP_ID}`

#### 3. Secret Files
The following files are excluded from version control and must be provided by each developer:
- `app/google-services.json` - Firebase configuration file
- Any keystore files (`.keystore`, `.jks`) - For signing release builds
- `local.properties` - Local SDK paths (auto-generated)

**Important**: Never commit secret files to version control. These files contain sensitive credentials and should remain private.

### Building the Project

1. Clone the repository
2. Open the project in Android Studio
3. Sync Gradle files
4. Ensure all prerequisites are met
5. Add `google-services.json` to the `app/` directory
6. Configure Facebook login credentials in `app/src/main/res/values/strings.xml`
7. Build and run the project




## Technology Stack

### Core Technologies
- **Kotlin 2.0.21** - Modern programming language with latest features
- **Java 17** - Target and source compatibility
- **Android SDK 34** - Latest Android API level
- **Gradle 8.2.2** - Modern build system

### Architecture & Design Patterns
- **MVVM (Model-View-ViewModel)** - Clean architecture pattern
- **Single Activity Architecture** - Multiple fragments with Navigation Component
- **ViewBinding & DataBinding** - Type-safe view references and declarative layouts
- **Lifecycle-Aware Components** - AndroidX Lifecycle 2.7.0

### Libraries & Frameworks
- **AndroidX Navigation 2.7.7** - Type-safe navigation with Safe Args
- **Material Design Components 1.11.0** - Modern Material 3 UI components
- **AndroidX Lifecycle 2.7.0** - ViewModel, LiveData, and lifecycle management
- **Glide 4.16.0** - Image loading and caching
- **EventBus 3.3.1** - Event-driven communication
- **Gson 2.10.1** - JSON serialization
- **Dexter 6.2.3** - Runtime permissions handling

### Firebase Services
- **Firebase Authentication** - Email/password and Facebook login
- **Cloud Firestore** - Real-time NoSQL database
- **Firebase Storage** - File and media storage
- **Firebase Cloud Messaging (FCM)** - Push notifications
- **Firebase Analytics** - User analytics and insights
- **Firebase Crashlytics** - Crash reporting and monitoring
- **Firebase BoM 32.8.0** - Dependency version management

### Android System Services
- **Download Manager** - File downloads
- **Media Recorder** - Audio recording
- **Notification Manager** - Push notifications

## Features

### Authentication
Sign up and login with email/password or Facebook account
  <img src="app-preview/Screenshot_20251123_142543.png" width="200" height="400">
 <img src="app-preview/Screenshot_20251123_142642.png" width="200" height="400"><br>
  

### Chat Management
Real-time chat previews on the home screen
<img src="app-preview/Screenshot_20251123_142720.png" width="200" height="400" ><br>


### Profile Management
Update profile information and pictures from camera or gallery
<img src="app-preview/Screenshot_20251123_150958.png" width="200" height="400" ><br>

### User Discovery
Search for users and send friend requests to start chatting
<img src="app-preview/Screenshot_20251123_153355.png" width="200" height="400" ><br>
<img src="app-preview/Screenshot_20251123_153534.png" width="200" height="400" ><br>


### Messaging
Type messages, record audio messages, send files and images with full-screen viewing and pinch-to-zoom support
<img src="app-preview/Screenshot_20251123_153534.png" width="200" height="400" ><br>


### Notifications
Receive real-time notifications for friend requests
<img src="app-preview/Screenshot_20251123_153355.png" width="800" height="40" ><br>

### Background Notifications
Receive push notifications even when the app is closed
<img src="app-preview/Screenshot_20251123_142720.png" width="200" height="400" ><br>

## Project Structure

```
app/src/main/java/com/ganainy/ourchat/
├── data/
│   └── model/          # Data models (User, Message, ChatParticipant, etc.)
├── service/             # Background services (FCM, etc.)
├── ui/                  # UI components organized by feature
│   ├── chat/           # Chat functionality
│   ├── contacts/       # Contacts management
│   ├── findUser/       # User search and discovery
│   ├── home/           # Home screen with chat previews
│   ├── login/          # Authentication
│   ├── profile/        # User profile management
│   └── ...
└── Utils/              # Utility classes and helpers
```

## Minimum Requirements

- **Minimum SDK**: 23 (Android 6.0 Marshmallow)
- **Target SDK**: 34 (Android 14)
- **Compile SDK**: 34

