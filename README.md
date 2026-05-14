# 2026 FYP Project

## Getting Started
Initial Installation Instructions

    1. Prerequisites
1.1. 	System Requirements
LinkSentry consists of an Android mobile application and a backend server. Ensure the following minimum requirements are met before proceeding:
            * Android device running Android 8.0 (API Level 26) or higher
            * Active internet connection (LTE/4G or better recommended for optimal scan performance)
            * Backend server running Linux, macOS, or Windows with WSL2
            * Minimum 2 GB RAM and 1 GB free disk space on the backend server

1.2.		Backend Prerequisites
The following software must be installed on the backend server:
            * Python 3.9 or higher
            * pip (Python package manager)
            * PostgreSQL 13+ or MySQL 8+ (relational database)
            * Redis (in-memory caching store)
            * Git

1.3.		Frontend Prerequisites
The following tools are required to build and deploy the Android application:
            * Android Studio (latest stable release)
            * Android SDK targeting API Level 26 minimum, aligned to the latest stable Android release
            * Java Development Kit (JDK) 11 or higher
            * Gradle (bundled with Android Studio)
            * Physical Android device or emulator running Android 8.0 or above


    2. Backend Setup

In order to get the backend running for the LinkSentry app, follow these steps:
        1. Install Required Software:
            * Ensure you have Flutter installed (for backend-related tasks like integration).
            * Set up Firebase for backend services such as authentication, database (Firestore), and cloud functions.
            * Install necessary dependencies for Cloud Functions (if used).
            * Make sure your Node.js environment is set up (for Firebase Functions or any custom server-related logic).
        2. Firebase Setup:
            * Create a Firebase project in the Firebase Console.
            * Enable Firebase Authentication, Firestore Database, and Cloud Functions in your Firebase Console.
            * Download the google-services.json or GoogleService-Info.plist and place it in your Flutter project (for Android/iOS respectively).
        3. Dependencies:
            * Run “flutter pub get” to install required packages.
            * Ensure that the “firebase_core”, “firebase_auth”, “cloud_firestore”, and “firebase_functions” are included in your “pubspec.yaml” file for backend services.
        4. Initialize Firebase:
            * In your Flutter app's main.dart, initialize Firebase with the code “Firebase.initializeApp();”

2.1.	 	Database Setup
The Firebase Firestore database is used to store user and app data in real-time. 
            1. Setting Up Firestore:
                * In the Firebase Console, go to Firestore Database and create a new database.
                * Set up collections like:
                    1. Users: Stores user data (first name, last name, email, etc)
                    2. Scans: Stores URL scan data (with scan results and metadata)
            2. Firestore rules:
                * Set the security rules to control access to the Firestore database as we only want to allow authenticated users to access the database.
            3. Adding Data:
                * When a user registers or  logs in, data can be stored in the “users” collections.

2.2.		Backend Environment Variables
Ensure that all the necessary environment variables are stored securely for use in backend services such as Firebase or any custom backend logic.
            1. Storing Firebase Credentials:
                * For Firebase, credentials are stored automatically in “google-services.json” or “GoogleService-Info.plist”. These files contain necessary configuration data.
                * For Cloud Functions or any server, environment variables like API keys can be stored securely using the Firebase CLI.
            2. Sensitive Data:
                * Do not hardcode sensitive data like API keys directly into the codebase.
                * Store them in “.env” files for development and use environment variable management tools in production.

2.3.		Running the Backend Server
When running Firebase Functions:
            1. Set up the Firebase CLI
                1. Install Firebase CLI 
                2. Log in with Google account
            2. Initialise the Firebase Functions:
                1. Set up the required fuels for Firebase Cloud Functions using “firebase init functions”
            3. Deploying Functions
                1. After setting up the functions, deploy them to firebase
            4. Local Testing
                1. Test the Firebase Functions locally before deploying


    3. Frontend Setup
The frontend of the app is developed using Flutter and works cross-platform on both operating systems (IOS and android).
            1. Install Flutter SDK
                * Install Flutter SDK from Flutter's official site and add it into your system’s PATH to run commands such as flutter doctor which will assist you in setting up the Flutter environment.
            2. Create a Flutter Project
                * Initialise the flutter project and open it in your preferred IDE for example VS Code or Android Studio.
            3. Add Firebase Dependencies
                * Add in your needed Firebase dependencies and run “flutter pub get” to install the specified dependencies.
            4. Configure Firebase in Flutter
                * Initialise Firebase in the main dart code file in order to access Firebase

3.1		Frontend Environment Variables
API Key and configurations:
                * For environment-specific configurations, creating a “.env” file and loading it with libraries like “flutter_dotenv”.
