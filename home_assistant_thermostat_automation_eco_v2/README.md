# Home Assistant Smart Thermostat Automation with Eco Mode

This repository contains configuration files for a smart thermostat automation that adjusts indoor temperature based on:

- Outdoor weather temperature
- Time of day (day/night)
- Seasonal mode (Winter / Summer / Eco)

## Files Included

- `blueprints/weather_based_thermostat.yaml`  
  Blueprint for automation using weather, time, and seasonal mode inputs

- `helpers/input_select.yaml`  
  Defines the `input_select.seasonal_mode` helper with options: Winter, Summer, Eco

- `automations/auto_seasonal_mode.yaml`  
  Automation to automatically switch seasonal mode based on date (April 1 & October 1)

## Setup Instructions

### 1. Add Seasonal Mode Helper

- Via UI:  
  Settings → Devices & Services → Helpers → Add Helper → Dropdown  
  Name: Seasonal Mode  
  Options: Winter, Summer, Eco

- Or add this to your `configuration.yaml` or helpers YAML file:
  ```yaml
  input_select:
    seasonal_mode:
      name: Seasonal Mode
      options:
        - Winter
        - Summer
        - Eco
      initial: Winter
      icon: mdi-weather-partly-snowy
  ```

### 2. Import Blueprint

- Go to Settings → Automations & Scenes → Blueprints → Import Blueprint  
- Paste the raw URL of the `weather_based_thermostat.yaml` file hosted on your GitHub repo  
- Assign the required inputs:  
  - Weather Entity (e.g., `weather.home`)  
  - Thermostat Entity (e.g., `climate.living_room`)  
  - Seasonal Mode Selector (e.g., `input_select.seasonal_mode`)

### 3. Create the Auto Seasonal Mode Automation

- Import the `auto_seasonal_mode.yaml` automation into Home Assistant (via UI or YAML)  
- This automation will automatically switch between Winter and Summer modes on April 1 and October 1  
- Eco mode must be set manually or by a custom automation

### 4. Enable & Test

- Enable the automation created from the blueprint  
- Adjust temperatures or time ranges if needed by editing the blueprint or automation options

## Customization

- Manually switch seasonal mode anytime via the helper dropdown  
- Modify temperature setpoints in the blueprint to fit your preferences  
- Add additional logic such as presence detection or eco modes if desired

## Support

Feel free to open issues or pull requests to suggest improvements or report bugs!

---

Enjoy your energy-efficient smart climate control!