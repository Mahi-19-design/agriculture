# 🌦 Weather API Research for Crop Disease Detection

This project explores and compares major **Weather APIs** that can be integrated into an **AI-based Crop Disease Detection System**.

Weather plays a crucial role in agriculture. Many plant diseases depend on environmental conditions such as **humidity, rainfall, temperature, and wind speed**. By integrating weather data with AI crop disease detection models, the system can provide **early warnings and predictive insights for farmers**.

---

# 📌 Table of Contents

- Overview
- Project Objective
- Why Weather Data Matters
- Quick API Decision Checklist
- Weather API Comparison
- Weather API Details
- Important Weather Parameters
- Example Disease Prediction Logic
- System Architecture
- Recommended APIs for Hackathons
- Future Improvements

---

# 🌱 Overview

This document compares the following Weather APIs:

- OpenWeather API
- Tomorrow.io API
- Weatherstack API
- Open-Meteo API

The comparison focuses on:

- Weather parameters available
- API request limits
- Pricing models
- Global coverage
- Agricultural relevance

---

# 🎯 Project Objective

The objective is to identify the most suitable weather API for integration with a **Crop Disease Detection Platform**.

The final system will provide:

- 🌾 Crop disease detection using AI
- 🌦 Weather-based disease risk prediction
- 🚨 Early alerts for farmers
- 📊 Environmental monitoring

---

# 🌿 Why Weather Data Matters

Many crop diseases depend heavily on environmental conditions.

| Disease | Weather Condition |
|-------|------------------|
| Powdery Mildew | High humidity |
| Leaf Blight | Warm + wet weather |
| Rust Disease | Rainfall + humidity |
| Downy Mildew | Cool + moist climate |

Combining **AI image detection + weather data** improves prediction accuracy.

---

# ⚡ Quick API Decision Checklist

Use this checklist for fast API selection.

```
[ ] Need a free API for hackathon
[ ] Need global coverage
[ ] Need high request limits
[ ] Need forecast data
[ ] Need historical weather data
[ ] Need advanced weather analytics
```

### Recommended Choices

| Requirement | API |
|-------------|-----|
| Beginner Friendly | OpenWeather |
| High Free Limits | Open-Meteo |
| Advanced Weather Intelligence | Tomorrow.io |
| Lightweight API | Weatherstack |

---

# 📊 Weather API Comparison

| Feature | OpenWeather | Tomorrow.io | Weatherstack | Open-Meteo |
|--------|-------------|-------------|--------------|------------|
| Global Coverage | ✅ | ✅ | ✅ | ✅ |
| Forecast Data | ✅ | ✅ | ✅ | ✅ |
| Historical Data | ✅ | Limited | ✅ | ✅ |
| Agricultural Data | Limited | Advanced | Basic | Moderate |
| Free Tier | Good | Limited | Small | Large |
| Ease of Integration | Easy | Medium | Easy | Easy |

---

# 🌍 Weather API Details

## 1️⃣ OpenWeather API

### Coverage
- Global coverage
- Uses latitude and longitude

### Parameters Provided

- Temperature
- Humidity
- Wind speed
- Atmospheric pressure
- Rainfall
- Cloud coverage
- UV index
- Visibility
- Weather alerts

### API Limits

Free Tier:

```
1000 API calls per day
60 calls per minute
```

### Pricing

| Plan | Price |
|------|------|
| Free | $0 |
| Pay-as-you-go | ~$0.001 per call |
| Enterprise | Custom pricing |

### Advantages

- Easy integration
- Good documentation
- Ideal for hackathons

---

## 2️⃣ Tomorrow.io API

### Coverage

- Global hyperlocal forecasts
- Satellite and radar data models

### Parameters

- Temperature
- Humidity
- Wind speed
- Precipitation
- Visibility
- Lightning probability
- Air quality
- Pollen levels

### API Limits

```
500 requests per day
25 requests per hour
```

### Pricing

| Plan | Price |
|------|------|
| Free | $0 |
| Developer | Paid |
| Enterprise | Custom |

### Advantages

- Highly accurate forecasts
- Advanced analytics

---

## 3️⃣ Weatherstack API

### Coverage

- Global coverage
- Multi-language support

### Parameters

- Temperature
- Humidity
- Wind speed
- Cloud cover
- Visibility
- Weather descriptions

### API Limits

```
100 API calls per month (Free Plan)
```

### Pricing

| Plan | Price | Calls |
|------|------|------|
| Free | $0 | 100/month |
| Standard | $9.99 | 50k/month |
| Professional | $49.99 | 300k/month |

---

## 4️⃣ Open-Meteo API

### Coverage

- Global weather models
- High resolution forecasts

### Parameters

- Temperature
- Rainfall
- Wind speed
- Solar radiation
- Air pressure
- Snow depth
- Soil temperature

### API Limits

```
10,000 requests per day
300,000 requests per month
```

### Pricing

| Plan | Price |
|------|------|
| Free | $0 |
| Standard | Paid |
| Professional | Paid |

### Advantages

- Very large free tier
- Great for research and data-heavy applications

---

# 🌾 Important Weather Parameters for Crop Disease Detection

| Parameter | Importance |
|----------|------------|
| Temperature | Influences pathogen growth |
| Humidity | Promotes fungal diseases |
| Rainfall | Helps spread disease spores |
| Wind Speed | Transmits pathogens |
| Solar Radiation | Affects plant stress |
| Soil Temperature | Influences root diseases |

---

# 🧠 Example Disease Prediction Logic

```python
humidity = 85
temperature = 27
rain_probability = 70

if humidity > 80 and 20 <= temperature <= 30 and rain_probability > 60:
    print("High Risk of Fungal Disease")
else:
    print("Low Disease Risk")
```

---

# 🏗 Suggested System Architecture

```
Farmer uploads crop image
        ↓
AI Model detects disease
        ↓
Get farmer location
        ↓
Fetch weather data using API
        ↓
Analyze weather conditions
        ↓
Predict disease risk
        ↓
Send recommendation to farmer
```

---

# 🚀 Recommended APIs for Hackathons

Best choices:

1. OpenWeather API
2. Open-Meteo API

Reasons:

- Large free tiers
- Global coverage
- Easy integration
- Good documentation

---

# 🔮 Future Improvements

Possible upgrades:

- Satellite crop monitoring
- IoT soil moisture sensors
- Machine learning disease prediction
- Regional disease outbreak alerts
- Weather-based pesticide recommendation

---

# 🤝 Contribution

Contributions are welcome!  
Feel free to open issues or submit pull requests.

---

# 📜 License

This project is licensed under the **MIT License**.