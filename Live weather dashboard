<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>IBM Live Weather Dashboard</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: "Segoe UI", Arial, sans-serif;
    }

    body {
      background: linear-gradient(135deg, #1f3c88, #2e86de);
      color: white;
      display: flex;
      flex-direction: column;
      align-items: center;
      min-height: 100vh;
      justify-content: center;
    }

    .container {
      text-align: center;
      background: rgba(255, 255, 255, 0.1);
      padding: 30px 40px;
      border-radius: 20px;
      box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
      width: 300px;
    }

    .search-box {
      margin-bottom: 20px;
    }

    .search-box input {
      padding: 10px 15px;
      width: 180px;
      border: none;
      border-radius: 8px;
      outline: none;
    }

    .search-box button {
      padding: 10px 15px;
      margin-left: 5px;
      border: none;
      border-radius: 8px;
      background: #ffcc00;
      color: #1f3c88;
      font-weight: bold;
      cursor: pointer;
      transition: 0.3s;
    }

    .search-box button:hover {
      background: #ffd633;
    }

    .weather-card {
      margin-top: 15px;
    }

    .weather-card img {
      width: 80px;
      margin: 10px 0;
    }

    footer {
      position: fixed;
      bottom: 10px;
      text-align: center;
      font-size: 14px;
    }

    footer a {
      color: #ffd633;
      text-decoration: none;
    }
  </style>
</head>
<body>
  <div class="container">
    <h2>🌦 IBM Live Weather Dashboard</h2>
    <div class="search-box">
      <input type="text" id="city-input" placeholder="Enter city name..." />
      <button id="search-btn">Search</button>
    </div>
    <div class="weather-card">
      <h3 id="city-name">--</h3>
      <img id="weather-icon" src="" alt="" />
      <p id="description">--</p>
      <h3 id="temperature">-- °C</h3>
      <p>Humidity: <span id="humidity">--%</span></p>
      <p>Wind: <span id="wind">-- km/h</span></p>
    </div>
  </div>

  <footer>
    <p>Powered by IBM Design • Demo Version (No API)</p>
  </footer>

  <script>
    const searchBtn = document.getElementById("search-btn");
    const cityInput = document.getElementById("city-input");

    // Sample demo data for cities
    const demoWeather = {
      "chennai": { temp: 32, desc: "sunny", humidity: 60, wind: 10, icon: "01d" },
      "mumbai": { temp: 29, desc: "cloudy", humidity: 75, wind: 15, icon: "03d" },
      "delhi": { temp: 27, desc: "hazy", humidity: 55, wind: 12, icon: "50d" },
      "bangalore": { temp: 24, desc: "rainy", humidity: 80, wind: 8, icon: "09d" },
      "kolkata": { temp: 30, desc: "humid", humidity: 85, wind: 14, icon: "02d" },
      "london": { temp: 18, desc: "overcast", humidity: 70, wind: 20, icon: "04d" },
    };

    // Function to display fake or demo weather
    function displayWeather(city) {
      const cityKey = city.toLowerCase();
      const data = demoWeather[cityKey] || generateRandomWeather(city);

      document.getElementById("city-name").textContent = city;
      document.getElementById("temperature").textContent = `${data.temp} °C`;
      document.getElementById("description").textContent = data.desc;
      document.getElementById("humidity").textContent = `${data.humidity}%`;
      document.getElementById("wind").textContent = `${data.wind} km/h`;
      document.getElementById("weather-icon").src =
        `https://openweathermap.org/img/wn/${data.icon}@2x.png`;
    }

    // Generate random weather for unknown cities
    function generateRandomWeather(city) {
      const conditions = [
        { desc: "sunny", icon: "01d" },
        { desc: "cloudy", icon: "03d" },
        { desc: "rainy", icon: "09d" },
        { desc: "stormy", icon: "11d" },
        { desc: "foggy", icon: "50d" },
      ];
      const random = conditions[Math.floor(Math.random() * conditions.length)];
      return {
        temp: (Math.random() * 15 + 20).toFixed(1),
        desc: random.desc,
        humidity: Math.floor(Math.random() * 40 + 50),
        wind: Math.floor(Math.random() * 15 + 5),
        icon: random.icon,
      };
    }

    // Handle user search
    searchBtn.addEventListener("click", () => {
      const city = cityInput.value.trim();
      if (city) {
        displayWeather(city);
      } else {
        alert("Please enter a city name.");
      }
    });

    cityInput.addEventListener("keypress", (e) => {
      if (e.key === "Enter") searchBtn.click();
    });
  </script>
</body>
</html>
