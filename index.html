<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Weather App</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/leaflet/1.9.4/leaflet.min.css" />
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        html, body {
            width: 100%;
            height: 100%;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            overflow: hidden;
        }
        body {
            position: relative;
            color: #fff;
        }
        #map {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 1;
        }
        .container {
            position: fixed;
            top: 0;
            left: 0;
            width: 420px;
            height: 100%;
            display: flex;
            flex-direction: column;
            z-index: 10;
            padding: 20px;
            background: rgba(0, 0, 0, 0.3);
            backdrop-filter: blur(10px);
            overflow-y: auto;
            overflow-x: hidden;
        }
        .search-box {
            display: flex;
            gap: 10px;
            margin-bottom: 20px;
            flex-direction: column;
            width: 100%;
        }
        .search-box input {
            flex: 1;
            padding: 15px 20px;
            border: none;
            border-radius: 50px;
            font-size: 16px;
            outline: none;
        }
        .search-box button {
            padding: 15px 30px;
            border: none;
            border-radius: 50px;
            background: #ff6b6b;
            color: #fff;
            font-size: 16px;
            cursor: pointer;
            transition: background 0.3s;
            font-weight: bold;
        }
        .search-box button:hover {
            background: #ee5a5a;
        }
        .search-box .favorite-btn {
            background: #4CAF50;
        }
        .search-box .favorite-btn:hover {
            background: #45a049;
        }
        .content-wrapper {
            display: flex;
            justify-content: flex-start;
            align-items: flex-start;
            width: 100%;
        }
        .current-weather {
            position: relative;
            width: 100%;
            height: 500px;
            border-radius: 30px;
            padding: 50px 30px 30px;
            text-align: center;
            backdrop-filter: blur(15px);
            background: rgba(0, 0, 0, 0.3);
            box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.37);
            border: 1px solid rgba(255, 255, 255, 0.18);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            overflow: hidden;
            flex-shrink: 0;
        }
        
        /* Weather simulation container */
        .weather-simulation {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            border-radius: 30px;
            pointer-events: none;
            overflow: hidden;
        }

        /* Rain animation */
        .rain {
            position: absolute;
            width: 100%;
            height: 100%;
            background: 
                repeating-linear-gradient(90deg, 
                    transparent, 
                    transparent 2px, 
                    rgba(255, 255, 255, 0.3) 2px, 
                    rgba(255, 255, 255, 0.3) 4px);
            animation: rainFall 0.5s linear infinite;
        }
        @keyframes rainFall {
            0% { transform: translateY(-100%); }
            100% { transform: translateY(100%); }
        }

        /* Sun animation */
        .sun {
            position: absolute;
            width: 150px;
            height: 150px;
            background: radial-gradient(circle, #FFD700, #FFA500);
            border-radius: 50%;
            top: 20px;
            right: 20px;
            box-shadow: 0 0 60px rgba(255, 215, 0, 0.8);
            animation: sunGlow 3s ease-in-out infinite;
        }
        @keyframes sunGlow {
            0%, 100% { box-shadow: 0 0 60px rgba(255, 215, 0, 0.8); }
            50% { box-shadow: 0 0 80px rgba(255, 215, 0, 1); }
        }

        /* Clouds animation */
        .cloud {
            position: absolute;
            width: 60px;
            height: 30px;
            background: rgba(255, 255, 255, 0.7);
            border-radius: 30px;
            animation: cloudMove 15s linear infinite;
        }
        .cloud::before {
            content: '';
            position: absolute;
            width: 35px;
            height: 35px;
            background: rgba(255, 255, 255, 0.7);
            border-radius: 50%;
            top: -17px;
            left: 10px;
        }
        .cloud::after {
            content: '';
            position: absolute;
            width: 30px;
            height: 30px;
            background: rgba(255, 255, 255, 0.7);
            border-radius: 50%;
            top: -15px;
            right: 10px;
        }
        @keyframes cloudMove {
            0% { transform: translateX(-200px); }
            100% { transform: translateX(100vw); }
        }

        /* Snow animation */
        .snowflake {
            position: absolute;
            color: white;
            font-size: 1.5em;
            animation: snowFall 10s linear infinite;
        }
        @keyframes snowFall {
            0% { 
                transform: translateY(-10px) translateX(0);
                opacity: 1;
            }
            100% { 
                transform: translateY(500px) translateX(100px);
                opacity: 0;
            }
        }

        /* Content overlay */
        .weather-content {
            position: relative;
            z-index: 5;
        }

        .weather-content h2 {
            font-size: 36px;
            margin-bottom: 20px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
        }

        .temp-display {
            font-size: 80px;
            font-weight: bold;
            margin: 20px 0;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
        }

        .emoji {
            font-size: 60px;
            margin-bottom: 10px;
        }

        .weather-content .desc {
            font-size: 24px;
            margin: 15px 0;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
        }

        .weather-content .date {
            font-size: 14px;
            opacity: 0.8;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
        }

        .forecast-title {
            font-size: 24px;
            margin-top: 30px;
            margin-bottom: 20px;
            text-align: center;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
            width: 100%;
            flex-shrink: 0;
        }

        .forecast-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 15px;
            padding: 0;
            background: transparent;
            border-radius: 0;
            max-width: 100%;
            width: 100%;
            flex-shrink: 0;
        }

        .day-card {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            padding: 20px;
            text-align: center;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .day-card .date {
            font-size: 14px;
            opacity: 0.8;
            margin-bottom: 10px;
        }

        .day-card .emoji {
            font-size: 30px;
            margin: 5px 0;
        }

        .day-card .temp-max {
            font-size: 22px;
            font-weight: bold;
        }

        .day-card .temp-min {
            font-size: 14px;
            opacity: 0.7;
            margin: 5px 0 10px;
        }

        .day-card .desc {
            font-size: 11px;
            opacity: 0.8;
        }

        .favorites {
            margin-top: 30px;
            width: 100%;
        }

        .favorites-title {
            font-size: 24px;
            margin-bottom: 20px;
            text-align: center;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
        }

        .favorites-list {
            display: flex;
            flex-direction: column;
            gap: 10px;
        }

        .favorite-item {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            padding: 15px;
            text-align: center;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .favorite-item .city-name {
            font-size: 18px;
            font-weight: bold;
        }

        .favorite-item .remove-btn {
            background: #ff6b6b;
            color: white;
            border: none;
            border-radius: 50%;
            width: 30px;
            height: 30px;
            cursor: pointer;
            font-size: 16px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .favorite-item .remove-btn:hover {
            background: #ee5a5a;
        }

        .error {
            background: rgba(255, 100, 100, 0.4);
            border-radius: 20px;
            padding: 30px;
            text-align: center;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 100, 100, 0.6);
            max-width: 500px;
            margin: 0 auto;
        }

        @media (max-width: 768px) {
            .container {
                width: 100%;
                background: rgba(0, 0, 0, 0.5);
            }
            .current-weather {
                height: 280px;
                padding: 40px 20px 20px;
            }
            .temp-display {
                font-size: 60px;
            }
            .forecast-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        @media (max-width: 480px) {
            .container {
                width: 100%;
                padding: 15px;
            }
            .current-weather {
                height: auto;
                padding: 30px 20px;
            }
            .weather-content h2 {
                font-size: 24px;
            }
            .temp-display {
                font-size: 48px;
            }
            .forecast-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div id="map"></div>
    
    <div class="container">
        <div class="search-box">
            <input type="text" id="cityInput" placeholder="Ingresa el nombre de la ciudad...">
            <button onclick="getWeather()">Buscar</button>
            <button class="favorite-btn" onclick="addToFavorites()">Guardar en favoritos</button>
        </div>
        
        <div class="content-wrapper">
            <div id="weatherDisplay"></div>
        </div>
        <div id="favoritesDisplay"></div>
    </div>

    <script src="https://cdnjs.cloudflare.com/ajax/libs/leaflet/1.9.4/leaflet.min.js"></script>
    <script>
        let map;
        let geocodeCache = {};
        let favorites = JSON.parse(localStorage.getItem('favorites')) || [];

        function initMap(lat, lon) {
            if (map) {
                map.setView([lat, lon], 10);
            } else {
                map = L.map('map').setView([lat, lon], 10);
                L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
                    attribution: '© OpenStreetMap contributors',
                    maxZoom: 19
                }).addTo(map);
            }
            L.marker([lat, lon]).addTo(map).bindPopup('📍 Ubicación');
        }

        function getWeatherEmoji(weatherCode, temp) {
            if (weatherCode === 0 || weatherCode === 1) return '☀️'; // Clear
            if (weatherCode === 2) return '🌤️'; // Partly cloudy
            if (weatherCode === 3) return '☁️'; // Overcast
            if (weatherCode === 45 || weatherCode === 48) return '🌫️'; // Fog
            if (weatherCode >= 51 && weatherCode <= 55) return '🌧️'; // Drizzle
            if (weatherCode >= 61 && weatherCode <= 65) return '🌧️'; // Rain
            if (weatherCode >= 71 && weatherCode <= 77) return '❄️'; // Snow
            if (weatherCode >= 80 && weatherCode <= 82) return '⛈️'; // Showers
            if (weatherCode >= 85 && weatherCode <= 86) return '❄️'; // Snow showers
            if (weatherCode >= 95 && weatherCode <= 99) return '⛈️'; // Thunderstorm
            return '🌡️';
        }

        function getTempEmoji(temp) {
            if (temp < 0) return '';
            if (temp < 10) return '';
            if (temp < 20) return '';
            if (temp < 30) return '';
            return '';
        }

        function getWeatherSimulation(weatherCode) {
            if (weatherCode >= 61 && weatherCode <= 65) return 'rain'; // Rain.
            if (weatherCode >= 71 && weatherCode <= 77 || weatherCode >= 85 && weatherCode <= 86) return 'snow'; // Snow.
            if (weatherCode >= 80 && weatherCode <= 82) return 'rain'; // Showers.
            if (weatherCode === 0 || weatherCode === 1) return 'sun'; // Clear.
            if (weatherCode === 2 || weatherCode === 3) return 'clouds'; // Cloudy.
            if (weatherCode >= 95 && weatherCode <= 99) return 'rain'; // Thunderstorm.
            return 'none';
        }

        function createWeatherSimulation(type) {
            if (type === 'rain') {
                return '<div class="weather-simulation"><div class="rain"></div></div>';
            }
            if (type === 'sun') {
                return '<div class="weather-simulation"><div class="sun"></div></div>';
            }
            if (type === 'clouds') {
                let clouds = '';
                for (let i = 0; i < 3; i++) {
                    clouds += `<div class="cloud" style="top: ${20 + i * 60}px; animation-delay: ${i * 5}s;"></div>`;
                }
                return `<div class="weather-simulation">${clouds}</div>`;
            }
            if (type === 'snow') {
                let snowflakes = '';
                for (let i = 0; i < 30; i++) {
                    const left = Math.random() * 100;
                    const delay = Math.random() * 10;
                    snowflakes += `<div class="snowflake" style="left: ${left}%; animation-delay: ${delay}s;">❄</div>`;
                }
                return `<div class="weather-simulation">${snowflakes}</div>`;
            }
            return '';
        }

        async function geocode(cityName) {
            if (geocodeCache[cityName]) return geocodeCache[cityName];
            const res = await fetch(`https://geocoding-api.open-meteo.com/v1/search?name=${encodeURIComponent(cityName)}&language=es`);
            const data = await res.json();
            if (!data.results || data.results.length === 0) throw new Error('Ciudad no encontrada');
            const { latitude, longitude, name, country } = data.results[0];
            geocodeCache[cityName] = { latitude, longitude, name, country };
            return { latitude, longitude, name, country };
        }

        async function getWeatherData(lat, lon) {
            const today = new Date();
            const weatherRes = await fetch(
                `https://api.open-meteo.com/v1/forecast?latitude=${lat}&longitude=${lon}&daily=temperature_2m_max,temperature_2m_min,weathercode&current_weather=true&timezone=auto`
            );
            const weatherData = await weatherRes.json();
            return weatherData;
        }

        function getWeatherCodeDescription(code) {
            const codes = {
                0: 'Cielo despejado', 
                1: 'Principalmente despejado', 
                2: 'Parcialmente nublado', 
                3: 'Nublado',
                45: 'Niebla', 
                48: 'Niebla escarcha',
                51: 'Llovizna ligera', 
                53: 'Llovizna moderada', 
                55: 'Llovizna densa',
                61: 'Lluvia ligera', 
                63: 'Lluvia moderada', 
                65: 'Lluvia fuerte',
                71: 'Nieve ligera', 
                73: 'Nieve moderada', 
                75: 'Nieve fuerte',
                77: 'Aguanieve', 
                80: 'Chubascos ligeros', 
                81: 'Chubascos moderados', 
                82: 'Chubascos violentos',
                85: 'Chubascos de nieve ligeros', 
                86: 'Chubascos de nieve fuertes',
                95: 'Tormenta', 
                96: 'Tormenta con granizo ligero', 
                99: 'Tormenta con granizo fuerte'
            };
            return codes[code] || 'Desconocido';
        }

        function formatDate(dateStr) {
            const date = new Date(dateStr + 'T00:00:00');
            return date.toLocaleDateString('es-ES', { weekday: 'short', month: 'short', day: 'numeric' });
        }

        async function getWeather() {
            const cityInput = document.getElementById('cityInput');
            const display = document.getElementById('weatherDisplay');
            const city = cityInput.value.trim();

            if (!city) {
                display.innerHTML = '<div class="error">Por favor ingresa el nombre de una ciudad</div>';
                return;
            }

            display.innerHTML = '<div style="text-align:center;padding:20px;color:white;text-shadow:2px 2px 4px rgba(0,0,0,0.5);">Cargando...</div>';

            try {
                const { latitude, longitude, name, country } = await geocode(city);
                initMap(latitude, longitude);
                const weatherData = await getWeatherData(latitude, longitude);

                const current = weatherData.current_weather;
                const daily = weatherData.daily;

                const simulation = getWeatherSimulation(current.weathercode);
                const emoji = getWeatherEmoji(current.weathercode, current.temperature);
                const tempEmoji = getTempEmoji(current.temperature);

                let html = `
                    <div class="current-weather">
                        ${simulation}
                        <div class="weather-content">
                            <h2>🗺️ ${name}, ${country}</h2>
                            <div class="emoji">${emoji} ${tempEmoji}</div>
                            <div class="temp-display">${Math.round(current.temperature)}°C</div>
                            <div class="desc">${getWeatherCodeDescription(current.weathercode)}</div>
                            <div class="date">Actualizado: ${new Date().toLocaleString('es-ES')}</div>
                        </div>
                    </div>
                `;

                display.innerHTML = html;

                // Add forecast
                let forecastHtml = `
                    <h3 class="forecast-title">📅 Pronóstico - Últimos 5 días</h3>
                    <div class="forecast-grid">
                `;

                for (let i = 0; i < 5; i++) {
                    const date = new Date();
                    date.setDate(date.getDate() - (4 - i));
                    const dateStr = date.toISOString().split('T')[0];
                    const code = daily.weathercode[i];
                    const emoji = getWeatherEmoji(code);
                    
                    forecastHtml += `
                        <div class="day-card">
                            <div class="date">${formatDate(dateStr)}</div>
                            <div class="emoji">${emoji}</div>
                            <div class="temp-max">${Math.round(daily.temperature_2m_max[i])}°C</div>
                            <div class="temp-min">${Math.round(daily.temperature_2m_min[i])}°C</div>
                            <div class="desc">${getWeatherCodeDescription(code)}</div>
                        </div>
                    `;
                }

                forecastHtml += '</div>';
                display.innerHTML += forecastHtml;

            } catch (error) {
                display.innerHTML = `<div class="error">❌ ${error.message}</div>`;
            }
        }

        function addToFavorites() {
            const city = document.getElementById('cityInput').value.trim();
            if (!city) {
                alert('Por favor ingresa el nombre de una ciudad primero.');
                return;
            }
            if (!favorites.includes(city)) {
                favorites.push(city);
                localStorage.setItem('favorites', JSON.stringify(favorites));
                displayFavorites();
            } else {
                alert('Esta ciudad ya está en favoritos.');
            }
        }

        function displayFavorites() {
            const display = document.getElementById('favoritesDisplay');
            if (favorites.length === 0) {
                display.innerHTML = '';
                return;
            }
            let favoritesHtml = '<div class="favorites"><h3 class="favorites-title">⭐ Ciudades Favoritas</h3><div class="favorites-list">';
            favorites.forEach((city, index) => {
                favoritesHtml += `<div class="favorite-item"><span class="city-name">${city}</span><button class="remove-btn" onclick="removeFavorite(${index})">×</button></div>`;
            });
            favoritesHtml += '</div></div>';
            display.innerHTML = favoritesHtml;
        }

        function removeFavorite(index) {
            favorites.splice(index, 1);
            localStorage.setItem('favorites', JSON.stringify(favorites));
            displayFavorites();
        }

        document.getElementById('cityInput').addEventListener('keypress', (e) => {
            if (e.key === 'Enter') getWeather();
        });

        // Initial load
        getWeather();
        displayFavorites();
    </script>
</body>
</html>