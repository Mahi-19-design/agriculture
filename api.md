# 🌦 Weather API — Hackathon Summary

---

## ✅ Best API: Open-Meteo (Primary) + OpenWeather (Secondary)

---

## 🥇 Open-Meteo — Primary API

**Why it's the best choice for our hackathon:**

- No API key, no registration, no credit card required — start instantly
- 10,000 free requests per day
- Covers all crop-disease-relevant parameters: humidity, temperature, rainfall, wind speed, solar radiation, and soil temperature
- Supports last 10 days of historical data via `past_days=10` parameter
- Non-commercial use is completely free — perfect for a hackathon

**Gandhinagar endpoint example:**
```
https://api.open-meteo.com/v1/forecast
  ?latitude=23.2156
  &longitude=72.6369
  &hourly=relative_humidity_2m,temperature_2m,precipitation,windspeed_10m
  &past_days=10
```

---

## 🥈 OpenWeather — Secondary API (for alerts + UV index)

**Use only for:**

- Government weather alerts
- UV index data (not available in Open-Meteo free tier)

**Free tier:** 1,000 calls/day — requires free account + credit card (set daily cap immediately after signup to avoid charges)

---

## 🤖 How Claude Haiku Accesses the Weather Data

Claude Haiku (model: `claude-haiku-4-5-20251001`) **does not call APIs directly**. The flow is:

1. **Your app code** calls the Open-Meteo API and gets JSON weather data
2. **Your app code** passes that JSON into Claude Haiku's prompt as context
3. **Claude Haiku** reads the data, reasons over it, and returns a disease risk verdict
```python
import requests
import anthropic

# Step 1: Fetch weather data (your code does this)
weather = requests.get(
    "https://api.open-meteo.com/v1/forecast",
    params={
        "latitude": 23.2156,
        "longitude": 72.6369,
        "hourly": "relative_humidity_2m,temperature_2m,precipitation",
        "past_days": 10
    }
).json()

# Step 2: Send to Claude Haiku with weather data as context
client = anthropic.Anthropic()
message = client.messages.create(
    model="claude-haiku-4-5-20251001",
    max_tokens=1024,
    messages=[
        {
            "role": "user",
            "content": f"""
You are a crop disease detection assistant.

Here is the last 10 days of weather data for Gandhinagar, India:
{weather}

Based on this weather data, assess the risk of fungal crop disease.
Flag any days where humidity exceeded 80% combined with temperatures between 20–30°C.
Give a risk level: Low / Medium / High.
            """
        }
    ]
)
print(message.content[0].text)
```

---

## 📊 Parameters Most Useful for Disease Detection

| Parameter | Open-Meteo Variable | Disease Link |
|-----------|-------------------|--------------|
| Humidity | `relative_humidity_2m` | Fungal growth trigger |
| Temperature | `temperature_2m` | Pathogen activity range |
| Rainfall | `precipitation` | Spore spread |
| Wind speed | `windspeed_10m` | Pathogen transmission |
| Soil temperature | `soil_temperature_0cm` | Root disease risk |
| Solar radiation | `shortwave_radiation` | Plant stress indicator |

---

## ⚡ Quick Summary

| Question | Answer |
|----------|--------|
| Best API | Open-Meteo |
| API key needed? | No |
| Last 10 days data? | Yes — `past_days=10` |
| Location for Gandhinagar | lat=23.2156, lon=72.6369 |
| Does Haiku call API itself? | No — your code fetches, then passes data |
| Claude model string | `claude-haiku-4-5-20251001` |
| Cost for hackathon | Free |
