
# Weather App

This is a simple Android application that fetches and displays the current weather information for a user-specified city using the OpenWeatherMap API.

## Features

- User can input a city name to get the weather information.
- Displays temperature, weather status, sunrise and sunset times, wind speed, pressure, and humidity.
- Shows a loading spinner while fetching data.
- Displays an error message if the data cannot be fetched.

## Requirements

- Android Studio
- Android SDK
- Internet connection (for fetching weather data)
- OpenWeatherMap API key

## Setup

1. **Clone the repository:**

    ```bash
    git clone https://github.com/GaryFeng86/EEP523HW3.git
    cd weather-app
    ```

2. **Open the project in Android Studio:**

    Open Android Studio, click on `Open an existing project`, navigate to the cloned directory, and select it.

3. **Get an API key from OpenWeatherMap:**

    Sign up on [OpenWeatherMap](https://openweathermap.org/) and get your free API key.

4. **Add the API key to the project:**

    Open `MainActivity.kt` and replace the placeholder API key with your actual API key:

    ```kotlin
    val API: String = "06c921750b9a82d8f5d1294e1586276f" // Use the API key
    ```

5. **Build and run the project:**

    Click on `Run` in Android Studio or press `Shift + F10` to build and run the project on your emulator or connected device.

## Usage

1. **Enter a city name:**
    - Launch the app.
    - Enter the name of the city in the input field (e.g., "Seattle,US").
    
2. **Fetch weather data:**
    - Click on the "Get Weather" button to fetch and display the weather information for the specified city.

## Code Overview

### `MainActivity.kt`

- **Initialization:**
  - `CITY` is a variable holding the default city name.
  - `API` is a constant holding the OpenWeatherMap API key.

- **onCreate:**
  - Sets up the layout and initializes the input field and button.
  - Sets an `OnClickListener` on the button to fetch weather data for the input city.

- **weatherTask (AsyncTask):**
  - `onPreExecute`: Shows the loader and hides the main content and error message.
  - `doInBackground`: Fetches weather data from the OpenWeatherMap API.
  - `onPostExecute`: Parses the JSON response and updates the UI with the fetched data. Handles errors by displaying an error message.

### `activity_main.xml`

- **Main Layout:**
  - Contains an `EditText` for city name input and a `Button` to trigger the weather fetch.
  - Shows a `ProgressBar` while data is being fetched.
  - Displays weather information (temperature, status, sunrise, sunset, wind, pressure, humidity) in various `TextView` elements.
  - Displays an error message if the data cannot be fetched.

## Test Vedio

https://drive.google.com/file/d/1tLhAR99aaL_1TtD0z2MP0Uky5HMqOVDO/view?usp=share_link
