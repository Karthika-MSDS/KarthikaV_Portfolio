# Open Weather – Your Daily Dose of Weather Wisdom

**Author:** Karthika Vellingiri  
**Date Created:** 25 Feb 2024  
**Program Requirement:** Interact with OpenWeatherMap API to retrieve current weather details for a given ZIP code or city.

---

## 📌 Project Overview

This Python application allows users to **fetch real-time weather data** for locations in the United States by either ZIP code or city name. The project interacts with the OpenWeatherMap API to provide current weather conditions, temperature, wind, humidity, and more, with an option to display data in **Celsius, Fahrenheit, or Kelvin**.

The application handles exceptions gracefully, ensuring robust and smooth user interaction even in case of connection errors, invalid inputs, or API issues.

---

## 🛠 Features

- **Multiple Input Options:** Lookup weather by ZIP code or city name + state.  
- **Real-Time API Data:** Uses OpenWeatherMap API to fetch accurate weather information.  
- **Unit Preferences:** Users can choose to view temperatures in Celsius, Fahrenheit, or Kelvin.  
- **Enhanced Output:** Displays weather icons, temperature ranges, wind speed, humidity, cloud cover, and descriptive conditions.  
- **Error Handling:** Catches API, connection, timeout, and input validation errors.  
- **Interactive CLI:** Command-line interface with clear prompts and instructions.  

---

## 🧰 Technical Tools

- **Programming Language:** Python 3.7+  
- **Libraries/Modules:**
  - `requests` – For API calls
  - `zipcodes` – For validating US ZIP codes
  - `json` – Parsing API responses
  - `datetime` – Handling date/time if needed
  - `re` – Regex for input validation
- **API Used:** [OpenWeatherMap API](https://openweathermap.org/api)  
- **IDE/Environment:** Jupyter Notebook, VS Code, PyCharm, or any Python-compatible IDE  
- **OS Compatibility:** Windows, macOS, Linux  

---

## ⚡ Functionalities

1. **Input Handling**
   - ZIP code search with format validation (`12345` or `12345-6789`).
   - City + State search with alphabet-only validation.
   - Exit option for graceful termination.

2. **Coordinate Retrieval**
   - Uses OpenWeatherMap Geocoding API to fetch latitude and longitude for a location.
   - Handles SSL, connection, timeout, HTTP, JSON parsing, and unexpected exceptions.

3. **Weather Retrieval**
   - Fetches current weather data including temperature, feels like, min/max temperature, humidity, pressure, wind speed, cloud coverage, and descriptive status.
   - Offers unit conversion: metric (°C), imperial (°F), and standard (K).

4. **Output Formatting**
   - Displays results in a **user-friendly, color-coded terminal output** with weather icons.
   - Highlights key details with Unicode icons for better readability.

5. **Error Validation**
   - Ensures ZIP codes are real using the `zipcodes` library.
   - Regex-based input validation for ZIP, city, and state.
   - Gracefully handles invalid or missing API responses.

---

## 💻 Requirements

- Python 3.7 or higher
- Libraries:
  - `requests`
  - `zipcodes`
  - `json`
  - `datetime`
  - `re`
- Access to the **OpenWeatherMap API** (API key required, free tier available).

Install dependencies using pip:

```bash
pip install requests zipcodes
````
---

## 🚀 How to Run

1. Clone the repository:

```bash
git clone <repository-url>
```

2. Install required libraries:

```bash
pip install -r requirements.txt
```

3. Run the application:

```bash
python main.py
```

4. Follow the CLI prompts:

   * Enter `Z` for ZIP code search or `C` for city search.
   * Input the ZIP or City + State as requested.
   * Select your preferred temperature unit.
   * View real-time weather details with formatted output.

---

## 🖼 Example Output

```text
Current Weather status of New York, US is:
☀️       Current Temperature :  25°C
☀️       Feels Like           :  24°C
↑        High Temperature      :  28°C
↓        Low Temperature       :  21°C
💨       Wind Speed            :  5 meter/sec
📈       Pressure              :  1013 hPa
💧       Humidity              :  60%
☁️       Cloud Cover           :  20%
☀️       Description           :  clear sky
```

---

## ⚠️ Notes

* Ensure an active internet connection for API calls.
* The API key is hardcoded in the script; for security, consider using environment variables.
* Only **US locations** are currently supported.
* Handles invalid or empty API responses gracefully.

---

## 🔗 References

* [OpenWeatherMap API Documentation](https://openweathermap.org/api)
* [Python Requests Library](https://docs.python-requests.org/)
* [Zipcodes Python Library](https://pypi.org/project/zipcodes/)

---

## 🛡 Error Handling Highlights

The application covers:

* SSL certificate issues
* Connection errors
* Timeout errors
* HTTP errors
* JSON parsing exceptions
* Keyboard interrupts

This ensures a **robust CLI experience** for users.

---

## 📝 Author

Karthika Vellingiri
