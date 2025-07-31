# Home Assistant Thermostat Automation Repo

This repo contains the following files for a smart, weather-based thermostat automation with day/night and seasonal mode:

- `weather_based_thermostat.yaml`: Blueprint to adjust your thermostat based on outdoor temperature, time of day, and seasonal mode
- `input_select.yaml`: Defines the seasonal mode selector helper (`Winter` / `Summer`)
- `auto_seasonal_mode.yaml`: Automation to auto-switch the seasonal mode based on date (April 1 and Oct 1)
  
## How to Use

1. Copy `input_select.yaml` content to your Home Assistant configuration (or create the helper via UI)
2. Import `weather_based_thermostat.yaml` as a Blueprint in Home Assistant
3. Create the `auto_seasonal_mode.yaml` automation manually or via UI to auto-switch season
4. When creating automation from the blueprint, assign your weather, thermostat, and seasonal_mode entities
5. Adjust temps and times if needed!

---

Enjoy your smart climate control!