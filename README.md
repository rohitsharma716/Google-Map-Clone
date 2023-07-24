# Mapbox Integration for Shortest Path and Directions

## Introduction
This is a ReadMe file for the Mapbox integration in our app. The purpose of this integration is to allow users to search for the shortest path between two locations using different types of transportation (e.g., walking, driving, cycling) and to display turn-by-turn directions for the chosen route.

## Features
- **Shortest Path**: Users can input two locations (starting point and destination) and select the type of transportation they prefer (walking, driving, cycling). The app will then use the Mapbox API to calculate the shortest path between the specified locations based on the chosen transportation type.

- **Directions**: After selecting the type of transportation and finding the shortest path, the app will display detailed turn-by-turn directions for the chosen route. This will help users navigate easily from the starting point to the destination.

## Prerequisites
Before using this feature in the app, you need to have the following:

1. **Mapbox API Access Token**: You must have a valid Mapbox API access token. This token is required to access Mapbox services, including routing and directions. Make sure the access token is properly configured to allow access to the required APIs.

2. **App Permissions**: Ensure that the app has the necessary permissions to access the user's current location (if needed) and to use the internet for making API requests.

## Installation
To integrate Mapbox in the app, follow these steps:

1. Obtain a Mapbox API access token from the Mapbox Dashboard. Make sure you enable the necessary APIs, including Directions API.

2. Add the Mapbox SDK to your app's build.gradle file:

```gradle
dependencies {
    implementation 'com.mapbox.mapboxsdk:mapbox-android-sdk:9.7.2'
    implementation 'com.mapbox.mapboxsdk:mapbox-android-navigation:0.42.6'
}
```

3. In the AndroidManifest.xml file, add the required permissions and meta-data for the Mapbox API access token:

```xml
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />

<application>
    <!-- Add the following meta-data tag within the application tag -->
    <meta-data
        android:name="com.mapbox.token"
        android:value="YOUR_MAPBOX_API_ACCESS_TOKEN" />
</application>
```

Replace `YOUR_MAPBOX_API_ACCESS_TOKEN` with your actual access token.

4. Implement the necessary functionality in your app to allow users to input the starting and destination locations and select the transportation type (walking, driving, cycling). When the user initiates the search, make an API request to Mapbox with the specified parameters and handle the response to display the shortest path and directions.

## Usage
1. Launch the app and grant necessary permissions (if any) to access the user's location.

2. In the app's main screen, users can find a search bar where they can input the starting location and destination. They can also find options to choose the type of transportation (e.g., walking, driving, cycling).

3. After providing the required information, users can tap the "Search" or "Find Route" button.

4. The app will use the Mapbox API to calculate the shortest path based on the provided parameters.

5. Once the shortest path is calculated, the app will display a map with the route drawn between the starting and destination points. It will also show turn-by-turn directions for the selected transportation type.

6. Users can follow the directions to navigate from the starting point to the destination efficiently.

## Troubleshooting
- If the map is not displaying or the directions are not shown, ensure that you have entered the correct Mapbox API access token in the AndroidManifest.xml file.

- Double-check the access token's configuration in the Mapbox Dashboard to ensure that the required APIs (Directions API) are enabled.

- If you encounter any issues related to the Mapbox API, refer to the official Mapbox documentation for troubleshooting and support.

## Note
Mapbox API usage might have associated costs, depending on the number of requests and usage. Make sure to review the pricing details on the Mapbox website and implement necessary measures to limit excessive API usage.

## Conclusion
With the Mapbox integration in our app, users can easily find the shortest path between two locations using different types of transportation and get detailed turn-by-turn directions. This feature enhances the app's usability and provides users with a seamless navigation experience.