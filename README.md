# Weather App 🌦️

A simple **Weather Application** built using **HTML, CSS, and JavaScript** that fetches real-time weather data from the **OpenWeather API** and displays information such as temperature, humidity, wind speed, and weather conditions for any searched city.

---

## 📌 Features

* Search weather by **city name**
* Shows **temperature in Celsius**
* Displays **humidity**
* Displays **wind speed**
* Dynamic **weather icons**
* Simple and responsive UI

---

## 🛠️ Technologies Used

* **HTML** – Structure of the application
* **CSS** – Styling and layout
* **JavaScript** – Logic and API integration
* **OpenWeather API** – Fetching real-time weather data

---

## 📂 Project Structure

```
weather-app/
│
├── index.html
├── style.css
├── script.js
└── images/
    ├── clear.png
    ├── clouds.png
    ├── rain.png
    ├── drizzle.png
    └── mist.png
```

---

## ⚙️ How It Works

1. User enters a **city name** in the search box.
2. JavaScript sends a request to the **weather API** using `fetch()`.
3. The API returns weather data in **JSON format**.
4. JavaScript extracts required data such as:

   * temperature
   * humidity
   * wind speed
5. The UI updates dynamically with the weather information.

---

## 🔑 API Integration

Example API request:

```
https://api.openweathermap.org/data/2.5/weather?q=CityName&appid=YOUR_API_KEY&units=metric
```

### Parameters

* `q` → City name
* `appid` → Your API key
* `units=metric` → Temperature in Celsius

Example in JavaScript:

```javascript
const apiKey = "YOUR_API_KEY";
const apiUrl = "https://api.openweathermap.org/data/2.5/weather?units=metric&q=";

async function checkWeather(city) {
  const response = await fetch(apiUrl + city + `&appid=${apiKey}`);
  const data = await response.json();

  document.querySelector(".temp").innerHTML = data.main.temp + "°C";
  document.querySelector(".humidity").innerHTML = data.main.humidity + "%";
  document.querySelector(".wind").innerHTML = data.wind.speed + " km/h";
}
```

---

## 📚 What I Learned

### 1. Working with APIs

* How to connect a website to external services.
* Learned how APIs return **JSON data**.

### 2. Using `fetch()` in JavaScript

* Sending **HTTP requests**.
* Handling **async/await** responses.

### 3. Parsing JSON Data

* Accessing nested data like:

```
data.main.temp
data.wind.speed
```

### 4. DOM Manipulation

* Updating HTML elements dynamically using JavaScript.

### 5. Error Handling

* Handling cases when a **city is not found**.

---

## 🚀 Future Improvements

* Add **5-day weather forecast**
* Detect **user location automatically**
* Improve UI with **animations**
* Add **dark/light mode**

---

## ▶️ How to Run the Project

1. Download or clone the repository
2. Replace `YOUR_API_KEY` with your API key
3. Open `index.html` in a browser
4. Search for any city to see its weather

---

## 📷 Preview

A simple weather dashboard showing:

* Temperature
* Weather condition
* Humidity
* Wind speed

---

## 📄 License

This project is for **learning purposes**.
